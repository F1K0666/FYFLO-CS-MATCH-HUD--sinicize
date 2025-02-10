# FYFLO-CS-赛事-HUD-汉化
原作者:fyflo，本项目是CS赛事UI，汉化由F1K0完成。

后面的代码项翻译可能不太准确，如果会的老登可以去[原文](https://github.com/fyflo/CS-CS2-CSGO-HUDS-Observer-fyflo)看看。

详细操作视频B站UP主: [角落里的阳光](https://www.bilibili.com/video/BV1Fp421m7mU)。

[原作者twitch](https://www.twitch.tv/fyflo)
[汉化作者哔哩哔哩账号](https://space.bilibili.com/1244247113)
[原作者DISCORD](https://discord.com/channels/392006529206976512/1315714438187323524)
[聊天QQ群](https://qm.qq.com/cgi-bin/qm/qr?k=YOEMEy-Wua8lnaPlQ2O13CHggFL77qTm&jump_from=webapi&authKey=0MIOvc4P6/yWUcHJcu1UfFQDyzFsJPmTfXZSGRbqQavgRNEEdF3d9LZxueHj0U2P)

# 更新bd
在原作者2.0.9版本中，数据库已经更新。现在使用lowbd数据库代替nebd数据库，因为它已经停止更新。而且我们需要更新node到最新版本。

为了转移队员，队伍和HUD数据库，您需要下载这个文件夹，并在没有数据库文件夹的情况下创建文件夹。

在打开时，我们会替换所有物品。

1. 进到HUD文件夹，在地址栏中调用cmd。
2. 逐条输入以下命令:
```commands
   	npm install lowdb@1.0.0 shortid nedb path
	node migrations/migrate-teams.js
	node migrations/migrate-huds.js
	node migrations/nedb-to-lowdb.js
```
3. 现在通过CS2_HUD_fyflo.exe将其作为标准程序运行

## 如果动画不适合你
启动overlay_v2.exe文件
第一步:打开开始菜单，点击齿轮图标打开设置。或者也可以按 Win+I 键快速启动设置。
第二步:导航到“辅助功能”>“视觉效果”选项，将按钮切换到“开”(默认)或“关”,以打开或关闭动画效果。

## 分辨率大于1920 x 1080的显示器设置
1.请前往以下文件夹地址: `CS2-CSGO-HUDS-Observer-fyflo-main\HUD\overlay` 中的 `package.json` 文件里根据您的需要调整分辨里 ("width": `设置宽度`, "height": `设置高度`).
2. 如果HUD显示错误, 在任务栏中选中它, 并且按下 `Win+Shift+方向键` 让其正确显示.

## 自动导播指令(目前会有BUG，请尝试后使用。)
请在控制台输入以下指令 `spec_autodirector 1` 要关可以把1设置为0

## 应用程序更新
+ 该应用程序添加了通过部分中的按钮管理团队的功能：几局几胜选项和局数胜利卡。.
还增加了一个使用HUD投票地图的部分.

<details><summary>例子</summary>

![Ex1](https://i.imgur.com/d5aTrEG.png)
![Ex2](https://i.imgur.com/eRsTkrZ.png)

</details>

## 修复COUCH和新的创建比赛页面
+ 修复 COUCH [JohnTimmermann](https://github.com/JohnTimmermann)
+ 添加了详细信息，以便地图选择不会干扰到页面创建匹配的BO 1
<details><summary>例子</summary>

![Ex1](https://i.imgur.com/9c2R9Vh.png)

</details>

## HUD和雷达文件
- 如果 RUN_HUD 和 RUN_RADAR 未启动，请下载存档并替换[文件.](https://drive.google.com/file/d/1yXAhl4kY60Tojo8oaQ7UOjq_LHR7GRVW/view?usp=sharing)

在添加新文件时，您需要删除 node_modules 文件夹

## CS2新地图
+ 更新Boltobserv 1.4版

## 新增创建匹配选项卡
更新HUD

## 新建创建匹配选项卡
+ 地图选择
+ 比赛信息

# 须知

## 在开始之前，如有必要，请更改 config.json

# 例子
<details><summary>FYFLO的HUD</summary>
	
![Ex1](https://i.imgur.com/vazk1hm.jpeg)
![Ex2](https://i.imgur.com/f70vHyB.jpeg)
- FYFLO的HUD如何工作的示例(https://www.youtube.com/watch?v=liKSKBNt224)

</details>

<details><summary>组装的HUD</summary>

[https://imgur.com/a/hx55fuz](https://imgur.com/a/hx55fuz)

</details>

## 它是如何工作的？

基本上，CS:GO/CS2将数据传输到本地应用服务器，服务器转换数据，然后将其加载到本地网页。

## 使用前需要做的事情

- 需要安装 Node.js
##
#### CSGO(不确定是否能用)
- SteamLibrary\steamapps\common\Counter-Strike Global Offensive\csgo\cfg\ `gamestate_integration_observerspectator.cfg` 需要放在CS:GO位置的cfg文件夹中
- SteamLibrary\steamapps\common\Counter-Strike Global Offensive\csgo\cfg\ `observer.cfg` 需要放在CS:GO位置的cfg文件夹中
- SteamLibrary\steamapps\common\Counter-Strike Global Offensive\csgo\cfg\ `observer_on_map_cs2.cfg` 需要放在CS:GO位置的cfg文件夹中
#### CS2
- SteamLibrary\steamapps\common\Counter-Strike Global Offensive\ `game` \csgo\cfg\ `gamestate_integration_observerspectator.cfg` 需要放在CS2位置的cfg文件夹中
- SteamLibrary\steamapps\common\Counter-Strike Global Offensive\ `game` \csgo\cfg\ `observer.cfg` 需要放在CS2位置的cfg文件夹中
- SteamLibrary\steamapps\common\Counter-Strike Global Offensive\ `game` \csgo\cfg\ `observer_on_map_cs2.cfg` 需要放在CS2位置的cfg文件夹中
##
- CS:GO/CS2 需要全屏窗口运行（我知道人们可能不喜欢它，但因为它只是为了观察，所以......）
- 在运行CS:GO/CS2并连接到比赛(或DEMO，你也可以在里面用这个)后，控制台输入` exec observer . CFG `/` observer _ on _ map _ CS2 `,它会使除地图和击杀信息之外的所有默认内容消失(可以使用` exec observer _ off . CFG `/` exec observer _ on _ map _ CS2 `恢复正常)
- 确保填写 `config.json` 文件中的所有内容

## 配置

```javascript
//config.json
{
    "GameStateIntegrationPort":1337, //这必须和gamestate_integration_observerspectator.cfg文件中相同,
    "ServerPort":2626, //你电脑上的空闲端口
    "SteamApiKey":"ABCDEFGIJK12345678", //Steam API密钥，没有它头像就不能工作
    "PrintPlayerData": false, // 用于查看游戏中玩家的STEAM ID以添加到玩家后台
    "DisplayAvatars": true, // 显示Obs头像
    "DisplayPlayerAvatars": false, // 显示玩家后台中自定义的玩家头像
    "DisplayTeamFlags": false, // 在团队回合分数下显示团队国旗
    "DisplayPlayerFlags": true, // 显示玩家国旗（一般在中间的显示台上）
    "DisplayAvatars": false, // 显示头像 true是开，false是关
    "AvatarDirectory":"./public/files/avatars/", // Local storage for avatars
    "SpecialEvent": "SHOWMATCH", // 如果“创建比赛类型”设置为“NONE”,它将使用此文本-用于其他用途，不要管它
    "LeftImage": "/files/league/miceklogo.png", // 左侧广告栏小图片1（如果HUD有广告栏则会显示）
    "LeftImage2": "/files/league/supearmiceklogo.png", // 左侧广告栏小图片2（如果HUD有广告栏则会显示）
    "LeftImage3": "/files/league/turniej_logo.png", // 左侧广告栏小图片3（如果HUD有广告栏则会显示）
    
    "LeftOneImage": "/files/league/turniej_logo_kopia.png", // 左侧广告栏最大图片，铺满整个广告栏（如果HUD有广告栏则会显示）
    "DisplayOnlyMainImage": false, // 打开此项将只显示一个大图片，而不是3个小图片
    "_onlyComment": " 这个图片 ^^^ (LeftOneImage) 应该是 405px x 85px ",
    
    "DisplayScoreboard": true, // 记分牌出现在回合结束时(每4回合一次)
    "DisplayRadar": true, // 显示雷达 (如果RUN_RADAR不起作用)
    
    "LeftPrimary": "Left Primary Text", // 左侧广告栏顶部文字
    "LeftSecondary": "Left Secondary Text", // 左侧广告栏底部文字
    "RightImage": "/files/img/elements/icon_microphone.png", // 右侧广告栏图片
    "RightPrimary": "Right Primary Text", // 右侧广告栏顶部文字
    "RightSecondary": "Right Secondary Text", // 右侧广告栏底部文字
}
```

## 怎么让它跑起来？

- 安装 NodeJS v20.18.0 (nodejs.org)
- 在某个地方下载 repo
##
- 
打开 CS2_HUD_fyflo.exe##
- 然后运行OVERLAY.exe: [OVERLAY 下载](https://drive.google.com/file/d/1_NoHJRfSVFF8yTp8hXabf9Du76mowhPD/view?usp=drive_link) (放置在文件夹CS-CS2-CSGO-HUDS-Observer-fyflo)或只是去你的浏览器 (http://你的 IP:2626)
- 确保在Overlay exe文件夹中，有一个包含以下内容的config.json文件:
- 雷达将在 :36364 端口 (http://localhost:36364)

```javascript
//config.json
    {
        "port": 2626 // 与上面的 config.json 文件中的 电脑空闲端口 相同
    }
```

## 如何让它和OBS一起工作？
- 在您的OBS里创建一个新的场景
- 在场景中，点击加号按钮，添加窗口捕捉，并选择cs2.exe
- 添加浏览器，在url中复制并粘贴您CS UI链接
- 添加第二个浏览器并粘贴雷达的网址(有的UI自带雷达，有的没有所以需要手动放下)
![Ex5](https://i.imgur.com/TsxNBgP.png)
![Ex6](https://i.imgur.com/aqxAHXH.png)

## UI后台面板

启动文件后，转到终端/命令提示符中显示的地址。你应该看到管理面板分为三个部分-队伍，玩家，创建比赛和hud。在这里您可以管理比赛中 HUD 的信息。

#### 队伍面板

您可以在这里定义队伍，队名，队名简称(但简称实际上是不在任何地方用的)，队伍的国旗和头像。队伍头像的文件保存在 `public/storage/` 其文件名应从 `logo-`.
![Ex1](https://i.imgur.com/7HPOrB0.png)

#### 玩家面板

在玩家标签中，你可以定义玩家的真实姓名，显示姓名，国旗(也可以设置为“与队伍相同”)，他们的队伍以及识别玩家 steam 64位ID. 玩家头像的文件保存在`public/storage/` 其文件名应从 `avatar-`.
![Ex2](https://i.imgur.com/tiDnUPj.png)

#### 创建比赛面板

在这里你可以设置比赛的类型--这是一个NONE，BO1，BO3或BO5的选项卡，队伍的得分以及哪个队应该应用在HUD。如果队名放反了，下面有一个 `反转队伍信息` 按钮，点击后可以快速翻转队名，以便恢复正确。
此外，如果在比赛期间，您想改变队伍或玩家信息，你可以改变它(例如在手机上，如果您允许通过防火墙的节点，您是在同一个局域网)，然后在这个标签点击 `强制刷新HUD`, 以确保应用所有更改。

![Ex3](https://i.imgur.com/61l8zd7.png)

### HUDS

此标签显示本地HUD。它们不会被验证是否能用，但是如果有任何文件丢失，它会在警告栏中通知你。
您可以创建或删除每个HUD以使其能不能访问。还有HUD链接信息-如果你点击它，它会将您重新跳转到本地网页，即用作HUD。如果主播想要单独HUD界面，这很有用的——例如 它可以作为浏览器源添加到OBS中，然后你只需要将其设置为HUD的URL。
这对于更大的流媒体工作空间可能很有用，例如对于具有不同PC的专门用于重放的设置-一个服务器应用程序将管理本地网络上的每个HUD，因为所有HUD都是可用的，如果它们没有被禁用的话。
![Ex4](https://i.imgur.com/HbdH4Ia.png)

### 活动页面

在这个标签中，您可以在HUD运行时显示/隐藏记分板和雷达边框

![Ex5](https://i.imgur.com/cyg5Ws4.png)

## 如何创建自己的HUD
进到 `public/huds` 复制粘贴 `default` 文件夹，并重新命名为你的心的内容-这就是你的HUD将如何显示在管理面板。
`template.pug` - template是用PUG编写文件，用来管理HUD模型的, 重要的。
`style.css` - style是用css编写文件，用来管理HUD模型大小和数据的的, 推荐的。
`index.js` - HUD的运行引擎。看看默认的和模板，了解它是如何工作的。

在 `index.js` 中最重要的部分是 `updatePage()` 函数。任何HUD都需要它来工作，因为当数据来自CS:GO时会调用这个函数。

屏幕上发生的所有主要动作都发生在“updatePage()”函数中，所以当你想表示一些信息时，你需要在它的边界内编写代码。
```javascript
function updatePage(data) {
	//Here happens magic
}
```
`data` 参数被传递给它，从那里我们可以采取行动，例如获取玩家、地图、回合等信息。您将在下面找到有关接收信息的详细信息:>

### `data`

获取不同对象的方法:



|方法|描述|例子|返回的对象|
|---|---|---|---|
|`getTeamOne()`|关于管理面板中定义的第一个队伍的信息|`var teamOne = data.getTeamOne();`|JSON:`{team_name: "SK Gaming", short_name: "sk", country_code: "Brazil", logo: "logo-1527775279488.png", _id: "MT3xr6mb37o8Vbe3"}`|
|`getTeamTwo()`|关于管理面板中定义的第二个队伍的信息|`var players = data.getTeamTwo();`|如上所述|
|`loadTeam(id)` id: 字符串 |有关在管理员面板中定义的具有给定 ID 的团队的信息|`var players = data.loadTeam("MT3xr6mb37o8Vbe3");`|如上所述|
|`getMatchType()`|这是哪种比赛类型的信息|`var matchup = data.getMatchType();`|字符串: `bo2`, `bo3` 或 `bo5`|
|`getMatch()`|有关面板中的比赛设置的信息|`var match = data.getMatch();`|JSON: `{match: "bo5", team_1: {map_score:1, team:"auto"}, team_2: {map_score:1, team:"MT3xr6mb37o8Vbe3"}}`|
|`getPlayers()`|玩家名单|`var players = data.getPlayers();`|(玩家数组)|
|`getCT()`|警 CT 的信息|`var ct = data.getCT();`|(队伍)|
|`getT()`|匪 T 的信息|```var t = data.getT();```|(队伍)|
|`getObserved()`|当前观看的玩家|```var player = data.getObserved();```|(玩家) 如果你不想见任何人, 返回的玩家将有steamID 1和名字GOTV|
|`getPlayer(observer_slot)` 具有给定观察槽 （o-9） 的玩家|```var first = data.getPlayer(1);```|(玩家)|
|`phase()`|游戏的当前阶段|```var phase = data.phase();```|(阶段)|
|`round()`|回合信息|```var round = data.round();```|(回合)|
|`map()`|地图信息|```var map = data.map();```|(地图)|
|`previously()`|如果自上次更新后有任何更改，它将包含以前的值|```var previously = data.previously();```|(阵列)有关的更多信息 `previously()` 你会在底部找到|


例子:
```javascript
function updatePage(data) {
	var player = data.getObserved(); // 当前观看的玩家信息
    var teamLeft = data.getTeamOne(); // 队伍一的信息
    var teamRight = data.getTeamTwo(); // 队伍二的信息
    
    var round = data.round();
    
    // 设置队伍名称
    $("#team_one_name").html(teamLeft.team_name); 
    $("#team_two_score").html(teamRight.team_name);
    // 如果没有指定，这些可能为 NULL , 然后使用getT()和getCT() 
    
    //设置队伍国旗
    if(teamLeft.country_code){
        $("#team_1 #team_flag").css("background-image", "url('/files/img/flags/"+teamLeft.country_code + ".png')");
    }
    if(teamRight.country_code){
        $("#team_2 #team_flag").css("background-image", "url('/files/img/flags/"+teamRight.country_code + ".png')";
    }
    
    var playerlist = data.getPlayers(); // 玩家名单
    if(playerlist){
        for(var steamid in playerlist){
        	/* 这里的操作将针对每个玩家 */
            let player = playerlist[steamid];
            
            let displayed_name = player.name;
            let real_name = player.real_name; // 如果没有设置名字，它将显示玩家游戏名字player.name
        }
    }
    
    
}
```

## 对象
### 玩家

性能


|Property(不咋会)|描述|例子|值|
|---|---|---|---|
|name|玩家的 Steam 名称|```var name = player.name;//OLOF```|(字符串)|
|real_name|玩家的真实姓名，如果在面板中设置的话|```var real_name = player.name;//Olof Kajbjer Gustafsson```|(字符串)|
|clan|玩家当前显示的氏族标记|```var clan = player.clan;//fnatic```|(字符串) 或者 (NULL)|
|observer_slot|玩家的号码|```var slot = player.observer_slot;//3```|(整数) 0-9|
|team|玩家阵营|```var team = player.team;//CT```|(字符串) CT/T|
|position|玩家在地图上的当前位置|```var pos = player.position;//-663.10, -198.32, 16.03```|(字符串) x, y, z|
|steamid|玩家的steam64位ID|```var sid = player.steamid;//76561197988627193```|(字符串)|
|teamData|玩家的个人队伍信息，如果在面板中设置|```var team = player.teamData;```|(JSON):```{team_name: "SK Gaming", short_name: "sk", country_code: "Brazil", logo: "logo-1527775279488.png", _id: "MT3xr6mb37o8Vbe3"}```|

例子:
```javascript
function updatePage(data) {
	var player = data.getObserved(); // 获取观看的玩家对象
    var name =  player.name; // 得到那个玩家的名字
    var slot = player.observer_slot; // 得到那个玩家的位置
    
     if(player.team == "CT"){...}
}
```
方法

|方法|描述|例子|值|
|---|---|---|---|
|`getWeapons()`|玩家武器列表|```var weapons = player.getWeapons();```|(武器阵列)|
|`getCurrentWeapon()`|玩家的主武器|```var holding = player.getCurrentWeapon();```|(武器)|
|`getGrenades()`|玩家的道具|```var grenades = player.getGrenades();```|(武器阵列)|
|`getStats()`|玩家当前的统计数据(列表如下)|```var stats = player.getStats();```|(排列)|

统计:



|统计名称|描述|例子|值|
|---|---|---|---|
|health|玩家的血量|```var health = player.getStats().health;```|(整数) 0-100|
|armor|玩家的护甲|```var armor = player.getStats().armor;```|(整数) 0-100|
|helmet|玩家的头盔|```var helmet = player.getStats().helmet;```|(bool) True/False|
|defusekit|玩家的拆弹器|```var def = player.getStats().defusekit;```|(bool) True/False 或 (NULL)|
|smoked|烟雾程度|```var flashed = player.getStats().smoked;```|(整数) 0-255 或 (NULL)|
|flashed|被闪程度|```var flashed = player.getStats().flashed;```|(整数) 0-255|
|burning|烧伤程度|```var burning = player.getStats().burning;```|(整数) 0-255|
|money|玩家的钱|```var money = player.getStats().money;```|(整数) 从0开始|
|round_kills|玩家在回合中的击杀数|```var round_kills = player.getStats().round_kills;```|(整数) 通常为 0-5|
|round_killhs|玩家在回合中爆头击杀|```var round_killhs = player.getStats().round_killhs;```|(整数) 通常为 0-5|
|equip_value|玩家装备的价值|```var equip_value = player.getStats().equip_value;```|(整数) 从0开始|
|kills|玩家的击杀数|```var kills = player.getStats().kills;```|(整数)|
|assists|玩家的助攻数|```var assists = player.getStats().assists;```|(整数)|
|deaths|玩家的死亡数|```var deaths = player.getStats().deaths;```|(整数)|
|mvps|玩家的MVP```var mvps = player.getStats().mvps;```|(整数)|
|score|玩家的分数|```var points = player.getStats().score;```|(整数)|

例子:

```javascript
function updatePage(data) {
	var player = data.getObserved(); //获取正在观看玩家的数据
    var stats =  player.getStats();
    var weapons = player.getWeapons();
    
    $("#health_box").html(stats.health);
    
    for(var k in weapons){...}
    
    if(stats.defusekit !== true){
    	$("#defusekit").css("display", "hidden");
    }
}
```

### 武器
|Property|描述|例子|值|
|---|---|---|---|
|name|武器的名称|```var name = weapon.name;//weapon_awp```|(字符串) weapon\_...|
|paintkit|武器皮肤的名称|```var skin = weapon.paintkit;//cu_medusa_awp```|(字符串)|
|type|武器类型|```var type = weapon.type;```|(字符串) Knife/Rifle/SniperRifle/Grenade|
|state|装备状态|```var state = weapon.state;```|(字符串) holstered/active|
|ammo_clip|弹匣中的弹药|```var clip = weapon.ammo_clip;```|(整数)|
|ammo_clip_max|弹匣中的最大弹药量|```var maxclip = weapon.ammo_clip_max;```|(整数)|
|ammo_reserve|弹匣外的弹药|```var res = weapon.ammo_reserve;```|(整数)|

### 地图
|Property|描述|例子|值|
|---|---|---|---|
|name|地图名称|```var name = map.name;//de_dust2```|(String)|
|mode|当前的游戏模式|```var mode = map.mode;//competitive```|(String) competitive/deathmatch/etc...|
|phase|当前的游戏阶段|```var phase = map.phase;```|(String) warmup/live/intermission/gameover|
|round|已经玩了多少回合，而不是哪个|```var round = map.round;```|(int) 0-15|
|num_matches_to_win_series|赢得系列赛需要多少场比赛|```var need = map.num_matches_to_win_series;```|(int)|
|current_spectators|当前现场观众人数|```var spec = map.current_spectators;```|(int)|
|souvenirs_total|掉落的纪念品数量(majors)|```var souv = map.souvenirs_total;```|(int)|

### 回合
|Property|描述|例子|值|
|---|---|---|---|
|phase|回合阶段|```var phase = round.phase;```|(字符串) freezetime/live/over|
|win_team|获胜的一方|```var win_team = round.win_team;```|(字符串) CT/T|
|bomb|炸弹状态|```var bomb = round.bomb;```|(字符串) exploded/defused/planted 或 (NULL)|

### 队伍
|Property|描述|例子|值|
|---|---|---|---|
|score|队伍得分|```var score_ct = team.score;```|(整数) 0-16 无 OTs|
|name|队伍名字|```var name_t = team.name;```|(字符串)|
|flag|队伍国旗|```var flag_ct = team.flag;```|(字符串) ISO 3166 国家代码|
|timeouts_remaining|队伍剩余暂停时间|```var timeouts_t = team.timeouts_remaining;```|(整数)|
|matches_won_this_series|该队伍在本系列赛中获胜的比赛数|```var won_ct = team.matches_won_this_series;```|(整数)|
|equip_value|团队的设备价值|```var ct_value = team.equip_value;```|(整数)|
|team_money|队伍玩家的资金总额|```var ct_money = team.team_money;```|(整数)|

### 阶段
|Property|描述|例子|值|
|---|---|---|---|
|phase|队伍的分数|```var phase = phase.phase;```|(String) freezetime/live/over/bomb/defuse/paused/timeout_t/timeout_ct|
|phase_ends_in|队伍的名称|```var time = phase.phase_ends_in;//"8.9"```|(字符串) 带小数点的时间 (秒)|

### 否决权
|Property|描述|例子|值|
|---|---|---|---|
|teams.team_3.logo|LOGO 队伍一 地图否决权||(字符串) team 1|
|teams.team_4.logo|LOGO 队伍二 地图否决权||(字符串) team 2|
........
|match.map.score_map_1|分数一 地图否决权||(整数) 0-100|
|match.map.score_map_2|分数二 地图否决权||(整数) 0-100|
........

# 对数据库的API请求
### 玩家对象例子
```json
{
    "sid":"76561198029090368",
    "real_name":"Hubert Walczak",
    "displayed_name":"osztenkurden",
    "country_code":"Poland",
    "team":"MT3xr6mb37o8Vbe3"
}
```
### 队伍对象例子
```json
{
    "team_name":"SK Gaming",
    "short_name":"sk",
    "country_code":"Brazil",
    "logo":"logo-1527775279488.png"
}
```
### HUD对象例子
```json
{
    "name":"default",
    "enabled":false
}
```

|网址|方法|请求正文|响应|
|---|--|--|---|
|`/api/players`|获取||`{players:[Array of Player objects with unique _id property]}` 或者 `Status 500`|
|`/api/players`|发布|`Player object`| `{id:String}`, 指定新的唯一 _id或者状态 `500`|
|`/api/players`|补丁|`Player object with _id property`|状态 `200` 或者 `500`|
|`/api/players`|删除|`{userId: String}`|状态 `200` 或者 `500`|
|`/api/teams`|获取||`{players: [Array of Player objects with unique _id property]}` 或者 `Status 500`|
|`/api/teams`|发布|`FormData` 包含字段的对象: team_name, short_name, country_code, logo| `{id:String}`, 指定新的唯一 _id或者状态 `500`|
|`/api/teams`|补丁|`FormData` 包含字段的对象: team_name, short_name, country_code, logo|状态 `200` 或者 `500`|
|`/api/teams`|删除|`{teamId: String}`|状态 `200` 或者 `500`|
|`/api/teams_logo`|删除|`{teamId: String}`|状态 `200` 或者 `500`|
|`/api/huds`|获取||`{players: [Array of HUD objects with unique _id property]}` 或者 `Status 500`|
|`/api/huds`|发布|`{id: String, enabled: Boolean}`|状态 `200` 或者 `500`|

## Credits

- [osztenkurden](https://github.com/osztenkurden) - Original Repo Creator [link](https://github.com/osztenkurden/Custom-CSGO-HUD)
- [boldgolt](https://github.com/boltgolt) - Radar on hud [link](https://github.com/boltgolt/boltobserv)
- As I mentioned before, [RedSparr0w](https://github.com/RedSparr0w) is the man I wouldn't make it without.
- [Bre3n](https://github.com/Bre3n) - No original Overlay CSGO HUD [link](https://github.com/Bre3n/CSGO)
- [JohnTimmermann](https://github.com/JohnTimmermann) - Fix Couch [link](https://github.com/JohnTimmermann/Custom-CS2-HUD)


## 许可证

这个项目是根据GPL-3许可的。对这个项目的任何改变都需要开源(除其他外)。允许分发，但必须是开放的(不是封闭的或者付费的)。

以上部分不是法律建议，不具有法律约束力。请查看存储库中的许可证文件以获得完整的许可证。

## FYFLO的HUD说明

关于购买FYFLO的HUD的问题，你需要发邮件给FYFLO。fyflostream@yandex.ru。FYFLO只会接俄罗斯联邦的HUD定制。
