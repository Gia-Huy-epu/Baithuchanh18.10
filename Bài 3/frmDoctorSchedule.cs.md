#nullable disable
using System.Data;
using System.Windows.Forms;

namespace BaiTap3_HospitalMDI
{
    public partial class frmDoctorSchedule : Form
    {
        private DataGridView dgvDoctors;

        public frmDoctorSchedule()
        {
            InitializeComponent();
            this.Text = "Lịch trực Bác sĩ";
            LoadData();
        }

        private void InitializeComponent()
        {
            this.ClientSize = new System.Drawing.Size(800, 300);

            dgvDoctors = new DataGridView();
            dgvDoctors.Dock = DockStyle.Fill;
            dgvDoctors.AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.Fill;
            dgvDoctors.AllowUserToAddRows = false;
            dgvDoctors.SelectionMode = DataGridViewSelectionMode.FullRowSelect;
            dgvDoctors.ReadOnly = true;

            this.Controls.Add(dgvDoctors);
        }

        private void LoadData()
        {
            DataTable dt = new DataTable();
            dt.Columns.Add("DoctorName", typeof(string));
            dt.Columns.Add("Department", typeof(string));
            dt.Columns.Add("Shift", typeof(string));
            dt.Columns.Add("Date", typeof(string));

            dt.Rows.Add("Nguyễn Văn A", "Cấp cứu", "07:00 - 15:00", "18/10/2026");
            dt.Rows.Add("Trần Thị B", "Nội tổng hợp", "15:00 - 23:00", "18/10/2026");
            dt.Rows.Add("Nguyễn Văn B", "Ngoại khoa", "23:00 - 07:00", "18/10/2026");

            dgvDoctors.DataSource = dt;
        }
    }
}
