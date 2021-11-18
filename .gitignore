package whacksrcc;
import java.awt.Container;
import java.awt.Color;
import java.awt.Font;
import java.awt.Image;
import java.awt.Point;
import java.awt.Toolkit;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Random;

import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JButton;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JOptionPane;
import javax.swing.SwingConstants;
import javax.swing.Timer;
import javax.swing.border.EmptyBorder;


public class Game4 extends JFrame{
    
    private JPanel panel;
    
    private int score1 = 0;
    private JLabel[] holes1 = new JLabel[9];
    private int[] board1 = new int[9];
    private int highscore1 = 0;
    
    private int score2 = 0;
    private JLabel[] holes2 = new JLabel[12];
    private int[] board2 = new int[12];
    private int highscore2 = 0;
    
    private int score3 = 0;
    private JLabel[] holes3 = new JLabel[16];
    private int[] board3 = new int[16];
    private int highscore3 = 0;

    private int timeLeft1 = 60;
    private int timeLeft2 = 40;
    private int timeLeft3 = 30;
    
    private JLabel lblScore1;
    private JLabel lblTimeLeft1;
    private JLabel lblHighscore1;
    
    private JLabel lblScore2;
    private JLabel lblTimeLeft2;
    private JLabel lblHighscore2;
    
    private JLabel lblScore3;
    private JLabel lblTimeLeft3;
    private JLabel lblHighscore3;
    
    private JButton menuStart;
    private JButton btn1Start;
    private JButton btn2Start;
    private JButton btn3Start;
    private JButton nextlevel2;
    private JButton nextlevel3;
    private Timer timer1;
    private Timer timer2;
    private Timer timer3;
    
    TSH1 menuHandler1 = new TSH1();
    TSH2 menuHandler2 = new TSH2();
    TSH3 menuHandler3 = new TSH3();
    
