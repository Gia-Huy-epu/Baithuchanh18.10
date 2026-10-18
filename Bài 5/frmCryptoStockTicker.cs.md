#nullable disable
using System;
using System.Drawing;
using System.Threading;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace BaiTap5_CryptoTicker
{
    public partial class frmCryptoStockTicker : Form
    {
        private bool isRunning;
        private decimal currentPrice = 50000m;
        private Random rand = new Random();
        private int syncCount = 0;

        public frmCryptoStockTicker()
        {
            InitializeComponent();
            dgvHistoryLog.AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.Fill;
            dgvHistoryLog.Columns.Add("Time", "Thời gian");
            dgvHistoryLog.Columns.Add("Price", "Giá BTC/USD");
        }

        private void btnStart_Click(object sender, EventArgs e)
        {
            if (isRunning) return;
            isRunning = true;
            Task.Run(() => BackgroundTicker());
        }

        private void btnPause_Click(object sender, EventArgs e)
        {
            isRunning = false;
        }

        private void BackgroundTicker()
        {
            while (isRunning)
            {
                Thread.Sleep(2000);
                decimal change = (decimal)(rand.NextDouble() * 1000 - 500);
                decimal newPrice = currentPrice + change;
                bool isUp = newPrice >= currentPrice;
                currentPrice = newPrice;

                UpdateUI(newPrice, isUp);
            }
        }

        private void UpdateUI(decimal price, bool isUp)
        {
            if (this.InvokeRequired)
            {
                this.Invoke(new Action(() => UpdateUI(price, isUp)));
                return;
            }

            lblBTCPrice.Text = $"BTC/USD: {price:N2}";
            lblBTCPrice.ForeColor = isUp ? Color.Green : Color.Red;

            syncCount++;
            lblLastUpdate.Text = $"Cập nhật: {DateTime.Now:HH:mm:ss} | ";
            lblSyncCount.Text = $"Đồng bộ: {syncCount}";

            dgvHistoryLog.Rows.Insert(0, DateTime.Now.ToString("HH:mm:ss"), price.ToString("N2"));
        }
    }
}
