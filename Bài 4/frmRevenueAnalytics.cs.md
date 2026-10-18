#nullable disable
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Drawing;
using System.Threading;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace BaiTap4_RevenueAnalytics
{
   
    public class RevenueRecord
    {
        public string TransactionId { get; set; }
        public string TransactionDate { get; set; }
        public string Branch { get; set; }
        public string Description { get; set; }
        public decimal Amount { get; set; }
    }

    public partial class frmRevenueAnalytics : Form
    {
        private CancellationTokenSource cts;
        private Random rand = new Random();
        private BindingList<RevenueRecord> revenueList;

        public frmRevenueAnalytics()
        {
            InitializeComponent();
            SetupDataGridView();
            cboBranch.SelectedIndex = 0; 
        }

        private void SetupDataGridView()
        {
            dgvRevenueData.AutoGenerateColumns = false;
            dgvRevenueData.AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.Fill;
            dgvRevenueData.SelectionMode = DataGridViewSelectionMode.FullRowSelect;
            dgvRevenueData.ReadOnly = true;
            dgvRevenueData.RowHeadersVisible = false;

            
            dgvRevenueData.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "TransactionId", HeaderText = "Mã GD" });
            dgvRevenueData.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "TransactionDate", HeaderText = "Ngày giao dịch" });
            dgvRevenueData.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Branch", HeaderText = "Chi nhánh" });
            dgvRevenueData.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Description", HeaderText = "Mô tả" });
            dgvRevenueData.Columns.Add(new DataGridViewTextBoxColumn { DataPropertyName = "Amount", HeaderText = "Số tiền", DefaultCellStyle = new DataGridViewCellStyle { Format = "N0", Alignment = DataGridViewContentAlignment.MiddleRight } });
        }

        private async void btnStat_Click(object sender, EventArgs e)
        {
            cts = new CancellationTokenSource();
            btnStat.Enabled = false;
            btnCancel.Enabled = true;

            
            revenueList = new BindingList<RevenueRecord>();
            dgvRevenueData.DataSource = revenueList;
            pgbLoading.Value = 0;
            pgbLoading.Maximum = 10;
            lblProcessingStatus.Text = "Đang bắt đầu tổng hợp dữ liệu...";
            lblProcessingStatus.ForeColor = Color.Black;

            string[] branches = { "Chi nhánh Hà Nội", "Chi nhánh Đà Nẵng", "Chi nhánh TP.HCM" };

            try
            {
                for (int i = 1; i <= 10; i++)
                {
                   
                    cts.Token.ThrowIfCancellationRequested();

                    
                    await Task.Delay(300, cts.Token);

                    
                    int idNum = i * 10;
                    revenueList.Add(new RevenueRecord
                    {
                        TransactionId = $"GD0{idNum}",
                        TransactionDate = DateTime.Now.AddDays(-rand.Next(1, 10)).AddHours(rand.Next(1, 12)).ToString("dd/MM/yyyy h:mm tt"),
                        Branch = branches[rand.Next(branches.Length)],
                        Description = $"Giao dịch bán hàng {idNum}",
                        Amount = (decimal)(rand.NextDouble() * 5000000) + 100000
                    });

                    
                    pgbLoading.Value = i;
                    lblProcessingStatus.Text = $"Đang xử lý... ({i}/10)";
                }

                
                lblProcessingStatus.Text = "Hoàn tất! Đã tổng hợp 10 giao dịch.";
                lblProcessingStatus.ForeColor = Color.Green;
                MessageBox.Show("Thống kê doanh thu hoàn tất!", "Thông báo", MessageBoxButtons.OK, MessageBoxIcon.Information);
            }
            catch (OperationCanceledException)
            {
                lblProcessingStatus.Text = "Trạng thái xử lý: Đã hủy thao tác!";
                lblProcessingStatus.ForeColor = Color.Red;
            }
            finally
            {
                btnStat.Enabled = true;
                btnCancel.Enabled = false;
            }
        }

        private void btnCancel_Click(object sender, EventArgs e)
        {
            cts?.Cancel();
            btnCancel.Enabled = false;
        }
    }
}
