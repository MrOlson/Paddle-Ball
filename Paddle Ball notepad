using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
/*
      ********************************************
             Mr. Olson
             Week 2 Assignment Due April 13th
             Paddle Ball
      **********************************************
    */
namespace Paddle_Ball
{
    public partial class Form1 : Form
    {
        public int speed_left = 4;
        public int speed_top = 4;
        public int point = 0;

        public Form1()
        {
            InitializeComponent();
            timer1.Enabled = true;
            timer1.Interval = 1;

            Cursor.Hide();   // this will hide the cursor

            this.FormBorderStyle = FormBorderStyle.None;   // this will remove andy boarder
            this.TopMost = true;                            // This will bring the form to the front/panel
            this.Bounds = Screen.PrimaryScreen.Bounds; // this will set the panel as big as the screen
            Racket.Top = Playground.Bottom - 30;


            


            lbl_GameOver.Hide();
            lbl_GameOver.Left = Playground.Width / 2 - lbl_GameOver.Width / 2;  // puts game over in the middle 
            lbl_GameOver.Top = Playground.Height / 2 - lbl_GameOver.Height / 2; // puts in the top bottom middle
            
           

        }

        

        private void Form1_KeyDown(object sender, KeyEventArgs e)
        {
            if (e.KeyCode == Keys.Escape)
            {
                this.Close();
            }
            if (e.KeyCode == Keys.F1)
            {
                point = 0;
                lbl_points.Text = "0";
                ball.Top = 30;
                ball.Left = 30;
                speed_left = 4;
                speed_top = 4;
                timer1.Enabled = true;
                lbl_GameOver.Hide();
                Playground.BackColor = Color.White;
            }


            if (e.KeyCode == Keys.P)
            {
                if (timer1.Enabled == false)
                {
                    timer1.Enabled = true;
                }
                else
                {
                    timer1.Enabled = false;
                }
            }
        }

        private void Timer1_Tick(object sender, EventArgs e)
        {
            Racket.Left= Cursor.Position.X - (Racket.Width / 2);
            ball.Left += speed_left;
            ball.Top += speed_top;

          
            // this code checks to see if the ball hits the paddle
            //  if it does it reverses the speed_top and it continues

            if (ball.Bottom >= Racket.Top && ball.Bottom <= Racket.Bottom && ball.Left >= Racket.Left && ball.Right <= Racket.Right)
            {
                speed_top += 2;
                speed_left += 2;
                speed_top = -speed_top;

                point += 1;
                lbl_points.Text = point.ToString();

                Random r = new Random();
                Playground.BackColor = Color.FromArgb(r.Next(150, 255), r.Next(150, 255), r.Next(150, 255));

            }
            if (ball.Left <= Playground.Left)
            {
                speed_left = -speed_left;
            }
            if (ball.Right >= Playground.Right)
            {
                speed_left = -speed_left;
            }
            if (ball.Top <= Playground.Top)
            {
                speed_top = -speed_top;
            }

            // 

            // this code checks to see if it hits the bottom 
            // if it does the time is stoped and the game is over.
            if (ball.Bottom >= Playground.Bottom)
            {
                timer1.Enabled = false;
                lbl_GameOver.Show();

            }

        }

        private void Ball_Click(object sender, EventArgs e)
        {

        }
    }

    
}
