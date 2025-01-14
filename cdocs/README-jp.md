# FastBuilder Phoenix 

## 紹介

> FastBuilder Phoenix とは、NetEaseの中国版のMinecraftの賃借的なサーバーで建築を迅速に作るツールである。目下建造出来る物はユークリッド幾何学のストラクチャーとACME(mcacblock)ファイル・schematicファイル(NBT データは廃棄される)・bdxファイルのストラクチャーと画像のプレート化したストラクチャーです。

**ご注意: FastBuilder Phoenix は営利的なソフトである**

### 原理

目下のFastBuilderは一新したテクを使用しているので、WebSocketに制限されないですので、新しいFastBuilderの建造するスピードも、性能も、スタビリティーも、かなり増進した。今のFastBuilderのコアはSandertvのMITライセンスで発表した[Gophertunnel](https://github.com/Sandertv/gophertunnel/)に基づいている。

### オープンソース

FastBuilder Phoenix のクライアントは [GitHub](https://github.com/LNSSPsd/PhoenixBuilder)でオープンソースで発表した。

(ライセンスはGPL v3です)

### ご注意 (決済する前には必ず読む)

* 決済するのは、お客様は[FastBuilder ユーザー　ライセンス](LICENSE.html)を同意し、遵守するのを保証することを示す。

- FastBuilderが使っているテクはいつか失効するかもしれないですので、FastBuilderの永遠なサポートって言うことは保証できない。
- お客様が買ったFastBuilderは、上述の機能が含んでいる、それ以上の機能がこの後で加えるかもしれないですが、それは保証されない。
- 一部のインストールのステップはある程度の**ITと数学の知識**が必要ですので、このマニュアルはお客様はもうそれらを備えてると考えます。
- FastBuilder ユーザーセンターには、新しいアカウントには二つのスロットが含まれています（ぼっち版には一つ）、そのスロットがNetEaseのMinecraftのサーバー番号とバインドできます、バインド後は一ヶ月に変動不能の状態になります。FastBuilder Phoenix はNEMCのムルチプレーヤーモードやMinecraft Bedrock Edition (国際版)に使用はできないのでご了承下さい。
- FastBuilder　ユーザーセンターには、二つのプランが選択可能となります（どれでもNEMCのムルチプレーヤーモードやMinecraft Bedrock Edition (国際版)に使用はできない）
  * ぼっち版（７０CNY）：アカウントは一つのスロットが含まれていますので、一つだけのレンタルサーバーとバインドできます。
  * 一般版（１２０CNY）：アカウントは二つのスロットが含まれていますので、二つのレンタルサーバーとバインドできます。
  * もしももっと多いレンタルサーバーが持っているなら、スロットも購入出来ます：
    * 変更出来るスロット（６０CNY）：一つのレンタルサーバーにバインドできます、一ヶ月に一回だけ変更できます。
    * 変更出来ないスロット（２０CNY）：一つのレンタルサーバーにバインドできますけど、バインド後は変更できません。
- 建築ファイルを**無許可的**に使用**しない**で下さい。創作者はみんな自分の力と知識でコミュニティーで生きることを求めているんです。他の人のIP(知的財産)の営利的な無駄使いは全ゲームにとっては破壊的なことになります。その上、もしもファイルの作者があなたの無駄使いを追及したら、あなたはそれを負担しなければならないです、そのうち、うちらはなにも負担しないはずです。

### <ruby><rb>基本概念</rb><rp>(</rp><rt style="font-size:80%">せかいかん</rt><rp>)</rp></ruby>

FastBuilderには、サーバーやクライアントっていう概念があります。ユーザーのゲームーとFastBuilderはみんなクライアントである、そのうちレンタルサーバーだけはサーバーである。

Therefore, clients can run on different devices, and FastBuilder can be executed to join your server w/o your game running.

The abilities explained below are required since FastBuilder needs the operations of command lines.

* The ability of operating files: Able to understand the level of paths and files.

- The ability of reading English: Able to identity words like "Error", "Permission denied" or "Not found" and know what they stands for.
- The ability to differ the full-width and the half-width characters.
- It's better to have the ability to enter and execute commands in the command line interface.

Please ensure that you have the abilities mentioned above, if you encountered problems when using FastBuilder because you are not satisfying the mentioned conditions, development group would not bear any liabilities, moreover it will not provide any help.

### Installation Instruction

#### Requirements

- Holds a FastBuilder User Center account, aka a FastBuilder account (bought FastBuilder).
- Depends on your device:
  * PC (Windows/Linux/macOS): Your computer should have a fully functional network adapter installed.
  * Android: Have *Termux* installed, see below for instruction.
  * iOS: Jailbroken, and you know how to use the terminal.
- Hard-working hands and thoughtful brain

1. Login to [FastBuilder User Center](https://uc.fastbuilder.pro) 
2. Click the *Profile* tab, and set the *<ruby><rb>Minecraft Netease Edition Username</rb><rp>(</rp><rt style="font-size:80%;">网易版用户名</rt><rp>)</rp></ruby>*.
3. Enter the number of the <ruby><rb>rental server</rb><rp>(</rp><rt style="font-size:80%;">租赁服</rt><rp>)</rp></ruby> that you want to use FastBuilder on.(note: The rental server should accept the entrance of **any <ruby><rb>level</rb><rp>(</rp><rt style="font-size:80%;">等级</rt><rp>)</rp></ruby>**'s player, satisfy it by turning off "<ruby><rb>player entrance level requirement</rb><rp>(</rp><rt style="font-size:80%;">玩家等级准入要求</rt><rp>)</rp></ruby>" toggle in the server settings interface)
4. Set a nickname of the <ruby><rb>helper user</rb><rp>(</rp><rt style="font-size:80%;">辅助用户</rt><rp>)</rp></ruby>, then click **[<ruby><rb>Create</rb><rp>(</rp><rt style="font-size:80%;">生成</rt><rp>)</rp></ruby>]** to create one.

That's all for the completion of necessary information, and the following content is the steps of installation, different platforms have different solutions, please find your own platform:

#### Steps for Installation

- Windows: Download directly in the [Download] tab of the user center.

- iOS: Install the package from our APT package source.

- Linux x86_64 (recommended platform): 

  ```shell
  wget -O fastbuilder https://fastbuilder.pro/downloads/phoenix/phoenixbuilder
  chmod +x fastbuilder
  ```

- Android: 

  - a. Click [here](https://f-droid.org/repo/com.termux_117.apk) to install Termux (**0.117**); (Or download it from a trustable source by yourself.)  

  - b. After the installation of Termux, navigate to your system configuration, and give it **the permission of accessing the storage space (aka sdcard)**, and allow it to **run in the background without limitations**.

  - c. Open the Termux application, copy and execute following commands.

    First, use the commands below to replace the official source to the TUNA mirror source (optional, recommended for users in China since it will boost the follow-up steps, users in other countries shouldn't perform this step.)

    > **WARNING: These 3 commands should be executed in order. The mentioned mirror is only suitable for Android version 7.0 (API 24) and above, the use of this mirror in older versions of system may cause program exceptions. Please do not use this mirror in case of you are using older versions of system.**

    ```shell
    sed -i 's@^\(deb.*stable main\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/termux-packages-24 stable main@' $PREFIX/etc/apt/sources.list
    sed -i 's@^\(deb.*games stable\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/game-packages-24 games stable@' $PREFIX/etc/apt/sources.list.d/game.list
    sed -i 's@^\(deb.*science stable\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/science-packages-24 science stable@' $PREFIX/etc/apt/sources.list.d/science.list
    ```

  - c. Update sources and packages (**REQUIRED**) :

    ```shell
    apt update -y
    apt upgrade -y
    apt install wget -y
    ```

   - d. After successfully executed commands mentioned above, download the FastBuilder binary.(Replace the `arm64` part to `armv7` if you surely know that your device is an armv7 device. Note that nowadays armv7 device is seldom. x86 or x86_64 android device are not supported.)

     > **Note: This step (d) is also the way of upgrading FastBuilder Phoenix, execute this step directly to upgrade FastBuilder afterwards.**

     ```shell
     wget -O fastbuilder https://fastbuilder.pro/downloads/phoenix/phoenixbuilder-android-executable-arm64
     chmod +x fastbuilder
     ```
### Usage

FastBuilder Phoenix is a pure command line program without complicated GUI, which made the program very easy to use.

#### Launching

- Windows: Double-click FastBuilder executable(**.exe**) file to execute.

- Linux: No need to explain.

- iOS: Open the terminal and execute the following command:

  ```shell
  fastbuilder
  ```

- Android: Open the Termux app and execute the following command:

  ```shell
  ./fastbuilder
  ```

#### Initialization

If no exceptions happened, after finishing these steps, you will see the FastBuilder's copyright notice and other things. It will ask you to enter your <ruby><rb>FBUC</rb><rp>(</rp><rt style="font-size:80%;">FastBuilder User Center</rt><rp>)</rp></ruby> username and password (**Password won't be echoed**), and you won't need to do that it twice.

Then, FastBuilder will ask you to enter the rental server number and its password(Press *Enter* directly if none, **won't be echoed**). If it haven't crashed, presumably it has been launched.

After that, leave it in the background, and enter the rental server. Seeing the helper user is online(in the user list in `/list` command or in pause interface) means that FastBuilder works properly. Please **give the helper user <ruby><rb>OP</rb><rp>(</rp><rt style="font-size:80%;">operator</rt><rp>)</rp></ruby> permission**. ~~The helper user will only listen to **<ruby><rb>operator's</rb><rp>(</rp><rt style="font-size:80%;">your</rt><rp>)</rp></ruby>** commands, so the the *Minecraft Netease Edition Username* should be set to the same to **you nickname in *Minecraft Netease Edition***. Please do not use skin packs with the **<ruby><rb>title</rb><rp>(</rp><rt style="font-size:80%;">称号</rt><rp>)</rp></ruby>** since the helper user won't be able to process your commands.~~ Please enter commands in the console since netease will ban accounts that entered fastbuilder commands in the chat scene. For that reason, it's also unrecommended to use the `get` command of FastBuilder as it gives the name of the controller to the backend, which may cause an auto ban.

#### FastBuilder Command Resolving

FastBuilder uses a system similar to Linux Shell (it isn't the same command system of Minecraft). The "/" is needless and you can execute it by simply send it as a chat message.

Note that you can't use "#" to give a comment in FastBuilder's commands.

```shell
# Example: Generate a round with radius 5, faces the y-axis.
# These 2 commands below do the same thing.
round -r 5 -f y -h 1
round --radius 5 --facing y --height 1
```

##### Generator Settings

After initializing FastBuilder, we call the dimension that the <ruby>helper user<rp>(</rp><rt style="font-size:80%;">bot</rt><rp>)</rp></ruby> in as a *space*, every operations would be executed in this space. So if you want to use FastBuilder in a different space, you should teleport the bot to the target space.

To use FastBuilder, you should set the **origin** of the **space**(**structures will be built around the origin**), and the default origin is the position where bot entered the game.

Use `get` command to modify the origin to the current position of **you**.

The usage of commands of corresponding features are shown below.

FastBuilder Phoenix used the **multi-task system**, which means that you can have more than one tasks to be executed at the same time, and you can use the `task` command to manage tasks.

##### Task Command

`task` command was designed for managing the current **tasks**(**building process**). Every task has its own runtime, and you can use some functional commands to set the internal arguments for tasks. `task` command has the following basic child commands(Texts after `#` are comments, which are used to explain what the child command for):

````shell
tasktype <type:async|sync> # **Global command**, set the task type for newly-created tasks. Sync mode doesn't support the progress displaying but builds at the same time of calculating, and async mode supports displaying the progress since it builds after calculation.
task list # Lists the ID of each tasks, and its content · status.
task pause <taskID> # Pauses a specific task
task resume <taskID> # Resumes a specific task
task break <taskID> # Destroys a specific task (Unrecoverable, the task will be gone from the task list)
````

`task` command can also be used to set the delay of a task or its delay mode:

```shell
task setdelay <taskID> <delay> # Sets the delay for the specified task. The unit in continuous mode is microsecond and it's second in discrete mode.
task setdelaymode <taskID> <delayMode:continuous|discrete|none> # Sets the delay mode for the specified task, there are 3 modes available.
task setdelaythreshold <taskID> <threshold:int> # Sets the threshold for a specific task, only available in discrete mode.
```

- continuous: Send packets with a specific speed.

- discrete: Send packets without delay after wait the time of `delay`'s value (the max count of packets per delay won't be greater than the threshold).

- none: Send packets continuously without delay.

Each mode has its own advantages and disadvantages, please handle is as you think fit:

* Speed: continuous <= discrete < none (For some special configurations, continuous mode's speed may faster than discrete mode's speed)
* Stability: continuous > discrete > none
* Smoothness: continuous > none >= discrete

##### Functional Commands

- Set the origin for the space:

  ```shell
  get
  set x y z
  ```

- Set the global command execution delay solution:

  ```shell
  delay mode <delayMode:continuous|discrete|none> # Sets the default packet sending solution
  delay threshold <threshold:int> # Sets the default threshold, only available in discrete mode.
  delay set <Delay:int> # Sets the default packet sending delay. The unit in continuous mode is microsecond and it's second in discrete mode.
  ```

- Set whether to show the progress (show information like the percentage of construction, total block count, and the instantaneous velocity. default:`true`)

  ```shell
  progress <value:bool>
  ```

* Logout from FastBuilder User Center

  ```shell
  logout
  ```

* Reselect the preferred language

  ```
  lang
  ```

* Open the FastBuilder controlling menu

  ```
  menu
  ```

  

##### Geometric Commands

FastBuilder has the ability of constructing simple geometry structures in the space. (like round, circle, sphere, line, ellipsoid, etc.)

- Round/Circle:
  ```shell
  round/circle -r <radius> -f <facing> -h <height> -b <tileName> -d <data>
  -r --radius The radius of the round or circle.
  -f --facing Facing, available values: x,y,z
  -b --block Block to be used to construct the structure
  -d --data The data (aka damage value) of the block to be used to construct the structure
  ```

- Sphere:
  ```shell
  sphere -r <radius> -s <shape>
  -s --shape hollow|solid
  ```

- Ellipse:

  ```shell
  ellipse -l <length> -w <width> -f <facing>
  -l --length Length
  -w --width Width
  ```

- Ellipsoid:

  ```shell
  ellipsoid -l <length> -w <width> -h <height>
  ```

##### Structure Construction Commands

Load and construct structures from `schematic`, <ruby><rb><code>bdx</code></rb><rp>(</rp><rt style="font-size:80%">bdump</rt><rp>)</rp></ruby> or `mcacblock`(structure file exported by the `ACME` building tool) files:

```shell
schem -p <filePath>
acme -p <filePath>
bdump -p <filePath>
-p --path The path of the file, use "" to assign a path with blankspace(s).
# optional flags: --excludecommands : Exclude commands in command blocks
# 				  --invalidatecommands: Invalidate commands in command blocks by adding characters to the start of the command content, for example, the invalid form of "say 123" is "|say 123".
#                -S --strict       : Break if the file is unsigned or failed to verify its signature.
```

##### Painting Slice Construction

- Load image to the space:

  ```shell
  plot -p <imageFilePath:string> -f <facing:x|y|z>
  ```

##### Experimental: Structure Export

**WARNING: This feature is unstable, unexpected things might happen during the use of this feature. Please check whether the exported file is valid since sometimes it might be exported to an invalid format.**

* Set the start point of export

  ```shell
  get
  set x y z
  ```

  or

  ```shell
  get begin
  ```

  - These are two different forms of a same command.

* Set the end point of export

  ```shell
  get end
  setend x y z
  ```

* Export the structure in assigned area to a file

  ```shell
  export -p <filePath>
  # optional flag: --excludecommands : Exclude commands in command blocks
  ```

* Import the exported file with the command `bdump` mentioned above.
