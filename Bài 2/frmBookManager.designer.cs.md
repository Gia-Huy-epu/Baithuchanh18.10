namespace BaiTap2_BookManager
{
    partial class frmBookManager
    {
        private System.ComponentModel.IContainer components = null;
        private System.Windows.Forms.MenuStrip menuStrip;
        private System.Windows.Forms.ToolStrip toolStrip;
        private System.Windows.Forms.StatusStrip statusStrip;
        private System.Windows.Forms.DataGridView dgvBooks;
        private System.Windows.Forms.PictureBox picBookCover;
        private System.Windows.Forms.Button btnLoadCover;
        private System.Windows.Forms.Label lblTitle;
        private System.Windows.Forms.Label lblPrice;
        private System.Windows.Forms.TextBox txtTitle;
        private System.Windows.Forms.TextBox txtPrice;
        private System.Windows.Forms.ToolStripStatusLabel lblTotalBooks;
        private System.Windows.Forms.ToolStripStatusLabel lblTotalPrice;
        private System.Windows.Forms.ToolStripStatusLabel lblTime;
        private System.Windows.Forms.Timer tmrClock;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null)) components.Dispose();
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            components = new System.ComponentModel.Container();
            menuStrip = new MenuStrip();
            menuFile = new ToolStripMenuItem();
            toolStrip = new ToolStrip();
            btnAdd = new ToolStripButton();
            statusStrip = new StatusStrip();
            lblTotalBooks = new ToolStripStatusLabel();
            lblTotalPrice = new ToolStripStatusLabel();
            lblTime = new ToolStripStatusLabel();
            dgvBooks = new DataGridView();
            picBookCover = new PictureBox();
            btnLoadCover = new Button();
            lblTitle = new Label();
            lblPrice = new Label();
            txtTitle = new TextBox();
            txtPrice = new TextBox();
            tmrClock = new System.Windows.Forms.Timer(components);
            menuStrip.SuspendLayout();
            toolStrip.SuspendLayout();
            statusStrip.SuspendLayout();
            ((System.ComponentModel.ISupportInitialize)dgvBooks).BeginInit();
            ((System.ComponentModel.ISupportInitialize)picBookCover).BeginInit();
            SuspendLayout();
            // 
            // menuStrip
            // 
            menuStrip.ImageScalingSize = new Size(20, 20);
            menuStrip.Items.AddRange(new ToolStripItem[] { menuFile });
            menuStrip.Location = new Point(0, 0);
            menuStrip.Name = "menuStrip";
            menuStrip.Size = new Size(800, 28);
            menuStrip.TabIndex = 8;
            // 
            // menuFile
            // 
            menuFile.Name = "menuFile";
            menuFile.Size = new Size(46, 24);
            menuFile.Text = "File";
            // 
            // toolStrip
            // 
            toolStrip.ImageScalingSize = new Size(20, 20);
            toolStrip.Items.AddRange(new ToolStripItem[] { btnAdd });
            toolStrip.Location = new Point(0, 28);
            toolStrip.Name = "toolStrip";
            toolStrip.Size = new Size(800, 27);
            toolStrip.TabIndex = 7;
            // 
            // btnAdd
            // 
            btnAdd.Name = "btnAdd";
            btnAdd.Size = new Size(113, 24);
            btnAdd.Text = "Thêm sách mới";
            btnAdd.Click += btnAdd_Click;
            // 
            // statusStrip
            // 
            statusStrip.ImageScalingSize = new Size(20, 20);
            statusStrip.Items.AddRange(new ToolStripItem[] { lblTotalBooks, lblTotalPrice, lblTime });
            statusStrip.Location = new Point(0, 428);
            statusStrip.Name = "statusStrip";
            statusStrip.Size = new Size(800, 22);
            statusStrip.TabIndex = 9;
            // 
            // lblTotalBooks
            // 
            lblTotalBooks.Name = "lblTotalBooks";
            lblTotalBooks.Size = new Size(0, 16);
            // 
            // lblTotalPrice
            // 
            lblTotalPrice.Name = "lblTotalPrice";
            lblTotalPrice.Size = new Size(0, 16);
            // 
            // lblTime
            // 
            lblTime.Name = "lblTime";
            lblTime.Size = new Size(0, 16);
            // 
            // dgvBooks
            // 
            dgvBooks.ColumnHeadersHeight = 29;
            dgvBooks.Location = new Point(170, 150);
            dgvBooks.Name = "dgvBooks";
            dgvBooks.RowHeadersWidth = 51;
            dgvBooks.Size = new Size(600, 250);
            dgvBooks.TabIndex = 0;
            // 
            // picBookCover
            // 
            picBookCover.BorderStyle = BorderStyle.FixedSingle;
            picBookCover.Location = new Point(20, 70);
            picBookCover.Name = "picBookCover";
            picBookCover.Size = new Size(120, 160);
            picBookCover.SizeMode = PictureBoxSizeMode.StretchImage;
            picBookCover.TabIndex = 6;
            picBookCover.TabStop = false;
            // 
            // btnLoadCover
            // 
            btnLoadCover.Location = new Point(20, 240);
            btnLoadCover.Name = "btnLoadCover";
            btnLoadCover.Size = new Size(120, 30);
            btnLoadCover.TabIndex = 5;
            btnLoadCover.Text = "Tải ảnh bìa";
            btnLoadCover.Click += btnLoadCover_Click;
            // 
            // lblTitle
            // 
            lblTitle.AutoSize = true;
            lblTitle.Location = new Point(170, 73);
            lblTitle.Name = "lblTitle";
            lblTitle.Size = new Size(68, 20);
            lblTitle.TabIndex = 4;
            lblTitle.Text = "Tên sách:";
            // 
            // lblPrice
            // 
            lblPrice.AutoSize = true;
            lblPrice.Location = new Point(170, 113);
            lblPrice.Name = "lblPrice";
            lblPrice.Size = new Size(63, 20);
            lblPrice.TabIndex = 2;
            lblPrice.Text = "Giá tiền:";
            // 
            // txtTitle
            // 
            txtTitle.Location = new Point(240, 70);
            txtTitle.Name = "txtTitle";
            txtTitle.Size = new Size(250, 27);
            txtTitle.TabIndex = 3;
            // 
            // txtPrice
            // 
            txtPrice.Location = new Point(240, 110);
            txtPrice.Name = "txtPrice";
            txtPrice.Size = new Size(250, 27);
            txtPrice.TabIndex = 1;
            // 
            // tmrClock
            // 
            tmrClock.Interval = 1000;
            tmrClock.Tick += tmrClock_Tick;
            // 
            // frmBookManager
            // 
            ClientSize = new Size(800, 450);
            Controls.Add(dgvBooks);
            Controls.Add(txtPrice);
            Controls.Add(lblPrice);
            Controls.Add(txtTitle);
            Controls.Add(lblTitle);
            Controls.Add(btnLoadCover);
            Controls.Add(picBookCover);
            Controls.Add(toolStrip);
            Controls.Add(menuStrip);
            Controls.Add(statusStrip);
            MainMenuStrip = menuStrip;
            Name = "frmBookManager";
            Text = "Quản lý Tài liệu Sách";
            menuStrip.ResumeLayout(false);
            menuStrip.PerformLayout();
            toolStrip.ResumeLayout(false);
            toolStrip.PerformLayout();
            statusStrip.ResumeLayout(false);
            statusStrip.PerformLayout();
            ((System.ComponentModel.ISupportInitialize)dgvBooks).EndInit();
            ((System.ComponentModel.ISupportInitialize)picBookCover).EndInit();
            ResumeLayout(false);
            PerformLayout();
        }

        private ToolStripMenuItem menuFile;
        private ToolStripButton btnAdd;
    }
}