    //1
    private void loadHighscore1(){
        BufferedReader br1 = null;
        String line = "";
        try {
            br1 = new BufferedReader(new FileReader(System.getProperty("user.dir") + "/highscore1.txt"));
            line = br1.readLine();
            br1.close();
        } catch (IOException e) { line = ""; }
        if(line != ""){
            highscore1 = Integer.parseInt(line);
            lblHighscore1.setText("Highscore: " + highscore1);
        }
    }
    public void saveHighscore1(){
        BufferedWriter bw1 = null;
        try {
            bw1 = new BufferedWriter(new FileWriter(System.getProperty("user.dir") + "/highscore1.txt", false)); //append - set to false
            bw1.write("" + highscore1);
            bw1.flush();
            bw1.close();
        } catch (IOException e) {
            JOptionPane.showMessageDialog(this, e.getMessage(), "Error while saving highscore", JOptionPane.ERROR_MESSAGE);
        }
    }
    private void gameOver1(){     
        btn1Start.setEnabled(true);
        if(score1 > highscore1){
            highscore1 = score1;
            lblHighscore1.setText("Highscore: " + highscore1);
            JOptionPane.showMessageDialog(this, "Your final score is: " + score1, "You beat the high score!", JOptionPane.INFORMATION_MESSAGE);
        } else{
            JOptionPane.showMessageDialog(this, "Your final score is: " + score1, "Game Over!", JOptionPane.INFORMATION_MESSAGE);
        }
        score1 = 0;
        timeLeft1 = 60;
        lblScore1.setText("Score: 0");
        lblTimeLeft1.setText("60");
        clearBoard1();
        saveHighscore1();
    }
    private void pressedButton1(int id1){
        int val1 = board1[id1];
        //if val is 1 = mole
        //if val is 0 = empty hole
        if(val1==1){ 
            score1++;
        } else{ //val==0
            score1--;
        }
        lblScore1.setText("Score: " + score1); //update the score
        clearBoard1();
        genRandMole1();  
    }
    private void initEvents1(){
        for(int i = 0; i < holes1.length; i++){
            holes1[i].addMouseListener(new MouseAdapter() {
                public void mouseClicked(MouseEvent e){
                    JLabel lbl = (JLabel)e.getSource();
                    int id1 = Integer.parseInt(lbl.getName());
                    pressedButton1(id1);
                }
            });
        }
        btn1Start.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                btn1Start.setEnabled(false);
                clearBoard1();
                genRandMole1();
                timer1.start();
            }
        });
        timer1 = new Timer(1000, new ActionListener() {
            public void actionPerformed(ActionEvent evt) {
                if(timeLeft1 == 0){
                    lblTimeLeft1.setText("" + timeLeft1);
                    timer1.stop();
                    gameOver1();
                }
                lblTimeLeft1.setText("" + timeLeft1);
                timeLeft1--;
            }
        });
    }
    
    //2
    private void loadHighscore2(){
        BufferedReader br2 = null;
        String line = "";
        try {
            br2 = new BufferedReader(new FileReader(System.getProperty("user.dir") + "/highscore2.txt"));
            line = br2.readLine();
            br2.close();
        } catch (IOException e) { line = ""; }
        if(line != ""){
            highscore2 = Integer.parseInt(line);
            lblHighscore2.setText("Highscore: " + highscore2);
        }
    }
    public void saveHighscore2(){
        BufferedWriter bw2 = null;
        try {
            bw2 = new BufferedWriter(new FileWriter(System.getProperty("user.dir") + "/highscore2.txt", false)); //append - set to false
            bw2.write("" + highscore2);
            bw2.flush();
            bw2.close();
        } catch (IOException e) {
            JOptionPane.showMessageDialog(this, e.getMessage(), "Error while saving highscore", JOptionPane.ERROR_MESSAGE);
        }
    }
    private void gameOver2(){     
        btn2Start.setEnabled(true);
        if(score2 > highscore2){
            highscore2 = score2;
            lblHighscore2.setText("Highscore: " + highscore2);
            JOptionPane.showMessageDialog(this, "Your final score is: " + score2, "You beat the high score!", JOptionPane.INFORMATION_MESSAGE);
        } else{
            JOptionPane.showMessageDialog(this, "Your final score is: " + score2, "Game Over!", JOptionPane.INFORMATION_MESSAGE);
        }
        score2 = 0;
        timeLeft2 = 40;
        lblScore2.setText("Score: 0");
        lblTimeLeft2.setText("40");
        clearBoard2();
        saveHighscore2();
    }
    private void pressedButton2(int id2){
        int val2 = board2[id2];
        //if val is 1 = mole
        //if val is 0 = empty hole
        if(val2==1){ 
            score2++;
        } else{ //val==0
            score2--;
        }
        lblScore2.setText("Score: " + score2); //update the score
        clearBoard2();
        genRandMole2();  
    }
    private void initEvents2(){
        for(int i = 0; i < holes2.length; i++){
            holes2[i].addMouseListener(new MouseAdapter() {
                public void mouseClicked(MouseEvent e){
                    JLabel lbl = (JLabel)e.getSource();
                    int id2 = Integer.parseInt(lbl.getName());
                    pressedButton2(id2);
                }
            });
        }
        btn2Start.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                btn2Start.setEnabled(false);
                clearBoard2();
                genRandMole2();
                timer2.start();
            }
        });
        timer2 = new Timer(1000, new ActionListener() {
            public void actionPerformed(ActionEvent evt) {
                if(timeLeft2 == 0){
                    lblTimeLeft2.setText("" + timeLeft2);
                    timer2.stop();
                    gameOver2();
                }
                lblTimeLeft2.setText("" + timeLeft2);
                timeLeft2--;
            }
        });
    }
    
    //3
    private void loadHighscore3(){
        BufferedReader br3 = null;
        String line = "";
        try {
            br3 = new BufferedReader(new FileReader(System.getProperty("user.dir") + "/highscore3.txt"));
            line = br3.readLine();
            br3.close();
        } catch (IOException e) { line = ""; }
        if(line != ""){
            highscore3 = Integer.parseInt(line);
            lblHighscore3.setText("Highscore: " + highscore3);
        }
    }
    public void saveHighscore3(){
        BufferedWriter bw3 = null;
        try {
            bw3 = new BufferedWriter(new FileWriter(System.getProperty("user.dir") + "/highscore3.txt", false)); //append - set to false
            bw3.write("" + highscore3);
            bw3.flush();
            bw3.close();
        } catch (IOException e) {
            JOptionPane.showMessageDialog(this, e.getMessage(), "Error while saving highscore", JOptionPane.ERROR_MESSAGE);
        }
    }
    private void gameOver3(){     
        btn3Start.setEnabled(true);
        if(score3 > highscore3){
            highscore3 = score3;
            lblHighscore3.setText("Highscore: " + highscore3);
            JOptionPane.showMessageDialog(this, "Your final score is: " + score3, "You beat the high score!", JOptionPane.INFORMATION_MESSAGE);
        } else{
            JOptionPane.showMessageDialog(this, "Your final score is: " + score3, "Game Over!", JOptionPane.INFORMATION_MESSAGE);
        }
        score3 = 0;
        timeLeft3 = 30;
        lblScore3.setText("Score: 0");
        lblTimeLeft3.setText("30");
        clearBoard3();
        saveHighscore3();
    }
    private void pressedButton3(int id3){
        int val3 = board3[id3];
        //if val is 1 = mole
        //if val is 0 = empty hole
        if(val3==1){ 
            score3++;
        } else{ //val==0
            score3--;
        }
        lblScore3.setText("Score: " + score3); //update the score
        clearBoard3();
        genRandMole3();  
    }
    private void initEvents3(){
        for(int i = 0; i < holes3.length; i++){
            holes3[i].addMouseListener(new MouseAdapter() {
                public void mouseClicked(MouseEvent e){
                    JLabel lbl = (JLabel)e.getSource();
                    int id3 = Integer.parseInt(lbl.getName());
                    pressedButton3(id3);
                }
            });
        }
        btn3Start.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                btn3Start.setEnabled(false);
                clearBoard1();
                genRandMole1();
                timer3.start();
            }
        });
        timer3 = new Timer(1000, new ActionListener() {
            public void actionPerformed(ActionEvent evt) {
                if(timeLeft3 == 0){
                    lblTimeLeft3.setText("" + timeLeft3);
                    timer3.stop();
                    gameOver3();
                }
                lblTimeLeft3.setText("" + timeLeft3);
                timeLeft3--;
            }
        });
    }
    
     public Game4() { //window menu
        setTitle("Whack A Mole");
        setResizable(false); 
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setBounds(100, 100, 608, 720);
                
        JPanel contentPane = new JPanel();
        contentPane = new JPanel();
        contentPane.setBackground(new Color(0, 51, 0));
        contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
        contentPane.setLayout(null);
       
        JLabel lblTitle = new JLabel("Whack A Mole");
        lblTitle.setForeground(new Color(153, 204, 0));
        lblTitle.setHorizontalAlignment(SwingConstants.CENTER);
        lblTitle.setFont(new Font("Century Gothic", Font.BOLD, 60));
        lblTitle.setBounds(0, 100, 602, 47);
        contentPane.add(lblTitle);
        
        menuStart = new JButton("START");
        menuStart.setBackground(Color.WHITE);
        menuStart.setFont(new Font("Cambria", Font.BOLD, 30));
        menuStart.setBounds(240, 200, 150,47);
        contentPane.add(menuStart);
        menuStart.addActionListener(menuHandler1);
        
        setContentPane(contentPane);
    }
        public  void createGamelv1(){
            menuStart.setVisible(false);//step to this new window
            
            setTitle("Whack A Mole");
            setResizable(false); 
            setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            setBounds(100, 100, 608, 720);

            JPanel contentPane = new JPanel();
            contentPane = new JPanel();
            contentPane.setBackground(new Color(0, 51, 0));
            contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
            contentPane.setLayout(null);

            JLabel lblTitle = new JLabel("Whack A Mole LV.I");
            lblTitle.setForeground(new Color(153, 204, 0));
            lblTitle.setHorizontalAlignment(SwingConstants.CENTER);
            lblTitle.setFont(new Font("Century Gothic", Font.BOLD, 20));
            lblTitle.setBounds(0, 0, 602, 47);
            contentPane.add(lblTitle);

            panel = new JPanel();
            panel.setBackground(new Color(0, 102, 0));
            panel.setBounds(32, 105, 535, 546);
            panel.setLayout(null);
            panel.setCursor(Toolkit.getDefaultToolkit().createCustomCursor(loadImage("res/hammer3.png").getImage(), new Point(0,0),"custom cursor1"));
            contentPane.add(panel);

            holes1[0] = new JLabel("0");
            holes1[0].setName("0");
            holes1[0].setBounds(0, 0, 132, 132);
            panel.add(holes1[0]);

            holes1[1] = new JLabel("1");
            holes1[1].setName("1");
            holes1[1].setBounds(264, 0, 132, 132);
            panel.add(holes1[1]);

            holes1[2] = new JLabel("2");
            holes1[2].setName("2");
            holes1[2].setBounds(132, 132, 132, 132);
            panel.add(holes1[2]);

            holes1[3] = new JLabel("3");
            holes1[3].setName("3");
            holes1[3].setBounds(264, 132, 132, 132);
            panel.add(holes1[3]);

            holes1[4] = new JLabel("4");
            holes1[4].setName("4");
            holes1[4].setBounds(396, 132, 132, 132);
            panel.add(holes1[4]);

            holes1[5] = new JLabel("5");
            holes1[5].setName("5");
            holes1[5].setBounds(0, 264, 132, 132);
            panel.add(holes1[5]);

            holes1[6] = new JLabel("6");
            holes1[6].setName("6");
            holes1[6].setBounds(132, 264, 132, 132);
            panel.add(holes1[6]);

            holes1[7] = new JLabel("7");
            holes1[7].setName("7");
            holes1[7].setBounds(132, 396, 132, 132);
            panel.add(holes1[7]);

            holes1[8] = new JLabel("8");
            holes1[8].setName("8");
            holes1[8].setBounds(396, 396, 132, 132);
            panel.add(holes1[8]);

            lblScore1 = new JLabel("Score: 0");//score play : turn
            lblScore1.setHorizontalAlignment(SwingConstants.TRAILING);
            lblScore1.setFont(new Font("Cambria", Font.BOLD, 20));
            lblScore1.setForeground(new Color(135, 206, 250));
            lblScore1.setBounds(423, 54, 144, 33);
            contentPane.add(lblScore1);

            lblTimeLeft1 = new JLabel("60");//time play : sec
            lblTimeLeft1.setHorizontalAlignment(SwingConstants.CENTER);
            lblTimeLeft1.setForeground(new Color(240, 128, 128));
            lblTimeLeft1.setFont(new Font("Cambria Math", Font.BOLD, 33));
            lblTimeLeft1.setBounds(225, 55, 144, 33);
            contentPane.add(lblTimeLeft1);

            lblHighscore1 = new JLabel("Highscore: 0");
            lblHighscore1.setHorizontalAlignment(SwingConstants.TRAILING);
            lblHighscore1.setForeground(new Color(255, 255, 0));
            lblHighscore1.setFont(new Font("Cambria", Font.BOLD, 20));
            lblHighscore1.setBounds(433, 18, 134, 33);
            contentPane.add(lblHighscore1);

            btn1Start = new JButton("Start");
            btn1Start.setBackground(Color.WHITE);
            btn1Start.setFont(new Font("Cambria", Font.BOLD, 20));
            btn1Start.setBounds(40, 60, 110, 35);
            contentPane.add(btn1Start);
            
            nextlevel2 = new JButton("next level"); 
            nextlevel2.setBackground(Color.WHITE);
            nextlevel2.setFont(new Font("Cambria", Font.BOLD, 20)); 
            nextlevel2.setBounds(35, 20, 125, 35);
            contentPane.add(nextlevel2);
            nextlevel2.addActionListener(menuHandler2);

            setContentPane(contentPane);
        }
        public  void createGamelv2(){
            nextlevel2.setVisible(false);//step to this new window
            
            setTitle("Whack A Mole");
            setResizable(false); 
            setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            setBounds(100, 100, 608, 720);

            JPanel contentPane = new JPanel();
            contentPane = new JPanel();
            contentPane.setBackground(new Color(0, 51, 0));
            contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
            contentPane.setLayout(null);

            JLabel lblTitle = new JLabel("Whack A Mole LV.II");
            lblTitle.setForeground(new Color(153, 204, 0));
            lblTitle.setHorizontalAlignment(SwingConstants.CENTER);
            lblTitle.setFont(new Font("Century Gothic", Font.BOLD, 20));
            lblTitle.setBounds(0, 0, 602, 47);
            contentPane.add(lblTitle);

            panel = new JPanel();
            panel.setBackground(new Color(0, 102, 0));
            panel.setBounds(32, 105, 535, 546);
            panel.setLayout(null);
            panel.setCursor(Toolkit.getDefaultToolkit().createCustomCursor(loadImage("res/hammer3.png").getImage(), new Point(0,0),"custom cursor1"));
            contentPane.add(panel);

            holes2[0] = new JLabel("0");
            holes2[0].setName("0");
            holes2[0].setBounds(0, 0, 132, 132);
            panel.add(holes2[0]);

            holes2[1] = new JLabel("1");
            holes2[1].setName("1");
            holes2[1].setBounds(264, 0, 132, 132);
            panel.add(holes2[1]);

            holes2[2] = new JLabel("2");
            holes2[2].setName("2");
            holes2[2].setBounds(132, 132, 132, 132);
            panel.add(holes2[2]);

            holes2[3] = new JLabel("3");
            holes2[3].setName("3");
            holes2[3].setBounds(264, 132, 132, 132);
            panel.add(holes2[3]);

            holes2[4] = new JLabel("4");
            holes2[4].setName("4");
            holes2[4].setBounds(396, 132, 132, 132);
            panel.add(holes2[4]);

            holes2[5] = new JLabel("5");
            holes2[5].setName("5");
            holes2[5].setBounds(0, 264, 132, 132);
            panel.add(holes2[5]);

            holes2[6] = new JLabel("6");
            holes2[6].setName("6");
            holes2[6].setBounds(132, 264, 132, 132);
            panel.add(holes2[6]);

            holes2[7] = new JLabel("7");
            holes2[7].setName("7");
            holes2[7].setBounds(132, 396, 132, 132);
            panel.add(holes2[7]);

            holes2[8] = new JLabel("8");
            holes2[8].setName("8");
            holes2[8].setBounds(396, 396, 132, 132);
            panel.add(holes2[8]);
            
            holes2[9] = new JLabel("9");
            holes2[9].setName("9");
            holes2[9].setBounds(132, 0, 132, 132);
            panel.add(holes2[9]);
     
            holes2[10] = new JLabel("10");
            holes2[10].setName("10");
            holes2[10].setBounds(396, 0, 132, 132);
            panel.add(holes2[10]);

            holes2[11] = new JLabel("11");
            holes2[11].setName("11");
            holes2[11].setBounds(264, 264, 132, 132);
            panel.add(holes2[11]);

            lblScore2 = new JLabel("Score: 0");//score play : turn
            lblScore2.setHorizontalAlignment(SwingConstants.TRAILING);
            lblScore2.setFont(new Font("Cambria", Font.BOLD, 20));
            lblScore2.setForeground(new Color(135, 206, 250));
            lblScore2.setBounds(423, 54, 144, 33);
            contentPane.add(lblScore2);

            lblTimeLeft2 = new JLabel("40");//time play : sec
            lblTimeLeft2.setHorizontalAlignment(SwingConstants.CENTER);
            lblTimeLeft2.setForeground(new Color(240, 128, 128));
            lblTimeLeft2.setFont(new Font("Cambria Math", Font.BOLD, 33));
            lblTimeLeft2.setBounds(225, 55, 144, 33);
            contentPane.add(lblTimeLeft2);

            lblHighscore2 = new JLabel("Highscore: 0");
            lblHighscore2.setHorizontalAlignment(SwingConstants.TRAILING);
            lblHighscore2.setForeground(new Color(255, 255, 0));
            lblHighscore2.setFont(new Font("Cambria", Font.BOLD, 20));
            lblHighscore2.setBounds(433, 18, 134, 33);
            contentPane.add(lblHighscore2);

            btn2Start = new JButton("Start");
            btn2Start.setBackground(Color.WHITE);
            btn2Start.setFont(new Font("Cambria", Font.BOLD, 20));
            btn2Start.setBounds(40, 60, 110, 35);
            contentPane.add(btn2Start);
            
            nextlevel3 = new JButton("next level"); 
            nextlevel3.setBackground(Color.WHITE);
            nextlevel3.setFont(new Font("Cambria", Font.BOLD, 20)); 
            nextlevel3.setBounds(35, 20, 125, 35);
            contentPane.add(nextlevel3);
            nextlevel3.addActionListener(menuHandler3);

            setContentPane(contentPane);
        }
        public  void createGamelv3(){
            nextlevel3.setVisible(false);//step to this new window
            
            setTitle("Whack A Mole");
            setResizable(false); 
            setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            setBounds(100, 100, 608, 720);

            JPanel contentPane = new JPanel();
            contentPane = new JPanel();
            contentPane.setBackground(new Color(0, 51, 0));
            contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
            contentPane.setLayout(null);

            JLabel lblTitle = new JLabel("Whack A Mole LV.III");
            lblTitle.setForeground(new Color(153, 204, 0));
            lblTitle.setHorizontalAlignment(SwingConstants.CENTER);
            lblTitle.setFont(new Font("Century Gothic", Font.BOLD, 20));
            lblTitle.setBounds(0, 0, 602, 47);
            contentPane.add(lblTitle);
            
            JLabel lblTitle2 = new JLabel("*final LV*");
            lblTitle2.setForeground(new Color(160, 204, 0));
            lblTitle2.setFont(new Font("Century Gothic", Font.BOLD, 25));
            lblTitle2.setBounds(35, 20, 120, 35);
            contentPane.add(lblTitle2);

            panel = new JPanel();
            panel.setBackground(new Color(0, 102, 0));
            panel.setBounds(32, 105, 535, 546);
            panel.setLayout(null);
            panel.setCursor(Toolkit.getDefaultToolkit().createCustomCursor(
            loadImage("res/hammer3.png").getImage(),
            new Point(0,0),"custom cursor1"));
            contentPane.add(panel);

            holes3[0] = new JLabel("0");
            holes3[0].setName("0");
            holes3[0].setBounds(0, 396, 132, 132);
            panel.add(holes3[0]);

            holes3[1] = new JLabel("1");
            holes3[1].setName("1");
            holes3[1].setBounds(132, 396, 132, 132);
            panel.add(holes3[1]);

            holes3[2] = new JLabel("2");
            holes3[2].setName("2");
            holes3[2].setBounds(264, 396, 132, 132);
            panel.add(holes3[2]);

            holes3[3] = new JLabel("3");
            holes3[3].setName("3");
            holes3[3].setBounds(396, 396, 132, 132);
            panel.add(holes3[3]);

            holes3[4] = new JLabel("4");
            holes3[4].setName("4");
            holes3[4].setBounds(0, 264, 132, 132);
            panel.add(holes3[4]);

            holes3[5] = new JLabel("5");
            holes3[5].setName("5");
            holes3[5].setBounds(132, 264, 132, 132);
            panel.add(holes3[5]);

            holes3[6] = new JLabel("6");
            holes3[6].setName("6");
            holes3[6].setBounds(264, 264, 132, 132);
            panel.add(holes3[6]);

            holes3[7] = new JLabel("7");
            holes3[7].setName("7");
            holes3[7].setBounds(396, 264, 132, 132);
            panel.add(holes3[7]);

            holes3[8] = new JLabel("8");
            holes3[8].setName("8");
            holes3[8].setBounds(0, 132, 132, 132);
            panel.add(holes3[8]);

            holes3[9] = new JLabel("9");
            holes3[9].setName("9");
            holes3[9].setBounds(132, 132, 132, 132);
            panel.add(holes3[9]);
     
            holes3[10] = new JLabel("10");
            holes3[10].setName("10");
            holes3[10].setBounds(264, 132, 132, 132);
            panel.add(holes3[10]);

            holes3[11] = new JLabel("11");
            holes3[11].setName("11");
            holes3[11].setBounds(396, 132, 132, 132);
            panel.add(holes3[11]);

            holes3[12] = new JLabel("12");
            holes3[12].setName("12");
            holes3[12].setBounds(0, 0, 132, 132);
            panel.add(holes3[12]);

            holes3[13] = new JLabel("13");
            holes3[13].setName("13");
            holes3[13].setBounds(132, 0, 132, 132);
            panel.add(holes3[13]);

            holes3[14] = new JLabel("14");
            holes3[14].setName("14");
            holes3[14].setBounds(264, 0, 132, 132);
            panel.add(holes3[14]);

            holes3[15] = new JLabel("15");
            holes3[15].setName("15");
            holes3[15].setBounds(396, 0, 132, 132);
            panel.add(holes3[15]);

            lblScore3 = new JLabel("Score: 0");//score play : turn
            lblScore3.setHorizontalAlignment(SwingConstants.TRAILING);
            lblScore3.setFont(new Font("Cambria", Font.BOLD, 20));
            lblScore3.setForeground(new Color(135, 206, 250));
            lblScore3.setBounds(423, 54, 144, 33);
            contentPane.add(lblScore3);

            lblTimeLeft3 = new JLabel("30");//time play : sec
            lblTimeLeft3.setHorizontalAlignment(SwingConstants.CENTER);
            lblTimeLeft3.setForeground(new Color(240, 128, 128));
            lblTimeLeft3.setFont(new Font("Cambria Math", Font.BOLD, 33));
            lblTimeLeft3.setBounds(225, 55, 144, 33);
            contentPane.add(lblTimeLeft3);

            lblHighscore3 = new JLabel("Highscore: 0");
            lblHighscore3.setHorizontalAlignment(SwingConstants.TRAILING);
            lblHighscore3.setForeground(new Color(255, 255, 0));
            lblHighscore3.setFont(new Font("Cambria", Font.BOLD, 20));
            lblHighscore3.setBounds(433, 18, 134, 33);
            contentPane.add(lblHighscore3);

            btn3Start = new JButton("Start");
            btn3Start.setBackground(Color.WHITE);
            btn3Start.setFont(new Font("Cambria", Font.BOLD, 20));
            btn3Start.setBounds(40, 60, 110,35);
            contentPane.add(btn3Start);
        
            setContentPane(contentPane);     
        }
        
        //action button to next level 
        public class TSH1 implements ActionListener{
            public void actionPerformed(ActionEvent event){
                createGamelv1();
                clearBoard1();
                initEvents1();
                loadHighscore1();
            }
        }
        public class TSH2 implements ActionListener{
            public void actionPerformed(ActionEvent event){
                createGamelv2();
                clearBoard2();
                initEvents2();
                loadHighscore2();
            }
        }
        public class TSH3 implements ActionListener{
            public void actionPerformed(ActionEvent event){
                createGamelv3();
                clearBoard3();
                initEvents3();
                loadHighscore3();
            }
        }
        //1
        private void clearBoard1(){
            for(int i = 0; i < 9; i++){
                holes1[i].setIcon(loadImage("res/hole.png"));
                board1[i] = 0;
            }
        }
        private void genRandMole1(){
            Random rnd1 = new Random(System.currentTimeMillis()); //seeding random with current time
            int moleID1 = rnd1.nextInt(9);
                board1[moleID1] = 1;
                holes1[moleID1].setIcon(loadImage("res/moleOut4.png"));
        }
        //2
        private void clearBoard2(){
            for(int i = 0; i < 12; i++){
                holes2[i].setIcon(loadImage("res/hole.png"));
                board2[i] = 0;
            }
        }
        private void genRandMole2(){
            Random rnd2 = new Random(System.currentTimeMillis()); //seeding random with current time
            int moleID2 = rnd2.nextInt(12);
                board2[moleID2] = 1;
                holes2[moleID2].setIcon(loadImage("res/moleOut4.png"));
        }
        //3
        private void clearBoard3(){
            for(int i = 0; i < 16; i++){
                holes3[i].setIcon(loadImage("res/hole.png"));
                board3[i] = 0;
            }
        }
        private void genRandMole3(){
            Random rnd3 = new Random(System.currentTimeMillis()); //seeding random with current time
            int moleID3 = rnd3.nextInt(16);
                board3[moleID3] = 1;
                holes3[moleID3].setIcon(loadImage("res/moleOut4.png"));
        }

        
        private ImageIcon loadImage(String path){ //image
            Image image = new ImageIcon(this.getClass().getResource(path)).getImage();
            Image scaledImage = image.getScaledInstance(132, 132,  java.awt.Image.SCALE_SMOOTH);
            return new ImageIcon(scaledImage);
        }
    public static void main(String[] args) { //main 
        Game4 frame = new Game4();
        frame.setVisible(true);
    }  
}
