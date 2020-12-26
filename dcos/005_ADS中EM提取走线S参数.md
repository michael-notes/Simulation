#   ADS使用EM提取走线S参数

### 目的

使用ADS的EM仿真从Layout将走线的S参数提取 ，联合原理图进行仿真

<img src="images/0501.png" width="80%">

### 一、Allegro PCB 导入 ADS Layout

#### 1.1 Allegro PCB导出 ODB++ 格式

1. 打开PCB文件，选择 “ file > export > ODB++ inside ” , 弹出对话框 ，点击 “OK”
   
    <img src="images/0502.png" width="80%">

2. 设置输出路径 ，文件名 ，点击 “ Translate ”  ，弹出“Select option viewer ”窗口，点击 “Accept” ，等待导出完成

    <img src="images/0503.png" width="80%">

3. 导出完成后 ，直接关闭 ODB++ Viewer , 保存路径下  ，生成 ODB++ 文件 （压缩包）

    <img src="images/0504.png" width="80%">

4. ODB++ 格式文件导出完成

#### 1.2 ODB++文件导入 ADS

1. 打开ADS软件 ，新建 Workspace ， 选择 file > improt > Design

    <img src="images/0505.png" width="80%">

2. Improt 对话框内，选择 ODB++ 格式类型 ，文件所在的路径

    <img src="images/0506.png" width="80%">

3. 弹出叠层信息 ，确认没有问题，点击 OK ，等待导入完成

>  PCB Layout设置了叠层信息 ，ODB++ 文件包含PCB的叠层信息

4. 导入完成后，自动生成 “ example ” cell ，叠层信息

     <img src="images/0507.png" width="80%">

5. 文件导入完成，双击 “ example ” cell 下的 Layout 文件 ，打开导入的PCB

    <img src="images/0508.png" width="80%">

### 二、ADS Layout 进行 EM仿真

#### 2.1  ADS Layout 中剪切仿真的走线

1. 使用导航栏过滤器 ，筛选要仿真的网络 ，并选中
   
    <img src="images/0509.png" width="80%">

2. 剪切部分电路进行仿真 ，选择 EM > Tools > Cookie cutter 

    <img src="images/0510.png" width="80%">

3. Cookie cutter 设置中 ，选择 Bounding Box ，点击 Cut

    <img src="images/0511.png" width="80%">

4. 生成剪切后的 Cell_1 Layout 文件

    <img src="images/0512.png" width="80%">

5. 网络过滤器筛选要仿真的网络 ，并选中走线 ，点击 Edit > Crop selected 

    <img src="images/0513.png" width="80%">

6. 剪切完成后的走线 

    <img src="images/0514.png" width="80%">

7. 点击 “Port ”  ， 走线的输入和输入放置 4个 Port

    <img src="images/0515.png" width="80%">

#### 2.2 EM 仿真设置

1. 菜单栏点击 “ EM > Simulation Setting ”

    <img src="images/0516.png" width="80%">

2. 弹出 New EM Setup View 对话框 ，默认设置，点击 “ Create EM Setup View ”

    <img src="images/0517.png" width="80%">

3. 设置 EM setup for Simulation  , EM Simulator 修改为 Momentum  RF 

    <img src="images/0518.png" width="80%">

4. Frequency Plan 修改 Stop 频率为 4GHz

    <img src="images/0519.png" width="80%">

5. Options 选择 Physical Model , Via 选择 wire

    <img src="images/0520.png" width="80%">

6. 其他未修改使用默认设置 ，点击 “Simulation”

    <img src="images/0522.png" width="80%">

7. 状态栏显示仿真完成

    <img src="images/0523.png" width="80%">

8. EM仿真的走线设置原理图Symbol ，点击 “OPEN symbol editor ”

    <img src="images/0524.png" width="80%">

9. Symbol Generator 选择 Look-like ，设置symbol放大倍数 0.1

    <img src="images/0526.png" width="80%">

10. 点击 “OK ”后 ，Symbol 与实际走线相同 ，菜单 file > save ，保存设置

    <img src="images/0527.png" width="80%">

### 三、原理图联合仿真

1. 新建原理图Cell_2 ，并打开 schematic ，Cell_1 下的Symbol右键 Place Component

    <img src="images/0528.png" width="80%">

2. 将 Cell_1生产的Symbol放置到 Cell_2 原理图 ，进行仿真

    <img src="images/0529.png" width="80%">