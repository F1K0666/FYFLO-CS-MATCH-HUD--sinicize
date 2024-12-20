# FYFLO-CS-赛事-HUD-汉化
原作者:fyflo，本项目是CS赛事UI，汉化由F1K0完成。

后面的代码项翻译可能不太准确，如果是会的老登可以去原文看看。
[原文地址](https://github.com/fyflo/CS-CS2-CSGO-HUDS-Observer-fyflo)

[原作者twitch](https://www.twitch.tv/fyflo)
[汉化作者哔哩哔哩账号](https://space.bilibili.com/1244247113)
[原作者DISCORD](https://discord.com/channels/392006529206976512/1315714438187323524)
[聊天QQ群](https://qm.qq.com/cgi-bin/qm/qr?k=YOEMEy-Wua8lnaPlQ2O13CHggFL77qTm&jump_from=webapi&authKey=0MIOvc4P6/yWUcHJcu1UfFQDyzFsJPmTfXZSGRbqQavgRNEEdF3d9LZxueHj0U2P)

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
|`getTeamOne()`|关于管理面板中定义的第1一个队伍的信息|`var teamOne = data.getTeamOne();`|JSON:`{team_name: "SK Gaming", short_name: "sk", country_code: "Brazil", logo: "logo-1527775279488.png", _id: "MT3xr6mb37o8Vbe3"}`|
|`getTeamTwo()`|关于管理面板中定义的第2个队伍的信息|`var players = data.getTeamTwo();`|如上所述|
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
	var player = data.getObserved(); // Getting spectated players object
    var teamLeft = data.getTeamOne(); // Team 1's informations
    var teamRight = data.getTeamTwo(); // Team 2's informations
    
    var round = data.round();
    
    // Setting teams' names
    $("#team_one_name").html(teamLeft.team_name); 
    $("#team_two_score").html(teamRight.team_name);
    // Those might be null if none specified, then use getT() and getCT() 
    
    //Setting teams' flag
    if(teamLeft.country_code){
        $("#team_1 #team_flag").css("background-image", "url('/files/img/flags/"+teamLeft.country_code + ".png')");
    }
    if(teamRight.country_code){
        $("#team_2 #team_flag").css("background-image", "url('/files/img/flags/"+teamRight.country_code + ".png')";
    }
    
    var playerlist = data.getPlayers(); // Array of player objects
    if(playerlist){
        for(var steamid in playerlist){
        	/* Actions here will be taken for each player */
            let player = playerlist[steamid];
            
            let displayed_name = player.name;
            let real_name = player.real_name; // If real name isn't set, it will show player.name
        }
    }
    
    
}
```

## Objects
### Player

Properties


|Property|Description|Example|Values|
|---|---|---|---|
|name|Player's steam name|```var name = player.name;//OLOF```|(String)|
|real_name|Player's real name, if set up in panel|```var real_name = player.name;//Olof Kajbjer Gustafsson```|(String)|
|clan|Player's current shown clan tag|```var clan = player.clan;//fnatic```|(String) or (NULL)|
|observer_slot|Player's spectating number|```var slot = player.observer_slot;//3```|(int) 0-9|
|team|Player's side|```var team = player.team;//CT```|(String) CT/T|
|position|Player's current position on map|```var pos = player.position;//-663.10, -198.32, 16.03```|(String) x, y, z|
|steamid|Player's SteamID64|```var sid = player.steamid;//76561197988627193```|(String)|
|teamData|Player's personal team information, if set up in panel|```var team = player.teamData;```|(JSON):```{team_name: "SK Gaming", short_name: "sk", country_code: "Brazil", logo: "logo-1527775279488.png", _id: "MT3xr6mb37o8Vbe3"}```|

Example:
```javascript
function updatePage(data) {
	var player = data.getObserved(); //Getting spectated players object
    var name =  player.name; //Getting name of that player
    var slot = player.observer_slot; // Getting slot of that player
    
     if(player.team == "CT"){...}
}
```
Methods

|Method|Description|Example|Values|
|---|---|---|---|
|`getWeapons()`|List of player's weapons|```var weapons = player.getWeapons();```|(Array of Weapons)|
|`getCurrentWeapon()`|Player's active weapon|```var holding = player.getCurrentWeapon();```|(Weapon)|
|`getGrenades()`|Player's grenades|```var grenades = player.getGrenades();```|(Array of Weapons)|
|`getStats()`|Player's current statistics (list below)|```var stats = player.getStats();```|(Array)|

Statistics:



|Stat's name|Description|Example|Values|
|---|---|---|---|
|health|Player's health|```var health = player.getStats().health;```|(int) 0-100|
|armor|Player's kevlar|```var armor = player.getStats().armor;```|(int) 0-100|
|helmet|Player's helmet|```var helmet = player.getStats().helmet;```|(bool) True/False|
|defusekit|Player's defuse kit|```var def = player.getStats().defusekit;```|(bool) True/False or (NULL)|
|smoked|Level of being smoked|```var flashed = player.getStats().smoked;```|(int) 0-255 or (NULL)|
|flashed|Level of being flashed|```var flashed = player.getStats().flashed;```|(int) 0-255|
|burning|Level of being burned|```var burning = player.getStats().burning;```|(int) 0-255|
|money|Player's money|```var money = player.getStats().money;```|(int) From 0 and up|
|round_kills|Player's kills during round|```var round_kills = player.getStats().round_kills;```|(int) Usually 0-5|
|round_killhs|Player's kills with headshot during round|```var round_killhs = player.getStats().round_killhs;```|(int) Usually 0-5|
|equip_value|Value of player's equipment|```var equip_value = player.getStats().equip_value;```|(int) From 0 and up|
|kills|Player's kills|```var kills = player.getStats().kills;```|(int)|
|assists|Player's assists|```var assists = player.getStats().assists;```|(int)|
|deaths|Player's deaths|```var deaths = player.getStats().deaths;```|(int)|
|mvps|Player's MVPs|```var mvps = player.getStats().mvps;```|(int)|
|score|Player's point score|```var points = player.getStats().score;```|(int)|

Example:

```javascript
function updatePage(data) {
	var player = data.getObserved(); //Getting spectated players object
    var stats =  player.getStats();
    var weapons = player.getWeapons();
    
    $("#health_box").html(stats.health);
    
    for(var k in weapons){...}
    
    if(stats.defusekit !== true){
    	$("#defusekit").css("display", "hidden");
    }
}
```

### Weapon
|Property|Description|Example|Values|
|---|---|---|---|
|name|Weapon's asset name|```var name = weapon.name;//weapon_awp```|(String) weapon\_...|
|paintkit|Weapon's skin's asset name|```var skin = weapon.paintkit;//cu_medusa_awp```|(String)|
|type|Weapon's type|```var type = weapon.type;```|(String) Knife/Rifle/SniperRifle/Grenade|
|state|State of being equiped|```var state = weapon.state;```|(String) holstered/active|
|ammo_clip|Ammo in clip|```var clip = weapon.ammo_clip;```|(int)|
|ammo_clip_max|Max ammount of ammo in clip|```var maxclip = weapon.ammo_clip_max;```|(int)|
|ammo_reserve|Ammo outside of clip|```var res = weapon.ammo_reserve;```|(int)|

### Map
|Property|Description|Example|Values|
|---|---|---|---|
|name|Map's name|```var name = map.name;//de_dust2```|(String)|
|mode|Game's current mode|```var mode = map.mode;//competitive```|(String) competitive/deathmatch/etc...|
|phase|Game's current phase|```var phase = map.phase;```|(String) warmup/live/intermission/gameover|
|round|How many rounds has been played, not which is it|```var round = map.round;```|(int) 0-15|
|num_matches_to_win_series|How many matches needed to win series|```var need = map.num_matches_to_win_series;```|(int)|
|current_spectators|Number of current live spectators|```var spec = map.current_spectators;```|(int)|
|souvenirs_total|Number of dropped souvenirs (majors)|```var souv = map.souvenirs_total;```|(int)|

### Round
|Property|Description|Example|Values|
|---|---|---|---|
|phase|Round's phase|```var phase = round.phase;```|(String) freezetime/live/over|
|win_team|Side who's win|```var win_team = round.win_team;```|(String) CT/T|
|bomb|State of bomb|```var bomb = round.bomb;```|(String) exploded/defused/planted or (NULL)|

### Team
|Property|Description|Example|Values|
|---|---|---|---|
|score|Team's score|```var score_ct = team.score;```|(int) 0-16 without OTs|
|name|Team's name|```var name_t = team.name;```|(String)|
|flag|Team's flag|```var flag_ct = team.flag;```|(String) ISO 3166 Country Code|
|timeouts_remaining|Team's remaining timeouts|```var timeouts_t = team.timeouts_remaining;```|(int)|
|matches_won_this_series|Matches won this series by this team|```var won_ct = team.matches_won_this_series;```|(int)|
|equip_value|Equipment value of team|```var ct_value = team.equip_value;```|(int)|
|team_money|Sum of  team's players' money|```var ct_money = team.team_money;```|(int)|

### Phase
|Property|Description|Example|Values|
|---|---|---|---|
|phase|Team's score|```var phase = phase.phase;```|(String) freezetime/live/over/bomb/defuse/paused/timeout_t/timeout_ct|
|phase_ends_in|Team's name|```var time = phase.phase_ends_in;//"8.9"```|(String) Time (seconds) with decimal|

### VETO
|Property|Description|Example|Values|
|---|---|---|---|
|teams.team_3.logo|LOGO team 1 Map Veto||(String) team 1|
|teams.team_4.logo|LOGO team 2 Map Veto||(String) team 2|
........
|match.map.score_map_1|score 1 Map Veto||(int) 0-100|
|match.map.score_map_2|score 2 Map Veto||(int) 0-100|
........

# API Requests to databases
### Player object example
```json
{
    "sid":"76561198029090368",
    "real_name":"Hubert Walczak",
    "displayed_name":"osztenkurden",
    "country_code":"Poland",
    "team":"MT3xr6mb37o8Vbe3"
}
```
### Team object example
```json
{
    "team_name":"SK Gaming",
    "short_name":"sk",
    "country_code":"Brazil",
    "logo":"logo-1527775279488.png"
}
```
### HUD object example
```json
{
    "name":"default",
    "enabled":false
}
```

|URL|Method|Request body|Response|
|---|--|--|---|
|`/api/players`|GET||`{players:[Array of Player objects with unique _id property]}` or `Status 500`|
|`/api/players`|POST|`Player object`| `{id:String}`, specifying new unique _id or Status `500`|
|`/api/players`|PATCH|`Player object with _id property`|Status `200` or `500`|
|`/api/players`|DELETE|`{userId: String}`|Status `200` or `500`|
|`/api/teams`|GET||`{players: [Array of Player objects with unique _id property]}` or `Status 500`|
|`/api/teams`|POST|`FormData` object with fields: team_name, short_name, country_code, logo| `{id:String}`, specifying new unique _id or Status `500`|
|`/api/teams`|PATCH|`FormData` object with fields: team_name, short_name, country_code, logo|Status `200` or `500`|
|`/api/teams`|DELETE|`{teamId: String}`|Status `200` or `500`|
|`/api/teams_logo`|DELETE|`{teamId: String}`|Status `200` or `500`|
|`/api/huds`|GET||`{players: [Array of HUD objects with unique _id property]}` or `Status 500`|
|`/api/huds`|POST|`{id: String, enabled: Boolean}`| Status `200` or `500`|

## Credits

- [osztenkurden](https://github.com/osztenkurden) - Original Repo Creator [link](https://github.com/osztenkurden/Custom-CSGO-HUD)
- [boldgolt](https://github.com/boltgolt) - Radar on hud [link](https://github.com/boltgolt/boltobserv)
- As I mentioned before, [RedSparr0w](https://github.com/RedSparr0w) is the man I wouldn't make it without.
- [Bre3n](https://github.com/Bre3n) - No original Overlay CSGO HUD [link](https://github.com/Bre3n/CSGO)
- [JohnTimmermann](https://github.com/JohnTimmermann) - Fix Couch [link](https://github.com/JohnTimmermann/Custom-CS2-HUD)


## License

This project is Licensed under GPL-3. Any changesd to this project need to be made open source (among other things). Distribution is allowed, but must be open (not closed or behind paywall).

The section above is not legal advice and is not legally binding. See the LICENSE file in the repository for the full license.

## My HUD

On the issue of purchasing my HUD, you need to write to my mail. fyflostream@yandex.ru. Only for Russian Federation.
