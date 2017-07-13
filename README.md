# java
package com.atguigu.com;

import java.util.Scanner;
import java.util.Vector;

/*
 * 利用Vector代替数组处理：从键盘读入学生成绩（以负数代表输入结束），找出最高分，并输出学生成绩等级。
       提示：数组一旦创建，长度就固定不变，所以在创建数组前就需要知道它的长度。而向量类java.util.Vector可以根据需要动态伸缩。
       创建Vector对象：Vector v=new Vector();
       给向量添加元素：v.addElement(obj);   //obj必须是对象
      取出向量中的元素：Object  obj=v.elementAt(0);
      注意第一个元素的下标是0，返回值是Object类型的。
      计算向量的长度：v.size();
      若与最高分相差10分内：A等；20分内：B等；30分内：C等；其它：D等

 */
import java.util.Scanner;
import java.util.Vector;

public class TestVector {
	public static void main(String[] args) {
		// 1，创建Scanner对象，从屏幕提示输入信息
		Scanner s = new Scanner(System.in);
		System.out.println("请输入学生的分数（输入负数表示结束输入）：");
		// 2.for(;;),从键盘依次获取学生的成绩，并填入由Vector v=new Vector()创建的对象v中。
		Vector v = new Vector();
		int max = 0;// 记录最高分
		for (;;) {
			int t = s.nextInt();
			if (t < 0) {
				break;
			} else {
				Integer i = new Integer(t);// 将基本类型转成包装类
				v.addElement(i);// 将这个包装类添加到向量类中
				if (max < t) {
					max = t;
				}
			}
		}
		System.out.println(max);
		for( int i=0;i<v.size();i++){
			Integer tt=(Integer)v.elementAt(i);
			int t=tt.intValue();
			char  level;
			if(max-t<10){
				System.out.println("分數"+t+"  等級"+"A");
			}else if(max-t<20){
				System.out.println("分數"+t+"  等級"+"B");
			}else if(max-t<30){
				System.out.println("分數"+t+"  等級"+"C");
			}else{
				System.out.println("分數"+t+"  等級"+"D");
			}
		}
	}

}


