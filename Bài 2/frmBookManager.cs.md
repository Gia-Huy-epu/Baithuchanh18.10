#nullable disable
using System;
using System.ComponentModel;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Windows.Forms;

namespace BaiTap2_BookManager
{
    public partial class frmBookManager : Form
    {
        private BindingList<BookModel> bookList;
        private string currentImagePath;

        public frmBookManager()
        {
            InitializeComponent();
            bookList = new BindingList<BookModel>();

            
            dgvBooks.AutoGenerateColumns = false;

            dgvBooks.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Title", HeaderText = "Tên sách" });
            dgvBooks.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "CoverPath", HeaderText = "Đường dẫn ảnh bìa" });
            dgvBooks.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Price", HeaderText = "Giá tiền", DefaultCellStyle = new DataGridViewCellStyle { Format = "N0" } });

            dgvBooks.DataSource = bookList;
            dgvBooks.AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.Fill;
            bookList.ListChanged += (s, e) => UpdateStatus();
            tmrClock.Start();
        }

        private void btnLoadCover_Click(object sender, EventArgs e)
        {
            using (OpenFileDialog ofd = new OpenFileDialog { Filter = "Images|*.png;*.jpg" })
            {
                if (ofd.ShowDialog() == DialogResult.OK)
                {
                    currentImagePath = ofd.FileName;
                    picBookCover.Image = Image.FromFile(currentImagePath);
                }
            }
        }

        private void menuOpenCsv_Click(object sender, EventArgs e)
        {
            using (OpenFileDialog ofd = new OpenFileDialog { Filter = "CSV Files|*.csv" })
            {
                if (ofd.ShowDialog() == DialogResult.OK)
                {
                    bookList.Clear();
                    var lines = File.ReadAllLines(ofd.FileName);
                    foreach (var line in lines)
                    {
                        var parts = line.Split(',');
                        if (parts.Length == 3)
                        {
                            bookList.Add(new BookModel { Title = parts[0], CoverPath = parts[1], Price = decimal.Parse(parts[2]) });
                        }
                    }
                }
            }
        }

        private void menuSaveCsv_Click(object sender, EventArgs e)
        {
            using (SaveFileDialog sfd = new SaveFileDialog { Filter = "CSV Files|*.csv" })
            {
                if (sfd.ShowDialog() == DialogResult.OK)
                {
                    var lines = bookList.Select(b => $"{b.Title},{b.CoverPath},{b.Price}");
                    File.WriteAllLines(sfd.FileName, lines);
                }
            }
        }

        private void btnAdd_Click(object sender, EventArgs e)
        {
            bookList.Add(new BookModel { Title = txtTitle.Text, CoverPath = currentImagePath, Price = decimal.Parse(txtPrice.Text) });
        }

        private void UpdateStatus()
        {
            lblTotalBooks.Text = $"Tổng sách: {bookList.Count} | ";
            lblTotalPrice.Text = $"Tổng giá trị: {bookList.Sum(b => b.Price):N0}";
        }

        private void tmrClock_Tick(object sender, EventArgs e)
        {
            lblTime.Text = $" | {DateTime.Now:HH:mm:ss}";
        }
    }
}
