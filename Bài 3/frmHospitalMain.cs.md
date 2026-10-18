#nullable disable
using System;
using System.Linq;
using System.Windows.Forms;

namespace BaiTap3_HospitalMDI
{
    public partial class frmHospitalMain : Form
    {
        public frmHospitalMain()
        {
            InitializeComponent();
            this.IsMdiContainer = true;
            this.WindowState = FormWindowState.Maximized; 
        }

        private void OpenSingleInstanceForm<T>() where T : Form, new()
        {
            Form childForm = this.MdiChildren.FirstOrDefault(f => f is T);
            if (childForm != null)
            {
                childForm.Activate();
            }
            else
            {
                childForm = new T();
                childForm.MdiParent = this;
                childForm.Show();
            }
        }

        private void menuPatientProfiles_Click(object sender, EventArgs e) => OpenSingleInstanceForm<frmPatientProfiles>();
        private void menuDoctorSchedule_Click(object sender, EventArgs e) => OpenSingleInstanceForm<frmDoctorSchedule>();
        private void menuCascade_Click(object sender, EventArgs e) => this.LayoutMdi(MdiLayout.Cascade);
        private void menuTileHor_Click(object sender, EventArgs e) => this.LayoutMdi(MdiLayout.TileHorizontal);
        private void menuTileVer_Click(object sender, EventArgs e) => this.LayoutMdi(MdiLayout.TileVertical);
        private void menuCloseAll_Click(object sender, EventArgs e)
        {
            foreach (Form child in this.MdiChildren) child.Close();
        }
        private void menuExit_Click(object sender, EventArgs e) => Application.Exit();
    }
}
