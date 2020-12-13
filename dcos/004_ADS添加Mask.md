#   ADS 添加Mask限值

### 目的

直观的查看仿真结果 ，在仿真结果图添加Mask限值线

<img src="images/0401.PNG" width="80%">

### 添加方法

#### 方法一  直接在仿真结果中画出限值线

1. 选择菜单 Insert > Mask > line ,分段画线

    <img src="images/0402.PNG" width="80%">

2. 双击画的线段 ，弹出 Edit plot Mask line 对话框 ，Option选项卡内设置线宽，颜色 

    <img src="images/0403.PNG" width="80%">

3. Data point 选项卡中 ，X Data 设置频率 ，Y Data设置限值

    <img src="images/0404.PNG" width="80%">

4. 设置起始频率和限值 ，再设置结束频率和限值 ，如频率10MHz~100MHz 限值 -6dB ~ -20dB

    <img src="images/0405.PNG" width="80%">

5. 依次设置其他频点和限值

#### 方法二  原理图中添加限值表达式

1. Part中选择 “ MeasEqn ” 控件 ，放到原理图中   

    <img src="images/0406.PNG" width="80%">

2. 双击 “ MeasEqn ” 控件 ，编辑参数

    |  Freq  | Value  |
    | -----  | -----  |
    | 10MHz  | -5dB   |
    | 100MHz | -20dB  |
    | 500MHz | -28dB  |
    | 1GHz   | -25dB  |
    | 3GHz   | -15dB  |

    <img src="images/0407.PNG" width="80%">
    <img src="images/0408.PNG" width="80%">

> Tips : 输入数据使用 [ ] , 使用 “ ，” 隔开

3. 编辑完成后 ，点击 “ OK ”
   
    <img src="images/0409.PNG" width="80%">

4. 双击仿真结果图 ，弹出 “Plot traces and Attributes ” , 选中 “ mask ” , 点击 “ Add vs ”

    <img src="images/0410.PNG" width="80%">

5. 弹出选择依赖变量对话框 ，选中 maskfreq ，点击 “ OK ” ，完成限值线的设置

      <img src="images/0411.PNG" width="80%">
      <img src="images/0412.PNG" width="80%">

6. 点击 “ OK ” ，仿真结果显示Mask限值线 ，添加说明图示完成

    <img src="images/0413.PNG" width="80%">