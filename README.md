# owls
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;
using System.Media;

namespace clicker
{
    /// <summary>
    /// Логика взаимодействия для MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
       
        public MainWindow()
        {
            InitializeComponent();
        }
        long point = 0;
        static int click = 1;
        double sol_b1 = 10 + 10 * (30 + click * 0.2);
        double sol_b2 = 20 + 20 * (60 + click * 0.4);

        public void Update()
        {
            poi.Content = "Points: " + point; // Вывод Points в первый label
            cli.Content = "Points for click: " + click; // Вывод Points per click во второй label
            b1.Content = (sol_b1).ToString(); //
            b2.Content = (sol_b2).ToString(); // Вывод цены Upgrade для Points per click на кнопке 
        }
        private void Grid_MouseDown(object sender, MouseButtonEventArgs e)
        {
            point += click;
            Update();
            SoundPlayer Simple = new SoundPlayer(@"Z:\шарага\3 ходка\тис\clicker\clicker\chickendown.wav");
            Simple.Play();
        }

        private void Button_Click(object sender, RoutedEventArgs e)
        {
            if (point >= (sol_b1))
            {
                point -= Convert.ToInt64(Math.Round(sol_b1));
                click += 3;
                Update();

            }

        }

        private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            if (point >= (sol_b1))
            {
                point -= Convert.ToInt64(Math.Round(sol_b2));
                click += 6;
                Update();

            }



           



        }

        private void Button_Click_2(object sender, RoutedEventArgs e)
        {
            Application.Current.Shutdown();
        }
    }
}
// вкаупирчалочмы 

        
                   
      
   
    
   
