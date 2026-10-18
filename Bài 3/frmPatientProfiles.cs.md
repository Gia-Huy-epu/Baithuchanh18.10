#nullable disable
using System.Data;
using System.Windows.Forms;

namespace BaiTap3_HospitalMDI
{
    public partial class frmPatientProfiles : Form
    {
        private DataGridView dgvPatients;

        public frmPatientProfiles()
        {
            InitializeComponent();
            this.Text = "Hồ sơ Bệnh nhân";
            LoadData();
        }

        private void InitializeComponent()
        {
            this.ClientSize = new System.Drawing.Size(800, 300);

            dgvPatients = new DataGridView();
            dgvPatients.Dock = DockStyle.Fill;
            dgvPatients.AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.Fill;
            dgvPatients.AllowUserToAddRows = false;
            dgvPatients.SelectionMode = DataGridViewSelectionMode.FullRowSelect;
            dgvPatients.ReadOnly = true;

            this.Controls.Add(dgvPatients);
        }

        private void LoadData()
        {
            DataTable dt = new DataTable();
            dt.Columns.Add("PatientId", typeof(string));
            dt.Columns.Add("FullName", typeof(string));
            dt.Columns.Add("Age", typeof(int));
            dt.Columns.Add("Gender", typeof(string));
            dt.Columns.Add("Department", typeof(string));

            dt.Rows.Add("BN001", "Nguyễn Thị A", 25, "Nữ", "Nội tổng hợp");
            dt.Rows.Add("BN002", "Trần Thị B", 32, "Nữ", "Tim mạch");
            dt.Rows.Add("BN003", "Lê Hoàng ", 41, "Nam", "Ngoại khoa");

            dgvPatients.DataSource = dt;
        }
    }
}
