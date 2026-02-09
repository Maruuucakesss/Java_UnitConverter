package unit_converter;

import java.awt.Color;
import java.awt.Font;
import java.awt.Image;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JComboBox;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JLayeredPane;
import javax.swing.JTextField;

public class converter extends JFrame implements ActionListener {
	
	ImageIcon bg = new ImageIcon(new ImageIcon("bg.jpg").getImage().getScaledInstance(500, 500, Image.SCALE_SMOOTH));
	ImageIcon icon = new ImageIcon(new ImageIcon("icon.jpg").getImage().getScaledInstance(500, 500, Image.SCALE_SMOOTH));
	ImageIcon logo = new ImageIcon(new ImageIcon("logo.png").getImage().getScaledInstance(137, 137, Image.SCALE_SMOOTH));
	ImageIcon name = new ImageIcon(new ImageIcon("name.png").getImage().getScaledInstance(300, 60, Image.SCALE_SMOOTH));
	ImageIcon arrow = new ImageIcon(new ImageIcon("arow.png").getImage().getScaledInstance(50, 50, Image.SCALE_SMOOTH));
	
	JLabel backG = new JLabel();
	JLabel log = new JLabel();
	JLabel title = new JLabel();
	JLabel arow = new JLabel();
	JLabel txtInput = new JLabel();
	JLabel txtUnit = new JLabel();
	JLabel txtOutput = new JLabel();
	
	JButton cle = new JButton();
	JButton conv = new JButton();
	
	JTextField inpot = new JTextField();
	JTextField awtpot = new JTextField();
	
	JComboBox unit1 = new JComboBox();
	JComboBox unit2 = new JComboBox();
	JComboBox unit3 = new JComboBox();
	
	JLayeredPane leyers = new JLayeredPane();
	
