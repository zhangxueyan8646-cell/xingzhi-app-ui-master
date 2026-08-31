# 行知专项 Skill 路由

需要多个专项 Skill 时，用本表确定各自负责范围；基础视觉始终由 `xingzhi-design-guidelines` 负责。

| 场景 | 主 Skill | 边界 |
|---|---|---|
| 首页、金刚区、首页信息流 | `xingzhi-home-page-guidelines` | 搜索提交后的结果页转 `xingzhi-search-results-guidelines` |
| 综合/主题/公司等搜索结果 | `xingzhi-search-results-guidelines` | 产业链图谱首页和详情转 `xingzhi-industry-chain-guidelines` |
| 产业链主题/公司图谱 | `xingzhi-industry-chain-guidelines` | 不等同于产业圈社区内容 |
| 产业圈、企业动态社区 | `xingzhi-industry-circle-guidelines` | 不负责上下游图谱和证券关系数据 |
| 研究内容、个股、月度金股 | `xingzhi-research-service-guidelines` | 机构研究服务申请转业务办理；超级 ETF 月报另用 ETF Skill |
| 超级 ETF 月报 | `xingzhi-super-etf-monthly-guidelines` | 不负责 ETF 搜索、交易、申赎或持仓 |
| 期货专区入口与研报 | `xingzhi-futures-zone-guidelines` | 云路演详情和播放状态转直播 Skill |
| 直播、云路演详情 | `xingzhi-live-page-guidelines` | 专区入口仍由对应专区 Skill 负责 |
| 活动落地与报名 | `xingzhi-landing-page-guidelines` | 空间首页/活动列表由空间 Skill；直播媒体状态由直播 Skill |
| 行知空间 | `xingzhi-space-guidelines` | 报名、身份和二维码凭证同时使用落地页 Skill |
| 投资理财、私募创造营 | `xingzhi-investment-wealth-guidelines` | 通用报名组件可组合落地页 Skill；ABS/REITs 转资管 Skill |
| 资管、ABS/REITs、文件权限 | `xingzhi-asset-management-guidelines` | 不负责私募管理人和创造营 |
| 业务办理与通用申请 | `xingzhi-business-processing-guidelines` | 专项业务的字段与状态仍由对应专项 Skill 负责 |
| 程序化交易协议与电子签署 | `xingzhi-programmatic-trading-guidelines` | 通用签署安全规则继承业务办理；不负责算法和订单 |
| 金创/衍生品、询券融券 | `xingzhi-derivatives-guidelines` | FICC 利率字段、账户与出金转 FICC Skill |
| FICC 固收、利率、账户、出金 | `xingzhi-ficc-fixed-income-guidelines` | 利率收益互换的订单生命周期可组合衍生品 Skill |
| 投行港股 IPO 簿记与配售 | `xingzhi-investment-bank-hk-guidelines` | 不等同于二级市场港股交易或普通投资产品 |
| 登录与内容访问认证 | `xingzhi-login-authentication-guidelines` | 横切能力；登录后内容继续由原业务 Skill 负责 |
| 个人中心、消息、联系人 | `xingzhi-personal-center-guidelines` | 进入具体业务记录后转对应业务 Skill |

## 通用组合规则

- 一个 Skill 负责页面外壳/入口，另一个负责进入后的专项流程时，按页面边界切换，不把两套外壳叠加。
- 横切 Skill（登录认证、业务办理、落地页报名）只负责其流程段，不覆盖业务字段、数据口径和合规文案。
- 搜索输入框由宿主页面负责；提交后的通用结果框架由搜索 Skill 负责；专项结果卡字段由对应业务 Skill 负责。
