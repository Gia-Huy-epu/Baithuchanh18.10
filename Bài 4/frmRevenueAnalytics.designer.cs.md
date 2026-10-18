namespace BaiTap4_RevenueAnalytics
{
    partial class frmRevenueAnalytics
    {
        private System.ComponentModel.IContainer components = null;
        private System.Windows.Forms.Label lblTitle;
        private System.Windows.Forms.Label lblCriteriaHeader;
        private System.Windows.Forms.Label lblFrom;
        private System.Windows.Forms.DateTimePicker dtpFrom;
        private System.Windows.Forms.Label lblTo;
        private System.Windows.Forms.DateTimePicker dtpTo;
        private System.Windows.Forms.Label lblBranch;
        private System.Windows.Forms.ComboBox cboBranch;
        private System.Windows.Forms.Button btnStat;
        private System.Windows.Forms.Button btnCancel;
        private System.Windows.Forms.Label lblStatusHeader;
        private System.Windows.Forms.Label lblProcessingStatus;
        private System.Windows.Forms.ProgressBar pgbLoading;
        private System.Windows.Forms.DataGridView dgvRevenueData;
        private System.Windows.Forms.Panel pnlLine;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null)) components.Dispose();
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            this.lblTitle = new System.Windows.Forms.Label();
            this.lblCriteriaHeader = new System.Windows.Forms.Label();
            this.lblFrom = new System.Windows.Forms.Label();
            this.dtpFrom = new System.Windows.Forms.DateTimePicker();
            this.lblTo = new System.Windows.Forms.Label();
            this.dtpTo = new System.Windows.Forms.DateTimePicker();
            this.lblBranch = new System.Windows.Forms.Label();
            this.cboBranch = new System.Windows.Forms.ComboBox();
            this.btnStat = new System.Windows.Forms.Button();
            this.btnCancel = new System.Windows.Forms.Button();
            this.lblStatusHeader = new System.Windows.Forms.Label();
            this.lblProcessingStatus = new System.Windows.Forms.Label();
            this.pgbLoading = new System.Windows.Forms.ProgressBar();
            this.dgvRevenueData = new System.Windows.Forms.DataGridView();
            this.pnlLine = new System.Windows.Forms.Panel();
            ((System.ComponentModel.ISupportInitialize)(this.dgvRevenueData)).BeginInit();
            this.SuspendLayout();

            // lblTitle
            this.lblTitle.AutoSize = true;
            this.lblTitle.Font = new System.Drawing.Font("Arial", 16F, System.Drawing.FontStyle.Bold);
            this.lblTitle.Location = new System.Drawing.Point(340, 20);
            this.lblTitle.Text = "THỐNG KÊ DOANH THU";

            // lblCriteriaHeader
            this.lblCriteriaHeader.AutoSize = true;
            this.lblCriteriaHeader.Location = new System.Drawing.Point(20, 70);
            this.lblCriteriaHeader.Text = "Tiêu chí thống kê";

            // Row Tiêu chí
            this.lblFrom.AutoSize = true;
            this.lblFrom.Location = new System.Drawing.Point(20, 103);
            this.lblFrom.Text = "Từ ngày:";

            this.dtpFrom.Format = System.Windows.Forms.DateTimePickerFormat.Short;
            this.dtpFrom.Location = new System.Drawing.Point(80, 100);
            this.dtpFrom.Size = new System.Drawing.Size(120, 22);

            this.lblTo.AutoSize = true;
            this.lblTo.Location = new System.Drawing.Point(220, 103);
            this.lblTo.Text = "Đến ngày:";

            this.dtpTo.Format = System.Windows.Forms.DateTimePickerFormat.Short;
            this.dtpTo.Location = new System.Drawing.Point(290, 100);
            this.dtpTo.Size = new System.Drawing.Size(120, 22);

            this.lblBranch.AutoSize = true;
            this.lblBranch.Location = new System.Drawing.Point(430, 103);
            this.lblBranch.Text = "Chi nhánh:";

            this.cboBranch.DropDownStyle = System.Windows.Forms.ComboBoxStyle.DropDownList;
            this.cboBranch.Items.AddRange(new object[] { "Tất cả chi nhánh", "Chi nhánh Hà Nội", "Chi nhánh Đà Nẵng", "Chi nhánh TP.HCM" });
            this.cboBranch.Location = new System.Drawing.Point(500, 100);
            this.cboBranch.Size = new System.Drawing.Size(150, 24);

            // Buttons
            this.btnStat.Location = new System.Drawing.Point(290, 150);
            this.btnStat.Size = new System.Drawing.Size(150, 35);
            this.btnStat.Text = "Thống kê doanh thu";
            this.btnStat.Click += new System.EventHandler(this.btnStat_Click);

            this.btnCancel.Location = new System.Drawing.Point(460, 150);
            this.btnCancel.Size = new System.Drawing.Size(120, 35);
            this.btnCancel.Text = "Hủy thao tác";
            this.btnCancel.Enabled = false;
            this.btnCancel.Click += new System.EventHandler(this.btnCancel_Click);

            // Đường kẻ ngang mờ phân cách
            this.pnlLine.BackColor = System.Drawing.Color.LightGray;
            this.pnlLine.Location = new System.Drawing.Point(20, 210);
            this.pnlLine.Size = new System.Drawing.Size(840, 1);

            // lblStatusHeader
            this.lblStatusHeader.AutoSize = true;
            this.lblStatusHeader.Location = new System.Drawing.Point(20, 230);
            this.lblStatusHeader.Text = "Trạng thái xử lý";

            // lblProcessingStatus
            this.lblProcessingStatus.AutoSize = true;
            this.lblProcessingStatus.Location = new System.Drawing.Point(20, 255);
            this.lblProcessingStatus.Text = "Sẵn sàng.";

            // pgbLoading
            this.pgbLoading.Location = new System.Drawing.Point(20, 280);
            this.pgbLoading.Size = new System.Drawing.Size(840, 15);

            // dgvRevenueData
            this.dgvRevenueData.Location = new System.Drawing.Point(20, 310);
            this.dgvRevenueData.Size = new System.Drawing.Size(840, 230);
            this.dgvRevenueData.BackgroundColor = System.Drawing.Color.White;

            // Form
            this.ClientSize = new System.Drawing.Size(880, 560);
            this.Controls.Add(this.pnlLine);
            this.Controls.Add(this.dgvRevenueData);
            this.Controls.Add(this.pgbLoading);
            this.Controls.Add(this.lblProcessingStatus);
            this.Controls.Add(this.lblStatusHeader);
            this.Controls.Add(this.btnCancel);
            this.Controls.Add(this.btnStat);
            this.Controls.Add(this.cboBranch);
            this.Controls.Add(this.lblBranch);
            this.Controls.Add(this.dtpTo);
            this.Controls.Add(this.lblTo);
            this.Controls.Add(this.dtpFrom);
            this.Controls.Add(this.lblFrom);
            this.Controls.Add(this.lblCriteriaHeader);
            this.Controls.Add(this.lblTitle);
            this.Text = "Bảng điều khiển thống kê doanh thu";
            this.StartPosition = System.Windows.Forms.FormStartPosition.CenterScreen;
            ((System.ComponentModel.ISupportInitialize)(this.dgvRevenueData)).EndInit();
            this.ResumeLayout(false);
            this.PerformLayout();
        }
    }
}
