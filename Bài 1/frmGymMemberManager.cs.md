#nullable disable
using System;
using System.ComponentModel;
using System.Text.RegularExpressions;
using System.Windows.Forms;

namespace BaiTap1_GymManager
{
    public partial class frmGymMemberManager : Form
    {
        private BindingList<MemberModel> memberList;
        private BindingSource bindingSource;
        private int idCounter = 1;

        public frmGymMemberManager()
        {
            InitializeComponent();
            InitializeData();
            SetupDataGridView();
            BindControls();
        }

        private void InitializeData()
        {
            memberList = new BindingList<MemberModel>();
            bindingSource = new BindingSource { DataSource = memberList };
            cboPackage.Items.AddRange(new string[] { "Theo tháng", "6 tháng", "1 năm" });
            GenerateNewId();
        }

        private void SetupDataGridView()
        {
            dgvMembers.AutoGenerateColumns = false;
            dgvMembers.SelectionMode = DataGridViewSelectionMode.FullRowSelect;
            dgvMembers.ReadOnly = true;
            dgvMembers.DataSource = bindingSource;

            dgvMembers.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "MemberId", HeaderText = "Mã HV", Width = 80 });
            dgvMembers.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "FullName", HeaderText = "Tên hội viên", Width = 150 });
            dgvMembers.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Phone", HeaderText = "SĐT", Width = 100 });
            dgvMembers.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Package", HeaderText = "Gói tập", Width = 100 });
            dgvMembers.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "StartDate", HeaderText = "Ngày ĐK", Width = 120 });
            dgvMembers.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Fee", HeaderText = "Phí dịch vụ", Width = 120, DefaultCellStyle = new DataGridViewCellStyle { Format = "N0" } });
        }

        private void BindControls()
        {
            txtMemberId.DataBindings.Add("Text", bindingSource, "MemberId", true, DataSourceUpdateMode.Never);
            txtFullName.DataBindings.Add("Text", bindingSource, "FullName", true, DataSourceUpdateMode.Never);
            txtPhone.DataBindings.Add("Text", bindingSource, "Phone", true, DataSourceUpdateMode.Never);
            cboPackage.DataBindings.Add("Text", bindingSource, "Package", true, DataSourceUpdateMode.Never);
            dtpStartDate.DataBindings.Add("Value", bindingSource, "StartDate", true, DataSourceUpdateMode.Never);
            txtFee.DataBindings.Add("Text", bindingSource, "Fee", true, DataSourceUpdateMode.Never, 0, "N0");
        }

        private void GenerateNewId()
        {
            txtMemberId.Text = $"HV{idCounter:D3}";
        }

        private bool ValidateInput()
        {
            errorProvider.Clear();
            bool isValid = true;

            if (string.IsNullOrWhiteSpace(txtFullName.Text) || !Regex.IsMatch(txtFullName.Text, @"^[a-zA-Z\sÀÁÂÃÈÉÊÌÍÒÓÔÕÙÚĂĐĨŨƠàáâãèéêìíòóôõùúăđĩũơƯĂẠẢẤẦẨẪẬẮẰẲẴẶẸẺẼỀỀỂưăạảấầẩẫậắằẳẵặẹẻẽềềểỄỆỈỊỌỎỐỒỔỖỘỚỜỞỠỢỤỦỨỪễệỉịọỏốồổỗộớờởỡợụủứừỬỮỰỲỴÝỶỸửữựỳỵỷỹ]+$"))
            {
                errorProvider.SetError(txtFullName, "Tên không hợp lệ");
                isValid = false;
            }
            if (!Regex.IsMatch(txtPhone.Text, @"^\d{10}$"))
            {
                errorProvider.SetError(txtPhone, "SĐT phải 10 chữ số");
                isValid = false;
            }
            if (!decimal.TryParse(txtFee.Text, out decimal fee) || fee <= 0)
            {
                errorProvider.SetError(txtFee, "Phí phải là số nguyên dương");
                isValid = false;
            }
            return isValid;
        }

        private void btnAdd_Click(object sender, EventArgs e)
        {
            if (!ValidateInput()) return;
            memberList.Add(new MemberModel
            {
                MemberId = txtMemberId.Text,
                FullName = txtFullName.Text,
                Phone = txtPhone.Text,
                Package = cboPackage.Text,
                StartDate = dtpStartDate.Value,
                Fee = decimal.Parse(txtFee.Text)
            });
            idCounter++;
            btnRefresh_Click(null, null);
        }

        private void btnEdit_Click(object sender, EventArgs e)
        {
            if (bindingSource.Current is MemberModel current && ValidateInput())
            {
                current.FullName = txtFullName.Text;
                current.Phone = txtPhone.Text;
                current.Package = cboPackage.Text;
                current.StartDate = dtpStartDate.Value;
                current.Fee = decimal.Parse(txtFee.Text);
                dgvMembers.Refresh();
            }
        }

        private void btnDelete_Click(object sender, EventArgs e)
        {
            if (bindingSource.Current != null)
            {
                if (MessageBox.Show("Xóa hội viên này?", "Cảnh báo", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                {
                    bindingSource.RemoveCurrent();
                }
            }
        }

        private void btnRefresh_Click(object sender, EventArgs e)
        {
            GenerateNewId();
            txtFullName.Clear();
            txtPhone.Clear();
            cboPackage.SelectedIndex = -1;
            dtpStartDate.Value = DateTime.Now;
            txtFee.Clear();
            errorProvider.Clear();
        }
    }
}
