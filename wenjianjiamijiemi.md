import java.awt.*;
import java.awt.event.*;
import java.io.*;
import javax.swing.*;
public class Swallow extends Frame{
	JLabel la1;
	JButton bt1, bt2, bt3;
	JTextField tf1;
	JTextArea nr;
	public static void main(String args[]){
		new Swallow();
	}
	public Swallow(){
		this.setTitle("Java加密和解密");
		JPanel p1 = new JPanel();
		la1 = new JLabel("选择文件路径");
		tf1 = new JTextField(20);
		bt1 = new JButton("浏览...");
		bt1.addActionListener(new myjianting1());
		p1.add(la1);
		p1.add(tf1);
		p1.add(bt1);
		add(p1, BorderLayout.NORTH);
		nr = new JTextArea();
		add(nr, BorderLayout.CENTER);
		bt2 = 
		setLocation(200, 200);
		setVisible(true);
		this.addWindowListener(new myclosing());
	}
	class myclosing extends WindowAdapter{
		public void windowClosing(WindowEvent e){
			setVisible(false);
			System.exit(0);
		}
	}
	class myjianting1 implements ActionListener{
		public void actionPerformed(ActionEvent e){
			JFileChooser fc = new JFileChooser(); // 实例化文件选择器
			fc.setFileSelectionMode(JFileChooser.FILES_AND_DIRECTORIES); // 设置文件选择模式,此处为文件和目录均可
			if (fc.showOpenDialog(Swallow.this) == JFileChooser.APPROVE_OPTION){ // 弹出文件选择器,并判断是否点击了打开按钮
				String fileName = fc.getSelectedFile().getAbsolutePath(); // 得到选择文件或目录的绝对路径
				tf1.setText(fileName);
			}
		}
	}
	class myjianting2 implements ActionListener{
		public void actionPerformed(ActionEvent event){
			swallow1 sw = new swallow1();
			try{
				sw.open(); 
				sw.password();
				sw.showFileContent();
			}
			catch(IOException e){
				nr.setText("文件不能打开！");	
			}
		}
	}
	class myjianting3 implements ActionListener{
		public void actionPerformed(ActionEvent event){
			swallow1 sw = new swallow1();
			try{
				sw.open(); 
				sw.password();
				sw.showFileContent();
			}
			catch (IOException e){
				nr.setText("文件解密有误！");
			}
		}
	}
	public class swallow1{
		private File file;
		byte[] buf;
		RandomAccessFile raf,raf1;
		Public
		}
	}
}
