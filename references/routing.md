# 行知业务路由

Choose one primary skill for the host experience. Add a cross-cutting skill only for the page or flow segment it owns.

| Requirement scope | Primary skill | Cross-cutting boundary |
|---|---|---|
| 首页、金刚区、首页信息流 | `modules/xingzhi-home-page-guidelines/SKILL.md` | Search submission moves to search results |
| 综合、主题、公司等搜索结果 | `modules/xingzhi-search-results-guidelines/SKILL.md` | Domain result fields remain owned by their domain skill |
| 产业链主题、公司图谱、上下游关系 | `modules/xingzhi-industry-chain-guidelines/SKILL.md` | Not the industry-circle community |
| 产业圈、企业动态、活动与社区互动 | `modules/xingzhi-industry-circle-guidelines/SKILL.md` | Not upstream/downstream graph data |
| 研究服务、研报、个股、月度金股 | `modules/xingzhi-research-service-guidelines/SKILL.md` | Institution application moves to business processing |
| 超级 ETF 月报 | `modules/xingzhi-super-etf-monthly-guidelines/SKILL.md` | Does not own ETF trading or positions |
| 期货专区入口、期货研报与数据库 | `modules/xingzhi-futures-zone-guidelines/SKILL.md` | Live playback/detail moves to live pages |
| 直播、云路演、倒计时、回放 | `modules/xingzhi-live-page-guidelines/SKILL.md` | Zone entry remains with its host zone |
| 活动落地、策划会、报名、电子票 | `modules/xingzhi-landing-page-guidelines/SKILL.md` | Add business processing for materials/signing/review segments |
| 行知空间、空间预约与空间活动 | `modules/xingzhi-space-guidelines/SKILL.md` | Add landing pages for registration/credential segments |
| 投资理财、私募管理人、创造营 | `modules/xingzhi-investment-wealth-guidelines/SKILL.md` | ABS/REITs move to asset management |
| 资管、ABS/REITs、文件权限 | `modules/xingzhi-asset-management-guidelines/SKILL.md` | Private-fund manager/camp remains investment wealth |
| 业务办理、材料、身份、通用协议签署 | `modules/xingzhi-business-processing-guidelines/SKILL.md` | Specialized business fields remain with their host domain |
| QTM/QMT、程序化交易协议、电子签署记录 | `modules/xingzhi-programmatic-trading-guidelines/SKILL.md` | Inherit only generic signing safeguards from business processing |
| 金创、衍生品、询券、融券 | `modules/xingzhi-derivatives-guidelines/SKILL.md` | FICC rate/account/withdrawal fields move to FICC |
| FICC 固收、利率、账户、划转与出金 | `modules/xingzhi-ficc-fixed-income-guidelines/SKILL.md` | Derivative lifecycle may be combined for swap orders |
| 投行港股 IPO 簿记与配售 | `modules/xingzhi-investment-bank-hk-guidelines/SKILL.md` | Not secondary-market Hong Kong trading |
| 登录、验证码与内容访问认证 | `modules/xingzhi-login-authentication-guidelines/SKILL.md` | Cross-cutting only; return to the host domain after login |
| 个人中心、消息、联系人与客户 | `modules/xingzhi-personal-center-guidelines/SKILL.md` | Specific business records move to their domain skill |

## Combination rules

- Activity + commitment signing/upload/review: primary `xingzhi-landing-page-guidelines`, add `xingzhi-business-processing-guidelines` for signing, material and review segments.
- Host page + login interception: host domain remains primary; `xingzhi-login-authentication-guidelines` owns only interception and return-to-content.
- Host search box + result page: the host owns the input entry; `xingzhi-search-results-guidelines` owns the common result shell; the domain owns specialized result fields.
- Zone entry + live detail: the zone owns the entry; `xingzhi-live-page-guidelines` owns countdown, playback and replay pages.
- Never load every domain skill for a single request. If the PRD spans domains, route per page or per flow segment.
