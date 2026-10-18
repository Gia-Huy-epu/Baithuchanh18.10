#nullable disable
using System;
using System.ComponentModel;

namespace BaiTap1_GymManager
{
    public class MemberModel : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler PropertyChanged;
        private string memberId;
        private string fullName;
        private string phone;
        private string package;
        private DateTime startDate;
        private decimal fee;

        public string MemberId { get => memberId; set { memberId = value; OnPropertyChanged("MemberId"); } }
        public string FullName { get => fullName; set { fullName = value; OnPropertyChanged("FullName"); } }
        public string Phone { get => phone; set { phone = value; OnPropertyChanged("Phone"); } }
        public string Package { get => package; set { package = value; OnPropertyChanged("Package"); } }
        public DateTime StartDate { get => startDate; set { startDate = value; OnPropertyChanged("StartDate"); } }
        public decimal Fee { get => fee; set { fee = value; OnPropertyChanged("Fee"); } }

        protected void OnPropertyChanged(string name) => PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(name));
    }
}