	converter(){
		
		//GUI
		this.setSize(500,500);
		this.setVisible(true);
		this.setLocationRelativeTo(null);
		this.setDefaultCloseOperation(EXIT_ON_CLOSE);
		this.setResizable(false);
		this.setLayout(null);
		this.setTitle("Unit Converter");
		this.setIconImage(icon.getImage());
		
		this.add(leyers);
		this.add(backG);
		this.add(log);
		this.add(title);
		this.add(arow);
		this.add(unit1);
		this.add(unit2);
		this.add(unit3);
		this.add(inpot);
		this.add(awtpot);
		this.add(cle);
		this.add(conv);
		this.add(txtInput);
		this.add(txtOutput);
		this.add(txtUnit);
		
		//LAYERS
		leyers.setBounds(0, 0, 500, 500);
		leyers.add(backG, Integer.valueOf(0));
		leyers.add(log, Integer.valueOf(1));
		leyers.add(unit1, Integer.valueOf(1));
		leyers.add(unit2, Integer.valueOf(1));
		leyers.add(unit3, Integer.valueOf(1));
		leyers.add(inpot, Integer.valueOf(1));
		leyers.add(awtpot, Integer.valueOf(1));
		leyers.add(cle, Integer.valueOf(1));
		leyers.add(conv, Integer.valueOf(1));
		leyers.add(title, Integer.valueOf(1));
		leyers.add(arow, Integer.valueOf(1));
		leyers.add(txtInput, Integer.valueOf(2));
		leyers.add(txtUnit, Integer.valueOf(2));
		leyers.add(txtOutput, Integer.valueOf(2));
		
		//BACKGROUND
		backG.setIcon(bg);
		backG.setBounds(0, 0, 500, 500);
		
		//LOGO
		log.setIcon(logo);
		log.setBounds(25,15,137,137);
		
		//TITLE (JVerter)
		title.setIcon(name);
		title.setBounds(150,50,300,60);
		
		//ARROW
		arow.setIcon(arrow);
		arow.setBounds(220,240,50,50);
		
		//UNIT 1-3
		unit1.setBounds(50,185,150,40);
		unit1.addItem("Length");
		unit1.addItem("Mass");
		unit1.addItem("Temperature");
		unit1.addItem("Time");
		unit1.addItem("Volume");
		unit1.addActionListener(new ActionListener() {
			
				//-----UNITS OPTIONS-----

			@Override
			public void actionPerformed(ActionEvent e) {
				if(unit1.getSelectedItem().equals("Length")) {
					
					unit2.addItem("Inches");
					unit2.addItem("Foot");
					unit2.addItem("Yard");
					unit2.addItem("Mile");
					unit2.addItem("Millimeter");
					unit2.addItem("Centimeter");
					unit2.addItem("Meter");
					unit2.addItem("kilometer");
					
					unit3.addItem("Inches");
					unit3.addItem("Foot");
					unit3.addItem("Yard");
					unit3.addItem("Mile");
					unit3.addItem("Millimeter");
					unit3.addItem("Centimeter");
					unit3.addItem("Meter");
					unit3.addItem("Kilometer");
				}else if(unit1.getSelectedItem().equals("Mass")) {
					
					unit2.addItem("Ounce");
					unit2.addItem("Pound");
					unit2.addItem("Stone");
					unit2.addItem("Milligram");
					unit2.addItem("Gram");
					unit2.addItem("Kilogram");
					unit2.addItem("Tonne");
					
					unit3.addItem("Ounce");
					unit3.addItem("Pound");
					unit3.addItem("Stone");
					unit3.addItem("Milligram");
					unit3.addItem("Gram");
					unit3.addItem("Kilogram");
					unit3.addItem("Tonne");
					
				}else if(unit1.getSelectedItem().equals("Temperature")) {
					
					unit2.addItem("Degree Celcius");
					unit2.addItem("Fahrenheit");
					unit2.addItem("Kelvin");
					
					unit3.addItem("Degree Celcius");
					unit3.addItem("Fahrenheit");
					unit3.addItem("Kelvin");
					
				}else if(unit1.getSelectedItem().equals("Time")) {
					
					unit2.addItem("Second");
					unit2.addItem("Minute");
					unit2.addItem("Hour");
					unit2.addItem("Day");
					unit2.addItem("Week");
					unit2.addItem("Month");
					unit2.addItem("Year");
					
					unit3.addItem("Second");
					unit3.addItem("Minute");
					unit3.addItem("Hour");
					unit3.addItem("Day");
					unit3.addItem("Week");
					unit3.addItem("Month");
					unit3.addItem("Year");
					
				}else if(unit1.getSelectedItem().equals("Volume")) {
					
					unit2.addItem("Cubic Inch");
					unit2.addItem("Cubic Foot");
					unit2.addItem("Cubic Meter");
					unit2.addItem("Milliliter");
					unit2.addItem("Liter");
					unit2.addItem("US Liquid Gallon");
					
					unit3.addItem("Cubic Inch");
					unit3.addItem("Cubic Foot");
					unit3.addItem("Cubic Meter");
					unit3.addItem("Milliliter");
					unit3.addItem("Liter");
					unit3.addItem("US Liquid Gallon");
					
				}
				
			}});
		
		//UNIT 1 TEXT
		txtInput.setText("Select Unit:");
		txtInput.setBounds(50,127,100,100);
		txtInput.setForeground(new Color(0xFFFFFF));
		txtInput.setFont(new Font("Arial Black",Font.PLAIN,10));
		
		unit2.setBounds(50,245,150,40);
		unit3.setBounds(290,245,150,40);
		
		//INPUT
		inpot.setBounds(290,185,150,40);
		
		//INPUT TEXT
		txtUnit.setText("Unit to Convert:");
		txtUnit.setBounds(290,127,100,100);
		txtUnit.setForeground(new Color(0xFFFFFF));
		txtUnit.setFont(new Font("Arial Black",Font.PLAIN,10));
		
		//OUTPUT
		awtpot.setBounds(100,330,300,40);
		awtpot.setEditable(false);
		
		//OUTPUT TEXT
		txtOutput.setText("OUTPUT:");
		txtOutput.setBounds(190,260,100,100);
		txtOutput.setForeground(new Color(0xFF0000));
		txtOutput.setFont(new Font("Arial Black",Font.PLAIN,20));
		
		//CLEAR
		cle.setBounds(56,390,110,40);
		cle.setText("CLEAR");
		cle.setFocusable(false);
		cle.addActionListener(this);
		
		//CONVERT
		conv.setBounds(324,390,110,40);
		conv.setText("CONVERT");
		conv.setFocusable(false);
		conv.addActionListener(new ActionListener() {
			
				//-----CONVERT-----

			@Override
			public void actionPerformed(ActionEvent e) {
				double unit = Double.parseDouble(inpot.getText());
				double convertUnit = 0;
				
				
				//-----LENGTH-----
				
				if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit;
					//awtpot.setText(String.valueOf(unit));
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit/12;
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit/36;
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/63360;
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit*25.4;
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit*2.54;
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit/39.37;
					
				}else if(unit2.getSelectedItem().equals("Inches") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit/39370.000;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit*12;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit/3;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/5280;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit*304.8;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit*30.48;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit/3.281;
					
				}else if(unit2.getSelectedItem().equals("Foot") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit/3281;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit*36;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit*3;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/1760;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit*914.4;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit*91.44;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit/1.094;
					
				}else if(unit2.getSelectedItem().equals("Yard") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit/1094;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit*63360;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit*5280;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit*1760;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit*1609344;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit*160934;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit*1609.34;
					
				}else if(unit2.getSelectedItem().equals("Mile") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit*1.60934;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit/25.4;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit/304.8;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit/914.4;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/1609344;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit/10;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit/1000;
					
				}else if(unit2.getSelectedItem().equals("Millimeter") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit/1000000;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit/2.54;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit/30.48;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit/91.44;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/160900;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit*10;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit/100;
					
				}else if(unit2.getSelectedItem().equals("Centimeter") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit/100000;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit*39.37;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit*3.281;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit*1.094;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/1609;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit/1000;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit*100;
					
				}else if(unit2.getSelectedItem().equals("Meter") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit/1000;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Kilometer")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Inches")) {
					convertUnit = unit*39370;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Foot")) {
					convertUnit = unit*3281;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Yard")) {
					convertUnit = unit*1094;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Mile")) {
					convertUnit = unit/1.609;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Millimeter")) {
					convertUnit = unit*100000;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Centimeter")) {
					convertUnit = unit*100000;
					
				}else if(unit2.getSelectedItem().equals("Kilometer") && unit3.getSelectedItem().equals("Meter")) {
					convertUnit = unit*1000;
					
				}
				
				//-----MASS-----
				
				if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit/16;
					
				}else if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit/224;
					
				}else if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit*28350;
					
				}else if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit*28.35;
					
				}else if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit/35.270;
					
				}else if(unit2.getSelectedItem().equals("Ounce") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit/35270;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit*16;
					
				}else if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit/14;
					
				}else if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit*453600;
					
				}else if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit*453.6;
					
				}else if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit/2.205;
					
				}else if(unit2.getSelectedItem().equals("Pound") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit/2205;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit*224;
					
				}else if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit*14;
					
				}else if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit*6350293.18;
					
				}else if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit*6350;
					
				}else if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit*6.35;
					
				}else if(unit2.getSelectedItem().equals("Stone") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit/157.5;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit/28350;
					
				}else if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit/453600;
					
				}else if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit/6350.29;
					
				}else if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit/1000;
					
				}else if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit/0.000001;
					
				}else if(unit2.getSelectedItem().equals("Milligram") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit/907184.740;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit/28.35;
					
				}else if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit/453.6;
					
				}else if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit/6350;
					
				}else if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit*1000;
					
				}else if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit/1000;
					
				}else if(unit2.getSelectedItem().equals("Gram") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit/1000000;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit*35.27396;
					
				}else if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit*2.20462;
					
				}else if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit*0.15747;
					
				}else if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit*1000000;
					
				}else if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit*1000;
					
				}else if(unit2.getSelectedItem().equals("Kilo") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit*0.001;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Tonne")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Ounce")) {
					convertUnit = unit*35273.96;
					
				}else if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Pound")) {
					convertUnit = unit*2204.62;
					
				}else if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Stone")) {
					convertUnit = unit*157.473;
					
				}else if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Milligram")) {
					convertUnit = unit*1000000000;
					
				}else if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Gram")) {
					convertUnit = unit*1000000;
					
				}else if(unit2.getSelectedItem().equals("Tonne") && unit3.getSelectedItem().equals("Kilo")) {
					convertUnit = unit*1000;
					
				}
				
				//-----TEMPERATURE-----
				
				if(unit2.getSelectedItem().equals("Degree Celcius") && unit3.getSelectedItem().equals("Degree Celcius")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Degree Celcius") && unit3.getSelectedItem().equals("Fahrenheit")) {
					convertUnit = unit*1.8+32;
					
				}else if(unit2.getSelectedItem().equals("Degree Celcius") && unit3.getSelectedItem().equals("Kelvin")) {
					convertUnit = unit+273.15;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Fahrenheit") && unit3.getSelectedItem().equals("Fahrenheit")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Fahrenheit") && unit3.getSelectedItem().equals("Degree Celcius")) {
					convertUnit = unit-32*0.556;
					
				}else if(unit2.getSelectedItem().equals("Fahrenheit") && unit3.getSelectedItem().equals("Kelvin")) {
					convertUnit = unit-32*0.556+273.15;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Kelvin") && unit3.getSelectedItem().equals("Kelvin")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Kelvin") && unit3.getSelectedItem().equals("Degree Celcius")) {
					convertUnit = unit-273.15;
					
				}else if(unit2.getSelectedItem().equals("Kelvin") && unit3.getSelectedItem().equals("Fahrenheit")) {
					convertUnit = unit-273.15*1.8+32;
					
				}
				
				//-----TIME-----
				
				if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit/60;
					
				}else if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit/3600;
					
				}else if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit/86400;
					
				}else if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit/604800;
					
				}else if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit/2629746;
					
				}else if(unit2.getSelectedItem().equals("Second") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit/31556952;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit*60;
					
				}else if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit/60;
					
				}else if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit/1440;
					
				}else if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit/10080;
					
				}else if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit/43800;
					
				}else if(unit2.getSelectedItem().equals("Minute") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit/525600;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit*3600;
					
				}else if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit*60;
					
				}else if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit/24;
					
				}else if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit/168;
					
				}else if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit/730;
					
				}else if(unit2.getSelectedItem().equals("Hour") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit/8760;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit*86400;
					
				}else if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit*1440;
					
				}else if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit*24;
					
				}else if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit/7;
					
				}else if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit/30.417;
					
				}else if(unit2.getSelectedItem().equals("Day") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit/365;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit*604800;
					
				}else if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit*10080;
					
				}else if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit*168;
					
				}else if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit*7;
					
				}else if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit/4.345;
					
				}else if(unit2.getSelectedItem().equals("Week") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit/52.143;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit*2628288;
					
				}else if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit*43800;
					
				}else if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit*730;
					
				}else if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit*30.417;
					
				}else if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit*4.345;
					
				}else if(unit2.getSelectedItem().equals("Month") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit/12;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Year")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Second")) {
					convertUnit = unit*31556952;
					
				}else if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Minute")) {
					convertUnit = unit*525600;
					
				}else if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Hour")) {
					convertUnit = unit*8760;
					
				}else if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Day")) {
					convertUnit = unit*365;
					
				}else if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Week")) {
					convertUnit = unit*52.143;
					
				}else if(unit2.getSelectedItem().equals("Year") && unit3.getSelectedItem().equals("Month")) {
					convertUnit = unit*12;
					
				}
				
				//-----VOLUME-----
				
				if(unit2.getSelectedItem().equals("Cubic Inch") && unit3.getSelectedItem().equals("Cubic Inch")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Cubic Inch") && unit3.getSelectedItem().equals("Cubic Foot")) {
					convertUnit = unit/1728;
					
				}else if(unit2.getSelectedItem().equals("Cubic Inch") && unit3.getSelectedItem().equals("Cubic Meter")) {
					convertUnit = unit/61020;
					
				}else if(unit2.getSelectedItem().equals("Cubic Inch") && unit3.getSelectedItem().equals("Milliliter")) {
					convertUnit = unit*16.387;
					
				}else if(unit2.getSelectedItem().equals("Cubic Inch") && unit3.getSelectedItem().equals("Liter")) {
					convertUnit = unit/61.024;
					
				}else if(unit2.getSelectedItem().equals("Cubic Inch") && unit3.getSelectedItem().equals("US Liquid Gallon")) {
					convertUnit = unit/231;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Cubic Foot") && unit3.getSelectedItem().equals("Cubic Foot")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Cubic Foot") && unit3.getSelectedItem().equals("Cubic Inch")) {
					convertUnit = unit*1728;
					
				}else if(unit2.getSelectedItem().equals("Cubic Foot") && unit3.getSelectedItem().equals("Cubic Meter")) {
					convertUnit = unit/35.315;
					
				}else if(unit2.getSelectedItem().equals("Cubic Foot") && unit3.getSelectedItem().equals("Milliliter")) {
					convertUnit = unit*28320;
					
				}else if(unit2.getSelectedItem().equals("Cubic Foot") && unit3.getSelectedItem().equals("Liter")) {
					convertUnit = unit*28.317;
					
				}else if(unit2.getSelectedItem().equals("Cubic Foot") && unit3.getSelectedItem().equals("US Liquid Gallon")) {
					convertUnit = unit*7.481;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Cubic Meter") && unit3.getSelectedItem().equals("Cubic Meter")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Cubic Meter") && unit3.getSelectedItem().equals("Cubic Inch")) {
					convertUnit = unit*61023.7441;
					
				}else if(unit2.getSelectedItem().equals("Cubic Meter") && unit3.getSelectedItem().equals("Cubic Foot")) {
					convertUnit = unit*35.3147;
					
				}else if(unit2.getSelectedItem().equals("Cubic Meter") && unit3.getSelectedItem().equals("Milliliter")) {
					convertUnit = unit*1000000;
					
				}else if(unit2.getSelectedItem().equals("Cubic Meter") && unit3.getSelectedItem().equals("Liter")) {
					convertUnit = unit*1000;
					
				}else if(unit2.getSelectedItem().equals("Cubic Meter") && unit3.getSelectedItem().equals("US Liquid Gallon")) {
					convertUnit = unit*264.172;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Milliliter") && unit3.getSelectedItem().equals("Milliliter")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Milliliter") && unit3.getSelectedItem().equals("Cubic Inch")) {
					convertUnit = unit*0.0610237;
					
				}else if(unit2.getSelectedItem().equals("Milliliter") && unit3.getSelectedItem().equals("Cubic Foot")) {
					convertUnit = unit*3.5314700000;
					
				}else if(unit2.getSelectedItem().equals("Milliliter") && unit3.getSelectedItem().equals("Cubic Meter")) {
					convertUnit = unit*10000000;
					
				}else if(unit2.getSelectedItem().equals("Milliliter") && unit3.getSelectedItem().equals("Liter")) {
					convertUnit = unit*0.001;
					
				}else if(unit2.getSelectedItem().equals("Milliliter") && unit3.getSelectedItem().equals("US Liquid Gallon")) {
					convertUnit = unit*0.000264172;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("Liter") && unit3.getSelectedItem().equals("Liter")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("Liter") && unit3.getSelectedItem().equals("Cubic Inch")) {
					convertUnit = unit*61.0237;
					
				}else if(unit2.getSelectedItem().equals("Liter") && unit3.getSelectedItem().equals("Cubic Foot")) {
					convertUnit = unit*0.0353147;
					
				}else if(unit2.getSelectedItem().equals("Liter") && unit3.getSelectedItem().equals("Cubic Meter")) {
					convertUnit = unit*0.001;
					
				}else if(unit2.getSelectedItem().equals("Liter") && unit3.getSelectedItem().equals("Milliliter")) {
					convertUnit = unit*1000;
					
				}else if(unit2.getSelectedItem().equals("Liter") && unit3.getSelectedItem().equals("US Liquid Gallon")) {
					convertUnit = unit*0.264172;
					
				}
				
				
				
				if(unit2.getSelectedItem().equals("US Liquid Gallon") && unit3.getSelectedItem().equals("US Liquid Gallon")) {
					convertUnit = unit;
					
				}else if(unit2.getSelectedItem().equals("US Liquid Gallon") && unit3.getSelectedItem().equals("Cubic Inch")) {
					convertUnit = unit*231;
					
				}else if(unit2.getSelectedItem().equals("US Liquid Gallon") && unit3.getSelectedItem().equals("Cubic Foot")) {
					convertUnit = unit*0.133681;
					
				}else if(unit2.getSelectedItem().equals("US Liquid Gallon") && unit3.getSelectedItem().equals("Cubic Meter")) {
					convertUnit = unit*0.00378541;
					
				}else if(unit2.getSelectedItem().equals("US Liquid Gallon") && unit3.getSelectedItem().equals("Milliliter")) {
					convertUnit = unit*3787.41;
					
				}else if(unit2.getSelectedItem().equals("US Liquid Gallon") && unit3.getSelectedItem().equals("Liter")) {
					convertUnit = unit*3.78541;
					
				}
				
				awtpot.setText(String.valueOf(convertUnit) + unit3.getSelectedItem());
			}});
		
	}

	
				//-----CLEAR-----
	
	@Override
	public void actionPerformed(ActionEvent e) {
		inpot.setText("");
		awtpot.setText("");
		unit2.removeAllItems();
		unit3.removeAllItems();
	}	
}
