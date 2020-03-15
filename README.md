# BasicCalculator
MyFirstBasicCalculatorJAVA
package calcy;

import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JTextField;
import java.awt.Color;
import java.awt.Font;
import javax.swing.JButton;
import javax.swing.UIManager;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.SwingConstants;
import javax.swing.JLabel;
import javax.swing.JRadioButton;

public class CalciWindow {

	private JFrame frame;
	private JTextField txtYourAnswerIs;
	private JRadioButton buttonON;
	private JRadioButton buttonOFF;
	
	double firstNumber;
	double secondNumber;
	double result;
	String operations;
	String answer;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					CalciWindow window = new CalciWindow();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the application.
	 */
	public CalciWindow() {
		initialize();
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		frame = new JFrame();
		frame.getContentPane().setFont(new Font("Yu Gothic Medium", Font.PLAIN, 14));
		frame.getContentPane().setForeground(new Color(255, 215, 0));
		frame.getContentPane().setBackground(Color.GRAY);
		frame.setBounds(100, 100, 320, 300);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(null);
		
		txtYourAnswerIs = new JTextField();
		txtYourAnswerIs.setHorizontalAlignment(SwingConstants.CENTER);
		txtYourAnswerIs.setBackground(new Color(152, 251, 152));
		txtYourAnswerIs.setBounds(10, 11, 290, 25);
		frame.getContentPane().add(txtYourAnswerIs);
		txtYourAnswerIs.setColumns(10);
		
		JButton CEbutton = new JButton("CE");
		CEbutton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			txtYourAnswerIs.setText(null);
			}
		});
		CEbutton.setForeground(new Color(0, 0, 0));
		CEbutton.setFont(new Font("Tahoma", Font.BOLD, 18));
		CEbutton.setBackground(new Color(95, 158, 160));
		CEbutton.setBounds(210, 189, 90, 25);
		frame.getContentPane().add(CEbutton);
		
		JButton buttonRe = new JButton("<-");
		buttonRe.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			String backSpace=null;
			
			if(txtYourAnswerIs.getText().length()>0) {
				StringBuilder newSB=new StringBuilder(txtYourAnswerIs.getText());
				newSB.deleteCharAt(txtYourAnswerIs.getText().length()-1);
				backSpace=newSB.toString();
				txtYourAnswerIs.setText(backSpace);
			}
			}
		});
		buttonRe.setForeground(new Color(0, 0, 0));
		buttonRe.setFont(new Font("Tahoma", Font.BOLD, 18));
		buttonRe.setBackground(new Color(95, 158, 160));
		buttonRe.setBounds(210, 225, 90, 25);
		frame.getContentPane().add(buttonRe);
		
		JButton plus = new JButton("+");
		plus.setFont(new Font("Tahoma", Font.PLAIN, 8));
		plus.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			firstNumber=Double.parseDouble(txtYourAnswerIs.getText());
			txtYourAnswerIs.setText("");
			operations="+";
			}
		});
		plus.setForeground(new Color(0, 0, 0));
		plus.setBackground(new Color(255, 215, 0));
		plus.setBounds(10, 45, 40, 40);
		frame.getContentPane().add(plus);
		
		JButton minus = new JButton("-");
		minus.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				firstNumber=Double.parseDouble(txtYourAnswerIs.getText());
				txtYourAnswerIs.setText("");
				operations="-";
			}
		});
		minus.setForeground(Color.BLACK);
		minus.setFont(new Font("Tahoma", Font.BOLD, 12));
		minus.setBackground(new Color(255, 215, 0));
		minus.setBounds(60, 45, 40, 40);
		frame.getContentPane().add(minus);
		
		JButton multyplication = new JButton("*");
		multyplication.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				firstNumber=Double.parseDouble(txtYourAnswerIs.getText());
				txtYourAnswerIs.setText("");
				operations="*";
			}
		});
		multyplication.setForeground(Color.BLACK);
		multyplication.setFont(new Font("Tahoma", Font.BOLD, 10));
		multyplication.setBackground(new Color(255, 215, 0));
		multyplication.setBounds(110, 45, 40, 40);
		frame.getContentPane().add(multyplication);
		
		JButton divide = new JButton("/");
		divide.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				firstNumber=Double.parseDouble(txtYourAnswerIs.getText());
				txtYourAnswerIs.setText("");
				operations="/";
			}
		});
		divide.setForeground(Color.BLACK);
		divide.setFont(new Font("Tahoma", Font.BOLD, 10));
		divide.setBackground(new Color(255, 215, 0));
		divide.setBounds(160, 45, 40, 40);
		frame.getContentPane().add(divide);
		
		JButton phactoriel = new JButton("n!");
		phactoriel.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				firstNumber=Integer.parseInt(txtYourAnswerIs.getText());
			       
			       txtYourAnswerIs.setText("");
					operations="n!";
			}
		});
		phactoriel.setForeground(Color.BLACK);
		phactoriel.setFont(new Font("Tahoma", Font.BOLD, 6));
		phactoriel.setBackground(new Color(255, 215, 0));
		phactoriel.setBounds(210, 45, 40, 40);
		frame.getContentPane().add(phactoriel);
		
		JButton one = new JButton("1");/////////////////////////////////ONE
		one.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+one.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		
		one.setBackground(new Color(95, 158, 160));
		one.setFont(new Font("Tahoma", Font.BOLD, 14));
		one.setBounds(10, 106, 60, 20);
		frame.getContentPane().add(one);
		
		JButton three = new JButton("3");/////////////////////////////////THREE
		three.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+three.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		three.setBackground(new Color(95, 158, 160));
		three.setFont(new Font("Tahoma", Font.BOLD, 14));
		three.setBounds(140, 106, 60, 20);
		frame.getContentPane().add(three);
		
		JButton two = new JButton("2");/////////////////////////////////TWO
		two.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+two.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		two.setBackground(new Color(95, 158, 160));
		two.setFont(new Font("Tahoma", Font.BOLD, 14));
		two.setBounds(80, 106, 50, 20);
		frame.getContentPane().add(two);
		
		JButton six = new JButton("6");/////////////////////////////////SIX
		six.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+six.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		six.setBackground(new Color(95, 158, 160));
		six.setFont(new Font("Tahoma", Font.BOLD, 14));
		six.setBounds(140, 137, 60, 20);
		frame.getContentPane().add(six);
		
		JButton five = new JButton("5");/////////////////////////////////FIVE
		five.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+five.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		five.setFont(new Font("Tahoma", Font.BOLD, 14));
		five.setBackground(new Color(95, 158, 160));
		five.setBounds(80, 137, 50, 20);
		frame.getContentPane().add(five);
		
		JButton four = new JButton("4");/////////////////////////////////FOUR
		four.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+four.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		four.setBackground(new Color(95, 158, 160));
		four.setFont(new Font("Tahoma", Font.BOLD, 14));
		four.setBounds(10, 137, 60, 20);
		frame.getContentPane().add(four);
		
		JButton nine = new JButton("9");/////////////////////////////////NINE
		nine.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+nine.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		nine.setFont(new Font("Tahoma", Font.BOLD, 14));
		nine.setBackground(new Color(95, 158, 160));
		nine.setBounds(140, 168, 60, 20);
		frame.getContentPane().add(nine);
		
		JButton eight = new JButton("8");/////////////////////////////////EIGHT
		eight.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+eight.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		eight.setBackground(new Color(95, 158, 160));
		eight.setFont(new Font("Tahoma", Font.BOLD, 14));
		eight.setBounds(80, 168, 50, 20);
		frame.getContentPane().add(eight);
		
		JButton seven = new JButton("7");/////////////////////////////////SEVEN
		seven.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+seven.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		seven.setFont(new Font("Tahoma", Font.BOLD, 14));
		seven.setBackground(new Color(95, 158, 160));
		seven.setBounds(10, 168, 60, 20);
		frame.getContentPane().add(seven);
		
		JButton decimal = new JButton(".");
		decimal.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				if(! txtYourAnswerIs.getText().contains(".")) {
					txtYourAnswerIs.setText(txtYourAnswerIs.getText() + decimal.getText());
		          }
			}
	
		});
		
		decimal.setFont(new Font("Tahoma", Font.BOLD, 18));
		decimal.setBackground(new Color(95, 158, 160));
		decimal.setBounds(10, 199, 60, 20);
		frame.getContentPane().add(decimal);
		
		JButton zero = new JButton("0");/////////////////////////////////ZERO
		zero.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			
				String EnterNumber=txtYourAnswerIs.getText()+zero.getText();
				txtYourAnswerIs.setText(EnterNumber);
			}
		});
		zero.setFont(new Font("Tahoma", Font.BOLD, 14));
		zero.setBackground(new Color(95, 158, 160));
		zero.setBounds(80, 199, 50, 20);
		frame.getContentPane().add(zero);
		
		JButton equals = new JButton("=");
		equals.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			String answer;
			
			secondNumber=Double.parseDouble(txtYourAnswerIs.getText());
			if(operations=="+") {
				result=firstNumber+secondNumber;
				answer=String.format("%.4f", result);
				txtYourAnswerIs.setText(answer);
			}else if(operations=="-") {
				result=firstNumber-secondNumber;
				answer=String.format("%.4f", result);
				txtYourAnswerIs.setText(answer);
			}else if(operations=="*") {
				result=firstNumber*secondNumber;
				answer=String.format("%.4f", result);
				txtYourAnswerIs.setText(answer);
			}else if(operations=="/") {
				result=firstNumber/secondNumber;
				answer=String.format("%.4f", result);
				txtYourAnswerIs.setText(answer);
			}else if(operations=="%") {
				
				result=((secondNumber/firstNumber));
				result=100/result;/////////////////////////////////////////%%%%
				answer=String.format("%.4f", result);
				txtYourAnswerIs.setText(answer);
			}else if(operations=="n!") {
				int numberP=1;
			       for(int i=(int) firstNumber;i>=1;i--){
			           numberP=numberP*i;
			       }
			       secondNumber=(double)numberP;
			        result=(firstNumber*0.0)+secondNumber;
				result*=1.0;
				answer=String.format("%.4f", result);
				txtYourAnswerIs.setText(answer);
				
			}
			}
			
		});
		equals.setFont(new Font("Tahoma", Font.BOLD, 18));
		equals.setBackground(new Color(95, 158, 160));
		equals.setBounds(10, 230, 190, 20);
		frame.getContentPane().add(equals);
		
		JButton plusNminus = new JButton("+/-");
		plusNminus.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			double ops=Double.parseDouble(String.valueOf(txtYourAnswerIs.getText()));
			ops=ops*(-1);
			txtYourAnswerIs.setText(String.valueOf(ops));
			}
		});
		plusNminus.setFont(new Font("Tahoma", Font.BOLD, 14));
		plusNminus.setBackground(new Color(95, 158, 160));
		plusNminus.setBounds(140, 199, 60, 20);
		frame.getContentPane().add(plusNminus);
		
		JButton percentage = new JButton("%");
		percentage.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				firstNumber=Double.parseDouble(txtYourAnswerIs.getText());
				txtYourAnswerIs.setText("");
				operations="%";
			}
		});
		percentage.setForeground(Color.BLACK);
		percentage.setFont(new Font("Tahoma", Font.PLAIN, 6));
		percentage.setBackground(new Color(255, 215, 0));
		percentage.setBounds(260, 47, 40, 38);
		frame.getContentPane().add(percentage);
		
		JLabel lblNewLabel = new JLabel("Basic Calculator");
		lblNewLabel.setFont(new Font("Tahoma", Font.BOLD, 10));
		lblNewLabel.setBackground(new Color(0, 0, 0));
		lblNewLabel.setForeground(new Color(152, 251, 152));
		lblNewLabel.setBounds(210, 170, 90, 20);
		frame.getContentPane().add(lblNewLabel);
		
		JRadioButton buttonON = new JRadioButton("ON");
		buttonON.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			if(buttonON.isSelected()) {
				buttonOFF.setSelected(false);
				buttonON.setSelected(true);
			
			}
			}
		});
		buttonON.setForeground(new Color(127, 255, 212));
		buttonON.setBackground(new Color(192, 192, 192));
		buttonON.setSelected(true);
		buttonON.setFont(new Font("Tahoma", Font.BOLD, 12));
		buttonON.setBounds(210, 105, 50, 25);
		frame.getContentPane().add(buttonON);
		
		JRadioButton buttonOFF = new JRadioButton("OFF");
		buttonOFF.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			if(buttonOFF.isSelected()) {
				buttonON.setSelected(false);
				buttonOFF.setSelected(true);
			}
			}
		});
		buttonOFF.setForeground(new Color(127, 255, 212));
		buttonOFF.setBackground(new Color(192, 192, 192));
		buttonOFF.setFont(new Font("Tahoma", Font.BOLD, 12));
		buttonOFF.setBounds(210, 138, 50, 25);
		frame.getContentPane().add(buttonOFF);
	}
}
