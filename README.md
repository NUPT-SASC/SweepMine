# By LemoXiao -2017-10-23

这是一份有关扫雷的游戏程序源代码说明，源代码分为七个文件，一个主函数，附带六个功能函数，以下分别对六个文件的具体功能进行说明：

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *

 ### 数据类型说明

#### int[ ][ ] isMine； // 用二维数组来标记是否为雷

#### int[ ][ ] isEnable; // 用二维数组来判断格子是否已经打开

#### int[ ][ ] rightClick,; // 右击的循环标记格子是处于旗子到问号到原装的状态

#### int[ ][ ] right; // 右击的循环标记从旗子到问号到原装的数字


#### int[ ] count1, count2; // 

#### JButton[ ][ ] button;//将扫雷的每一个格子都设置成一个按钮，用二维数组来表示

#### JButton[ ] bon; //将主界面内的除扫雷格子以外的按钮用数组包含

#### JMenuItem[ ] item;//将菜单栏里面的内容用数组包括定义

#### String[ ] str; // 字符串数组包含菜单栏项目的名字

#### JList<?> list;//  在Statistics 面板中的难度单选框

#### JLabel[] label; // 在Statistics 面板中的所有label的集合

#### BufferedWriter BW; //将文本写入字符输出流，用于文件读写record

#### BufferedReader BR;//读出字符输出流，用于文件读写record

#### TextField[] file; //文本域数组，用于扫雷区域的长、宽和雷数的记录和设定

#### JRadioButton[ ] radio;//单选框数组，用于Options选项中难度设置的选择

#### JLabel[ ] label;//标签数组，用于Option选项中难度内容的说明

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *

##  main.java

### 这是运行整个程序的主函数

## Part 1:
    使用了SweepMine中的Frame（）函数，生成了一个扫雷框架实例

## Part 2：
    设置了主窗口的大小以及进行了扫雷实例窗口和实际窗口大小比较适应、位置调整

## Part 3:
    设置了主窗口的默认关闭方式

## Part 4：
    添加了一个窗口监听器，在里面添加了对按钮的监听以及窗口对应的提示
    在其中添加了对record函数的调用，完成对记录的读写

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *

## failPane.java

### 这是点到雷之后，游戏失败时弹出的窗口，窗口使用的容器是JDialog，并带上监听器的功能

## Part 1：  
    设置面板属性，大小位置、是否可见等属性，并设置了默认的关闭模式

## Part 2: 
    创建了一个Jpanel实例，并且对其的位置、大小等进行设置，然后向面板中添加了三个按钮以及一个文本框

## Part 3：
    分别设置了三个按钮的功能，分别调用了newgame（）函数，restart函数，退出时调用了record的功能函数，对数据进行记录

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
## winpane.java

### 这是通过扫雷游戏后弹出的窗口，使用的容器，流程都与failpane.java保持一致，不再多加描述

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *

## Message.java

### 这是信息窗口面板，主要是对record的信息进行读取，并且排序显示出来

## 代码结构：
    class Message extends JDialog implements ActionListener, MouseListener,Runnable
        public Message(String s)
        public void run()
        public void sort(String[] str)
        public void countWin(String s) 
        public void noRecord() 
        public void show(String s)
        public void actionPerformed(ActionEvent e)
        public void mousePressed(MouseEvent e)
        public void mouseClicked(MouseEvent arg0) 
        public void mouseEntered(MouseEvent arg0)
        public void mouseExited(MouseEvent arg0) 
        public void mouseReleased(MouseEvent arg0) 


### 注释结构：

    // Constuct Method
        // Add component to pane
        //restruct the run method
        // read the information of record
        // Add component to pane
    
    ***Difficult Part** 
    // range the time of sweeping mines
        // Calculate the percent of winning the game
        // Judge Record is empty
        // Judge Record is not empty
        // Check && Confirm
        // Reset the statistical information
    **************
    
    // The function about Mouse' pressing the RadionButton
            // Basis
            // Intermediate 
            // Advance
    
    // Mouse Method restruction Default

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
## Recorder.java
### 主要函数：
    构造方法：
    FileWriter fw = new FileWriter(String fileName);//创建字符输出流类对象和已存在的文件相关联。文件不存在的话，并创建。
    BufferWriter
    将文本写入字符输出流，缓冲各个字符，从而提供单个字符、数组和字符串的高效写入。
    write
    写入数据
    close
    关掉数据流
    异常捕获：
    catch (IOException e) {
            e.printStackTrace();

## 代码结构
    class Record
        public Record()
        public void writeNumber(int level, int i) 
        public void writeTime(int level, int i) 
        public void writeLevel(int i)
        public void writeLevel4(int row, int column, int mine) 
        public String readNumber(int level) 
        public String readLevel()
        public String readTime(int level)
        public void clear() 
        public String getTime() 


### 注释结构

    //set a number of the game
    // Set the time of Sweeping mine
    // record the Difficulty level of Sweeping mine
    // set the number of squares and mines when user defines level by itself
    // get the number of the game
    // read the time of sweeping mine
    // Read the level of sweeping mine
    // Reading the number of squares 
    // read mines when user defines level by itself
    // Clear every record
    // formate the win time

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *

## Setting.java

 * This is a level setting panel,include the number of the block and mines    
 * // set 4 radiobuttons  add to the button group ,add to the pane
 * // set 9 Label ,3 text windows, 2 Button:"confirm' and "cancel",add to the pane
 * 
 * supplement：we add the user-defined mode to add the fun of game
 * supplement: we add the shortcut key function to make the panel more similar likes the game 


## 代码结构

    class Setting extends JDialog implements ActionListener, KeyListener,Runnable 
        public Setting(SweepMine mine, int level, String s)
        public void addPart() 
        public void actionPerformed(ActionEvent e) 
        public void run() 
        public void keyPressed(KeyEvent e)
        public void keyReleased(KeyEvent arg0)
        public void keyTyped(KeyEvent e) 



### 注释结构
    // Setting the panel font and location
    // setting the radiobutton and add to the group and panel
    // set the location and actionlistener
    // setting the label font\location  and add to the panel
    //add three textfield to set the hight\width\mine number 
    //add two button to make the setting coming into force
    // Setting the usable the custom bar
    // Setting the number of text
    // select the level of difficulties  
    // Cancel Button
    // Basis
    // Intermediate
    // Advance
    //  User-defined
    // monitoring the shortcut key input and make key's function is working 


