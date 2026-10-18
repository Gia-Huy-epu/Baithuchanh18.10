namespace BaiTap5_CryptoTicker
{
    partial class frmCryptoStockTicker
    {
        private System.ComponentModel.IContainer components = null;
        private System.Windows.Forms.Button btnStart;
        private System.Windows.Forms.Button btnPause;
        private System.Windows.Forms.Label lblBTCPrice;
        private System.Windows.Forms.StatusStrip statusStrip;
        private System.Windows.Forms.ToolStripStatusLabel lblLastUpdate;
        private System.Windows.Forms.ToolStripStatusLabel lblSyncCount;
        private System.Windows.Forms.DataGridView dgvHistoryLog;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null)) components.Dispose();
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            this.btnStart = new System.Windows.Forms.Button();
            this.btnPause = new System.Windows.Forms.Button();
            this.lblBTCPrice = new System.Windows.Forms.Label();
            this.statusStrip = new System.Windows.Forms.StatusStrip();
            this.lblLastUpdate = new System.Windows.Forms.ToolStripStatusLabel();
            this.lblSyncCount = new System.Windows.Forms.ToolStripStatusLabel();
            this.dgvHistoryLog = new System.Windows.Forms.DataGridView();
            ((System.ComponentModel.ISupportInitialize)(this.dgvHistoryLog)).BeginInit();
            this.SuspendLayout();

            this.btnStart.Location = new System.Drawing.Point(20, 20);
            this.btnStart.Size = new System.Drawing.Size(150, 40);
            this.btnStart.Text = "Bắt đầu Giám sát";
            this.btnStart.Click += new System.EventHandler(this.btnStart_Click);

            this.btnPause.Location = new System.Drawing.Point(190, 20);
            this.btnPause.Size = new System.Drawing.Size(150, 40);
            this.btnPause.Text = "Tạm dừng";
            this.btnPause.Click += new System.EventHandler(this.btnPause_Click);

            this.lblBTCPrice.AutoSize = true;
            this.lblBTCPrice.Location = new System.Drawing.Point(20, 80);
            this.lblBTCPrice.Font = new System.Drawing.Font("Arial", 18F, System.Drawing.FontStyle.Bold);
            this.lblBTCPrice.Text = "BTC/USD: 50,000.00";

            this.dgvHistoryLog.Location = new System.Drawing.Point(20, 130);
            this.dgvHistoryLog.Size = new System.Drawing.Size(450, 250);
            this.dgvHistoryLog.AllowUserToAddRows = false;

            this.statusStrip.Items.Add(this.lblLastUpdate);
            this.statusStrip.Items.Add(this.lblSyncCount);

            this.ClientSize = new System.Drawing.Size(500, 430);
            this.Controls.Add(this.dgvHistoryLog);
            this.Controls.Add(this.lblBTCPrice);
            this.Controls.Add(this.btnPause);
            this.Controls.Add(this.btnStart);
            this.Controls.Add(this.statusStrip);
            this.Text = "Giám sát Tỷ giá Crypto";
            ((System.ComponentModel.ISupportInitialize)(this.dgvHistoryLog)).EndInit();
            this.ResumeLayout(false);
            this.PerformLayout();
        }
    }
}
