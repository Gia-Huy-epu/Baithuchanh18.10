namespace BaiTap1_GymManager
{
    partial class frmGymMemberManager
    {
        private System.ComponentModel.IContainer components = null;
        private System.Windows.Forms.Label lblId;
        private System.Windows.Forms.Label lblName;
        private System.Windows.Forms.Label lblPhone;
        private System.Windows.Forms.Label lblPackage;
        private System.Windows.Forms.Label lblDate;
        private System.Windows.Forms.Label lblFee;
        private System.Windows.Forms.TextBox txtMemberId;
        private System.Windows.Forms.TextBox txtFullName;
        private System.Windows.Forms.TextBox txtPhone;
        private System.Windows.Forms.ComboBox cboPackage;
        private System.Windows.Forms.DateTimePicker dtpStartDate;
        private System.Windows.Forms.TextBox txtFee;
        private System.Windows.Forms.Button btnAdd;
        private System.Windows.Forms.Button btnEdit;
        private System.Windows.Forms.Button btnDelete;
        private System.Windows.Forms.Button btnRefresh;
        private System.Windows.Forms.DataGridView dgvMembers;
        private System.Windows.Forms.ErrorProvider errorProvider;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null)) components.Dispose();
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            this.components = new System.ComponentModel.Container();
            this.lblId = new System.Windows.Forms.Label();
            this.lblName = new System.Windows.Forms.Label();
            this.lblPhone = new System.Windows.Forms.Label();
            this.lblPackage = new System.Windows.Forms.Label();
            this.lblDate = new System.Windows.Forms.Label();
            this.lblFee = new System.Windows.Forms.Label();
            this.txtMemberId = new System.Windows.Forms.TextBox();
            this.txtFullName = new System.Windows.Forms.TextBox();
            this.txtPhone = new System.Windows.Forms.TextBox();
            this.cboPackage = new System.Windows.Forms.ComboBox();
            this.dtpStartDate = new System.Windows.Forms.DateTimePicker();
            this.txtFee = new System.Windows.Forms.TextBox();
            this.btnAdd = new System.Windows.Forms.Button();
            this.btnEdit = new System.Windows.Forms.Button();
            this.btnDelete = new System.Windows.Forms.Button();
            this.btnRefresh = new System.Windows.Forms.Button();
            this.dgvMembers = new System.Windows.Forms.DataGridView();
            this.errorProvider = new System.Windows.Forms.ErrorProvider(this.components);
            ((System.ComponentModel.ISupportInitialize)(this.dgvMembers)).BeginInit();
            ((System.ComponentModel.ISupportInitialize)(this.errorProvider)).BeginInit();
            this.SuspendLayout();

            this.lblId.AutoSize = true;
            this.lblId.Location = new System.Drawing.Point(20, 23);
            this.lblId.Text = "Mã hội viên:";

            this.lblName.AutoSize = true;
            this.lblName.Location = new System.Drawing.Point(20, 63);
            this.lblName.Text = "Họ và tên:";

            this.lblPhone.AutoSize = true;
            this.lblPhone.Location = new System.Drawing.Point(20, 103);
            this.lblPhone.Text = "Số điện thoại:";

            this.lblPackage.AutoSize = true;
            this.lblPackage.Location = new System.Drawing.Point(20, 143);
            this.lblPackage.Text = "Gói tập:";

            this.lblDate.AutoSize = true;
            this.lblDate.Location = new System.Drawing.Point(20, 183);
            this.lblDate.Text = "Ngày đăng ký:";

            this.lblFee.AutoSize = true;
            this.lblFee.Location = new System.Drawing.Point(20, 223);
            this.lblFee.Text = "Phí dịch vụ:";

            this.txtMemberId.Location = new System.Drawing.Point(120, 20);
            this.txtMemberId.Size = new System.Drawing.Size(220, 22);

            this.txtFullName.Location = new System.Drawing.Point(120, 60);
            this.txtFullName.Size = new System.Drawing.Size(220, 22);

            this.txtPhone.Location = new System.Drawing.Point(120, 100);
            this.txtPhone.Size = new System.Drawing.Size(220, 22);

            this.cboPackage.Location = new System.Drawing.Point(120, 140);
            this.cboPackage.Size = new System.Drawing.Size(220, 22);

            this.dtpStartDate.Location = new System.Drawing.Point(120, 180);
            this.dtpStartDate.Size = new System.Drawing.Size(220, 22);

            this.txtFee.Location = new System.Drawing.Point(120, 220);
            this.txtFee.Size = new System.Drawing.Size(220, 22);

            this.btnAdd.Location = new System.Drawing.Point(380, 20);
            this.btnAdd.Size = new System.Drawing.Size(120, 30);
            this.btnAdd.Text = "Thêm mới";
            this.btnAdd.Click += new System.EventHandler(this.btnAdd_Click);

            this.btnEdit.Location = new System.Drawing.Point(380, 60);
            this.btnEdit.Size = new System.Drawing.Size(120, 30);
            this.btnEdit.Text = "Sửa thông tin";
            this.btnEdit.Click += new System.EventHandler(this.btnEdit_Click);

            this.btnDelete.Location = new System.Drawing.Point(380, 100);
            this.btnDelete.Size = new System.Drawing.Size(120, 30);
            this.btnDelete.Text = "Xóa hội viên";
            this.btnDelete.Click += new System.EventHandler(this.btnDelete_Click);

            this.btnRefresh.Location = new System.Drawing.Point(380, 140);
            this.btnRefresh.Size = new System.Drawing.Size(120, 30);
            this.btnRefresh.Text = "Làm mới";
            this.btnRefresh.Click += new System.EventHandler(this.btnRefresh_Click);

            this.dgvMembers.Location = new System.Drawing.Point(20, 270);
            this.dgvMembers.Size = new System.Drawing.Size(740, 250);

            this.errorProvider.ContainerControl = this;

            this.ClientSize = new System.Drawing.Size(790, 540);
            this.Controls.Add(this.dgvMembers);
            this.Controls.Add(this.btnRefresh);
            this.Controls.Add(this.btnDelete);
            this.Controls.Add(this.btnEdit);
            this.Controls.Add(this.btnAdd);
            this.Controls.Add(this.txtFee);
            this.Controls.Add(this.dtpStartDate);
            this.Controls.Add(this.cboPackage);
            this.Controls.Add(this.txtPhone);
            this.Controls.Add(this.txtFullName);
            this.Controls.Add(this.txtMemberId);
            this.Controls.Add(this.lblFee);
            this.Controls.Add(this.lblDate);
            this.Controls.Add(this.lblPackage);
            this.Controls.Add(this.lblPhone);
            this.Controls.Add(this.lblName);
            this.Controls.Add(this.lblId);
            this.Text = "Quản lý Hội Viên";
            ((System.ComponentModel.ISupportInitialize)(this.dgvMembers)).EndInit();
            ((System.ComponentModel.ISupportInitialize)(this.errorProvider)).EndInit();
            this.ResumeLayout(false);
            this.PerformLayout();
        }
    }
}
