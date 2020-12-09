# shiyan5


#实验目的
1.掌握字符串String及其方法的使用
2.掌握文件的读取/写入方法
3.掌握异常处理结构


#实验要求
在某课上,学生要提交实验结果，该结果存储在一个文本文件A中。
文件A包括两部分内容：
一是学生的基本信息；
二是学生处理后的作业信息，该作业的业务逻辑内容是：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能方法，实现如下功能：
1）每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
2）允许提供输入参数，统计古诗中某个字或词出现的次数
3）输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A
4）考虑操作中可能出现的异常，在程序中设计异常处理程序

#实验过程
一、首先，创建一个学生类，可以参考上一次实验的学生类进行修改。
class Student{                  //创建学生类
	    public Student(){

	    }
	    public Student(String name,int age,int number,String sex){
	        this.name = name;           //对学生基本信息进行赋值
	        this.age = age;
	        this.number = number;
	        this.sex = sex;
	    }
      private String name;            //对学生的基本信息进行定义
	    private int age;
	    private int number;
	    private String sex;
      ……………………
      
      
 二、进行作业系统的设计，对作业进行读取和修改。
 class Homework{                                      //创建作业类
	    public static StringBuffer HW(StringBuffer str1){
	        StringBuffer str2 = new StringBuffer(str1);
	        int j=0;int z;
	        for(int i = 7;i < str2.length()-45;i= i+7){        //按照实验要求对作业进行修改，使输入的文本B修改好后写入文本A中
	            z = i +j;
	            if(i%2 == 0){                                    //文本修改条件
	                str2.insert(z,"。\n");
	                j = j+2;
	            }
	            else{
	                str2.insert(z,"，");
	                j= j+1;
	            }
	        }
	        System.out.println(str2);
	        return str2;
	    }
      
      ………………



三、读取文件，创建txt文件，将文件的路径输入到对应的位置。
  public static void Write(StringBuffer s){
	        try{
	            BufferedWriter bw = new BufferedWriter(new FileWriter("C:\\Java\\File\\A.txt"));     //存放文件的路径（注：文件路径需要用双反斜杠符号隔开）
	            bw.write(s.toString());
	            bw.close();
	        }catch (IOException e){
	        }
	    }
      
      ………………
      
      
 四、运行程序，得到想要的实验效果。
 实验结果如下（不会插入图片，所以直接用文字代替）
 
 汉皇重色思倾国，御宇多年求不得。
杨家有女初长成，养在深闺人未识。
天生丽质难自弃，一朝选在君王侧。
回眸一笑百媚生，六宫粉黛无颜色。
春寒赐浴华清池，温泉水滑洗凝脂。
侍儿扶起娇无力，始是新承恩泽时。
云鬓花颜金步摇，芙蓉帐暖度春宵。
春宵苦短日高起，从此君王不早朝。
承欢侍宴无闲暇，春从春游夜专夜。
后宫佳丽三千人，三千宠爱在一身。
金屋妆成娇侍夜，玉楼宴罢醉和春。
姊妹弟兄皆列士，可怜光采生门户。
遂令天下父母心，不重生男重生女。
骊宫高处入青云，仙乐风飘处处闻。
缓歌慢舞凝丝竹，尽日君王看不足。
渔阳鼙鼓动地来，惊破霓裳羽衣曲。
九重城阙烟尘生，千乘万骑西南行。
<未完，待续>，


实验心得：
1.通过这次实验，我掌握了字符串string及其方法的使用；
2.掌握了文件的读取以及写入方法；
3.本次实验中出现了很多问题，比如异常处理部分，没有完全掌握，导致实验过程进展缓慢，今后会对这一部分的内容进行反复练习，争取早日掌握。
4.在这次实验中，复习了许多c语言中的常用语法，也让我意识到编程语言有很多相通的地方，自己对于编程语言的理解还不是很透彻，还有很多东西需要学习。
