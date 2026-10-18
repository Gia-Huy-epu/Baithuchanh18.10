namespace BaiTap3_HospitalMDI
{
    partial class frmHospitalMain
    {
        private System.ComponentModel.IContainer components = null;
        private System.Windows.Forms.MenuStrip menuStrip;
        private System.Windows.Forms.StatusStrip statusStrip;
        private System.Windows.Forms.ToolStripStatusLabel lblStatusInfo;
        private System.Windows.Forms.ToolStripProgressBar pgbStatus;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null)) components.Dispose();
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            this.menuStrip = new System.Windows.Forms.MenuStrip();
            this.statusStrip = new System.Windows.Forms.StatusStrip();
            this.lblStatusInfo = new System.Windows.Forms.ToolStripStatusLabel();
            this.pgbStatus = new System.Windows.Forms.ToolStripProgressBar();
            this.SuspendLayout();

            var menuSystem = new System.Windows.Forms.ToolStripMenuItem("Hệ thống");
            menuSystem.DropDownItems.Add("Thoát", null, menuExit_Click);

            var menuManage = new System.Windows.Forms.ToolStripMenuItem("Quản lý");
            menuManage.DropDownItems.Add("Hồ sơ Bệnh nhân", null, menuPatientProfiles_Click);
            menuManage.DropDownItems.Add("Lịch trực Bác sĩ", null, menuDoctorSchedule_Click);

            var menuWindows = new System.Windows.Forms.ToolStripMenuItem("Cửa sổ");
            menuWindows.DropDownItems.Add("Sắp xếp Xếp tầng", null, menuCascade_Click);
            menuWindows.DropDownItems.Add("Ngang", null, menuTileHor_Click);
            menuWindows.DropDownItems.Add("Dọc", null, menuTileVer_Click);
            menuWindows.DropDownItems.Add("Đóng tất cả", null, menuCloseAll_Click);

            this.menuStrip.Items.Add(menuSystem);
            this.menuStrip.Items.Add(menuManage);
            this.menuStrip.Items.Add(menuWindows);

            this.lblStatusInfo.Text = "Bác sĩ trực: Nguyễn Văn An   |   Nạp dữ liệu hoàn tất   Tiến trình: ";

            this.statusStrip.Items.Add(this.lblStatusInfo);
            this.statusStrip.Items.Add(this.pgbStatus);

            this.ClientSize = new System.Drawing.Size(1200, 700);
            this.Controls.Add(this.menuStrip);
            this.Controls.Add(this.statusStrip);
            this.MainMenuStrip = this.menuStrip;
            this.Text = "HỆ THỐNG QUẢN LÝ BỆNH VIỆN";
            this.ResumeLayout(false);
            this.PerformLayout();
        }
    }
}
