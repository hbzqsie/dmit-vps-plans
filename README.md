# vps云服务器：DMIT 三大机房全套餐价格对比与 CN2 GIA 线路选择建议，建站、跨境、低延迟场景一次说清

如果你搜"vps云服务器"搜到了这里，大概率你不是在找一台最便宜的机器，而是在找一台**国内访问能跑得动、晚高峰不抽风、线路能说清楚来源**的 VPS。便宜的 VPS 满大街都是，但真到了给国内用户做站点、跑 API、做跨境业务的时候，国际 BGP 线路在晚高峰的丢包和绕路，会让人重新理解"便宜没好货"这句话。

DMIT 是一家 2017 年成立、总部在美国的 VPS 服务商，主打的就是中国大陆优化线路——CN2 GIA、CMIN2、AS9929 这些词在它的产品页上不是营销话术，而是真的对应不同的网络系列。它家产品不便宜，但线路质量在圈子里口碑相对稳定，经常出现热门套餐售罄的情况。这篇文章就围绕"vps云服务器"这个搜索意图，把 DMIT 当前的套餐结构、价格、线路差异、机房选择和优惠码一次说清楚，帮你判断它到底适不适合你的场景。

## 一、先搞清楚：DMIT 的三种网络系列到底差在哪

DMIT 把所有套餐按"网络系列"分类，而不是只按 CPU/内存分。这是它和其他 VPS 商最大的区别，也是你选套餐时第一个要做的决定。同一个机房、同一档配置，三种网络的价格能差出好几倍，原因就在线路。

**Premium Network（Pro 系列）**：DMIT 的旗舰线路，组合了 Tier 1 国际 transit、DMIT 自有骨干网，以及中国电信 CN2 GIA（AS23764）。官方描述是面向中国大陆和亚太地区提供最低延迟、最少跳数和最低丢包率的路由。简单说，电信回程走 CN2 GIA，联通和移动也有专门 peering（AS9929、CMI/CMIN2）。适合面向国内用户的企业站、电商、直播、低延迟游戏服务器这类对体验敏感的业务。价格最高。

**Eyeball Network（EB 系列）**：在 Tier 1 基础上叠加"reasonable effort"的中国路由优化，走 CMIN2/CMI 这类中国 eyeball ISP。它没有 Pro 那种 CN2 GIA 的硬保证，但对国内住宅用户的访问体验明显好于纯 Tier 1，价格只有 Pro 的一半左右。适合面向"全球为主、中国为辅"的混合受众，比如博客、API 后端、SaaS 平台、下载镜像。

**Tier 1 Network（T1 系列）**：纯国际 Tier 1 骨干网路由，不做任何中国大陆专门优化，走的是 Cogent、NTT、GTT、Arelion、Lumen 这些国际大厂的标准 transit。价格最便宜，年付最低 $36.9 起。适合备份、归档、CI/CD、监控、VPN 中继这类不需要对接国内用户、只关心带宽和跨区延迟的工作负载。

一句话总结：**如果你服务的对象在国内，按 Pro → EB → T1 的顺序选；如果完全不考虑国内访问，T1 性价比最高。**

## 二、三个机房怎么选：洛杉矶、香港、东京

DMIT 目前公开提供三个机房：洛杉矶（LAX）、香港（HKG）、东京（TYO）。每个机房都提供 Pro、EB、T1 三种网络系列，但配置和价格差异很大。

**洛杉矶（LAX）**：面向国内电信用户延迟最低的海外节点，三网回程 CN2 GIA，Pro 系列延迟通常在 140–180ms。也是 DMIT 套餐最全、价格梯度最开的机房，从年付 $36.9 的 T1 WEE 到月付 $619.99 的 Pro GIANT 都有。如果你做的是面向国内用户但又不想用香港/东京高价方案的业务，LAX.Pro 是最常见的选择。

**香港（HKG）**：延迟最低，到深圳参考延迟约 15–50ms，适合对延迟极敏感的场景。但香港 Pro 套餐流量给得少、价格高，HKG.Pro.TINY 月付就要 $39.90，只有 500GB 流量。香港 T1 反而和 LAX T1 价格一样（年付 $36.9 起），如果不走国内优化，香港 T1 是个低延迟的便宜选择。

**东京（TYO）**：到上海参考延迟约 30–60ms，介于香港和洛杉矶之间。东京 Pro 走 CN2 GIA/CTG GIA/CMI，对国内移动和联通用户体验不错。东京 T1 WEE 也是年付 $36.9 起，和 LAX/HKG T1 同价。

> 提示：DMIT 官方在 LAX AS3 系列页面注明，该平台仍在建设和优化中，期间可能出现磁盘性能下降和低于成熟平台的 SLA。如果你对稳定性要求高，下单前可以先确认你选的套餐是 AS3 还是 AN4/AN5 平台。

## 三、DMIT 全套餐对比表（2026 年当前官网价格）

下面这张表覆盖了 DMIT 官网当前公开展示的全部套餐，按机房和网络系列分组。价格均为官网公示的起步月付价（美元），T1 系列另有年付特价。流量为双向计入（BIDI 或 IN/OUT Max）。所有购买链接均为 AFF 推广链接。

### 洛杉矶 LAX.Pro（Premium / CN2 GIA）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.TINY | 1 vCore | 2GB | 20GB | 1000GB | 1Gbps | $10.90 | [查看 LAX.Pro.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=100) |
| LAX.Pro.Pocket | 2 vCore | 2GB | 40GB | 1500GB | 4Gbps | $16.90 | [查看 LAX.Pro.Pocket 套餐](https://www.dmit.io/aff.php?aff=18446&pid=137) |
| LAX.Pro.STARTER | 2 vCore | 2GB | 80GB | 3000GB | 10Gbps | $29.90 | [查看 LAX.Pro.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=56) |
| LAX.Pro.MINI | 4 vCore | 4GB | 80GB | 5000GB | 10Gbps | $58.88 | [查看 LAX.Pro.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=58) |
| LAX.Pro.MICRO | 4 vCore | 4GB | 160GB | 7000GB | 10Gbps | $74.99 | [查看 LAX.Pro.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=81) |
| LAX.Pro.MEDIUM | 6 vCore | 8GB | 160GB | 15000GB | 10Gbps | $199.90 | [查看 LAX.Pro.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=82) |
| LAX.Pro.LARGE | 8 vCore | 16GB | 320GB | 25000GB | 10Gbps | $338.88 | [查看 LAX.Pro.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=61) |
| LAX.Pro.GIANT | 12 vCore | 24GB | 640GB | 50000GB | 10Gbps | $619.99 | [查看 LAX.Pro.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=98) |

### 洛杉矶 LAX.EB（Eyeball / CMIN2）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.EB.TINY | 1 vCore | 2GB | 20GB | 1500GB | 2Gbps | $9.99 | [查看 LAX.EB.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=189) |
| LAX.EB.Pocket | 2 vCore | 2GB | 40GB | 3000GB | 4Gbps | $14.90 | [查看 LAX.EB.Pocket 套餐](https://www.dmit.io/aff.php?aff=18446&pid=190) |
| LAX.EB.STARTER | 2 vCore | 2GB | 80GB | 5000GB | 10Gbps | $29.90 | [查看 LAX.EB.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=191) |
| LAX.EB.MINI | 4 vCore | 4GB | 80GB | 10000GB | 10Gbps | $58.88 | [查看 LAX.EB.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=192) |
| LAX.EB.MICRO | 4 vCore | 4GB | 160GB | 14000GB | 10Gbps | $74.99 | [查看 LAX.EB.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=193) |
| LAX.EB.MEDIUM | 6 vCore | 8GB | 160GB | 30000GB | 10Gbps | $168.88 | [查看 LAX.EB.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=194) |
| LAX.EB.LARGE | 8 vCore | 16GB | 320GB | 50000GB | 10Gbps | $338.88 | [查看 LAX.EB.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=195) |
| LAX.EB.GIANT | 12 vCore | 24GB | 640GB | 100000GB | 10Gbps | $619.99 | [查看 LAX.EB.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=196) |

### 洛杉矶 LAX.T1（Tier 1 / 国际线路，年付特价）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 年付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.T1.WEE | 1 vCore | 1GB | 20GB | 1000GB | 1Gbps | — | $36.90/年 | [查看 LAX.T1.WEE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=71) |
| LAX.T1.TINY | 1 vCore | 1GB | 20GB | 2000GB | 1Gbps | $6.90 | — | [查看 LAX.T1.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=116) |
| LAX.T1.STARTER | 1 vCore | 2GB | 40GB | 4000GB | 1Gbps | $12.90 | — | [查看 LAX.T1.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=117) |
| LAX.T1.MINI | 2 vCore | 2GB | 60GB | 8000GB | 1Gbps | $21.90 | — | [查看 LAX.T1.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=118) |
| LAX.T1.MICRO | 4 vCore | 4GB | 80GB | 16000GB | 1Gbps | $32.90 | — | [查看 LAX.T1.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=119) |
| LAX.T1.MEDIUM | 4 vCore | 8GB | 160GB | 32000GB | 1Gbps | $49.90 | — | [查看 LAX.T1.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=120) |
| LAX.T1.LARGE | 8 vCore | 16GB | 320GB | 64000GB | 1Gbps | $99.90 | — | [查看 LAX.T1.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=121) |
| LAX.T1.GIANT | 8 vCore | 24GB | 640GB | 128000GB | 1Gbps | $199.90 | — | [查看 LAX.T1.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=122) |

### 香港 HKG.Pro（Premium / CN2 GIA）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.Pro.TINY | 1 vCore | 1GB | 20GB | 500GB | 1Gbps | $39.90 | [查看 HKG.Pro.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=123) |
| HKG.Pro.STARTER | 1 vCore | 2GB | 40GB | 1000GB | 1Gbps | $79.90 | [查看 HKG.Pro.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=124) |
| HKG.Pro.MINI | 2 vCore | 2GB | 60GB | 1500GB | 1Gbps | $119.90 | [查看 HKG.Pro.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=125) |
| HKG.Pro.MICRO | 4 vCore | 4GB | 80GB | 2000GB | 1Gbps | $159.90 | [查看 HKG.Pro.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=126) |
| HKG.Pro.MEDIUM | 4 vCore | 8GB | 160GB | 2500GB | 1Gbps | $179.90 | [查看 HKG.Pro.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=127) |
| HKG.Pro.LARGE | 8 vCore | 16GB | 320GB | 3000GB | 1Gbps | $239.90 | [查看 HKG.Pro.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=128) |
| HKG.Pro.GIANT | 8 vCore | 24GB | 640GB | 6000GB | 1Gbps | $499.90 | [查看 HKG.Pro.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=129) |

### 香港 HKG.EB（Eyeball / CMI）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.EB.TINYv2 | 1 vCore | 1GB | 20GB | 1000GB | 1Gbps | $29.90 | [查看 HKG.EB.TINYv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=210) |
| HKG.EB.STARTERv2 | 1 vCore | 2GB | 40GB | 2000GB | 2Gbps | $59.90 | [查看 HKG.EB.STARTERv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=211) |
| HKG.EB.MINIv2 | 2 vCore | 2GB | 60GB | 3000GB | 2Gbps | $89.90 | [查看 HKG.EB.MINIv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=212) |
| HKG.EB.MICROv2 | 4 vCore | 4GB | 80GB | 4000GB | 4Gbps | $129.90 | [查看 HKG.EB.MICROv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=213) |
| HKG.EB.MEDIUMv2 | 4 vCore | 8GB | 160GB | 6000GB | 4Gbps | $199.90 | [查看 HKG.EB.MEDIUMv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=214) |
| HKG.EB.LARGEv2 | 8 vCore | 16GB | 320GB | 12000GB | 4Gbps | $389.90 | [查看 HKG.EB.LARGEv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=215) |
| HKG.EB.GIANTv2 | 8 vCore | 24GB | 640GB | 24000GB | 4Gbps | $789.90 | [查看 HKG.EB.GIANTv2 套餐](https://www.dmit.io/aff.php?aff=18446&pid=216) |

### 香港 HKG.T1（Tier 1 / 国际线路，年付特价）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 年付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.T1.WEE | 1 vCore | 1GB | 20GB | 1000GB | 1Gbps | — | $36.90/年 | [查看 HKG.T1.WEE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=197) |
| HKG.T1.TINY | 1 vCore | 1GB | 20GB | 2000GB | 1Gbps | $6.90 | — | [查看 HKG.T1.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=198) |
| HKG.T1.STARTER | 1 vCore | 2GB | 40GB | 4000GB | 1Gbps | $12.90 | — | [查看 HKG.T1.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=199) |
| HKG.T1.MINI | 2 vCore | 2GB | 60GB | 8000GB | 1Gbps | $21.90 | — | [查看 HKG.T1.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=200) |
| HKG.T1.MICRO | 4 vCore | 4GB | 80GB | 16000GB | 1Gbps | $32.90 | — | [查看 HKG.T1.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=201) |
| HKG.T1.MEDIUM | 4 vCore | 8GB | 160GB | 32000GB | 1Gbps | $49.90 | — | [查看 HKG.T1.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=202) |
| HKG.T1.LARGE | 8 vCore | 16GB | 320GB | 64000GB | 1Gbps | $99.90 | — | [查看 HKG.T1.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=203) |
| HKG.T1.GIANT | 8 vCore | 24GB | 640GB | 128000GB | 1Gbps | $199.90 | — | [查看 HKG.T1.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=204) |

### 东京 TYO.Pro（Premium / CN2 GIA）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.Pro.TINY | 1 vCore | 1GB | 20GB | 500GB | 1Gbps | $21.90 | [查看 TYO.Pro.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=138) |
| TYO.Pro.STARTER | 1 vCore | 2GB | 40GB | 1000GB | 1Gbps | $39.90 | [查看 TYO.Pro.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=139) |
| TYO.Pro.MINI | 2 vCore | 2GB | 60GB | 2000GB | 1Gbps | $79.90 | [查看 TYO.Pro.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=140) |
| TYO.Pro.MICRO | 4 vCore | 4GB | 80GB | 4000GB | 1Gbps | $159.90 | [查看 TYO.Pro.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=141) |
| TYO.Pro.MEDIUM | 4 vCore | 8GB | 160GB | 5000GB | 1Gbps | $259.90 | [查看 TYO.Pro.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=142) |
| TYO.Pro.LARGE | 8 vCore | 16GB | 320GB | 8000GB | 1Gbps | $429.90 | [查看 TYO.Pro.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=143) |
| TYO.Pro.GIANT | 8 vCore | 24GB | 640GB | 15000GB | 1Gbps | $799.90 | [查看 TYO.Pro.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=144) |

### 东京 TYO.EB（Eyeball / CMI）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.EB.TINY | 1 vCore | 1GB | 20GB | 1000GB | 1Gbps | $25.90 | [查看 TYO.EB.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=221) |
| TYO.EB.STARTER | 1 vCore | 2GB | 40GB | 2000GB | 2Gbps | $55.90 | [查看 TYO.EB.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=222) |
| TYO.EB.MINI | 2 vCore | 2GB | 60GB | 3000GB | 2Gbps | $85.90 | [查看 TYO.EB.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=223) |
| TYO.EB.MICRO | 4 vCore | 4GB | 80GB | 4000GB | 4Gbps | $119.90 | [查看 TYO.EB.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=224) |
| TYO.EB.MEDIUM | 4 vCore | 8GB | 160GB | 6000GB | 4Gbps | $179.90 | [查看 TYO.EB.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=225) |
| TYO.EB.LARGE | 8 vCore | 16GB | 320GB | 12000GB | 4Gbps | $369.90 | [查看 TYO.EB.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=226) |
| TYO.EB.GIANT | 8 vCore | 24GB | 640GB | 24000GB | 4Gbps | $749.90 | [查看 TYO.EB.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=227) |

### 东京 TYO.T1（Tier 1 / 国际线路，年付特价）

| 套餐 | CPU | 内存 | SSD | 流量 | 端口 | 月付起 | 年付起 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.T1.WEE | 1 vCore | 1GB | 20GB | 1000GB | 1Gbps | — | $36.90/年 | [查看 TYO.T1.WEE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=228) |
| TYO.T1.TINY | 1 vCore | 1GB | 20GB | 2000GB | 1Gbps | $6.90 | — | [查看 TYO.T1.TINY 套餐](https://www.dmit.io/aff.php?aff=18446&pid=131) |
| TYO.T1.STARTER | 1 vCore | 2GB | 40GB | 4000GB | 1Gbps | $12.90 | — | [查看 TYO.T1.STARTER 套餐](https://www.dmit.io/aff.php?aff=18446&pid=132) |
| TYO.T1.MINI | 2 vCore | 2GB | 60GB | 8000GB | 1Gbps | $21.90 | — | [查看 TYO.T1.MINI 套餐](https://www.dmit.io/aff.php?aff=18446&pid=133) |
| TYO.T1.MICRO | 4 vCore | 4GB | 80GB | 16000GB | 1Gbps | $32.90 | — | [查看 TYO.T1.MICRO 套餐](https://www.dmit.io/aff.php?aff=18446&pid=134) |
| TYO.T1.MEDIUM | 4 vCore | 8GB | 160GB | 32000GB | 1Gbps | $49.90 | — | [查看 TYO.T1.MEDIUM 套餐](https://www.dmit.io/aff.php?aff=18446&pid=135) |
| TYO.T1.LARGE | 8 vCore | 16GB | 320GB | 64000GB | 1Gbps | $99.90 | — | [查看 TYO.T1.LARGE 套餐](https://www.dmit.io/aff.php?aff=18446&pid=136) |
| TYO.T1.GIANT | 8 vCore | 24GB | 640GB | 128000GB | 1Gbps | $199.90 | — | [查看 TYO.T1.GIANT 套餐](https://www.dmit.io/aff.php?aff=18446&pid=229) |

> 说明：以上价格均为官网公示的起步月付价，部分套餐另有季付、半年付、年付折扣。T1 系列的 WEE 套餐为年付专属特价产品，不参与月付。如果你需要直接浏览全部套餐并查看当前实时库存，可以 👉 [访问 DMIT 官方套餐页面](https://bit.ly/DmiT)。

## 四、当前可用的优惠码（2026 年）

DMIT 的优惠码大多是**循环折扣**（recurring），即每个计费周期都生效，不是只减一次。下面这些是当前多个公开渠道仍在更新的优惠码，使用前请在结账页面的"Validate Code"确认是否仍有效，因为 DMIT 会不定期下架或替换。

- **`LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF`**：LAX EB TINY 及以上，季付及以上周期，8 折循环。
- **`2025-TYO-T1-HI-GSL-NON-MONTHLY-30OFF`**：TYO T1 TINY，季付及以上，7 折循环。
- **`2025-TYO-T1-HI-GSL-MONTHLY-10OFF`**：TYO T1 TINY，月付，9 折。
- **`202510_HKG_TYO_PRO_20OFF_RECURRING`**：HKG Pro / TYO Pro，季付及以上，8 折循环。
- **`202510_HKG_TYO_T1_30OFF_RECURRING`**：HKG T1 / TYO T1（不含 WEE），季付及以上，7 折循环。
- **`Lite-Annually-Recur-30OFF`**：Standard（Lite）网络系列，年付，7 折。
- **`Lite-Semi-Annually-Recur-20OFF`**：Standard（Lite）网络系列，半年付，8 折。
- **`2025-TYO-PRO-HI-GSL-ANNUALLY-20OFF`**：TYO Pro 年付新单，20% 循环折扣（限量，售完即止，不可叠加）。

注意事项：所有优惠码仅限新订单使用，不适用于特价产品（如 T1 WEE 年付 $36.9 这类本身已经打折的套餐）；同一订单通常不可叠加多个折扣码；DMIT 保留随时调整或下架优惠码的权利。下单前最稳妥的做法是把候选优惠码贴进结账页验证一次。

## 五、几个实际场景下的套餐建议

光看价格表容易选花眼。下面按几个常见的"vps云服务器"使用场景，给出更具体的方向。

**场景一：给国内用户做企业站或电商，预算敏感**
首选 LAX.Pro.STARTER（2 核 2GB / 80GB SSD / 3000GB / 10Gbps，月付 $29.90）。三网回程 CN2 GIA，10Gbps 端口在晚高峰也能扛住突发流量。如果预算更紧，LAX.EB.STARTER 同配置但走 CMIN2，月付也是 $29.90，流量还给到 5000GB，对国内访问体验略逊于 Pro 但差距没有价格差距那么大，适合博客、轻量 SaaS。

**场景二：低延迟游戏服务器或实时 API，面向国内**
香港 HKG.Pro 是延迟最低的选择，到深圳参考延迟约 15ms。但 HKG.Pro 流量给得少，HKG.Pro.STARTER 月付 $79.90 只有 1000GB。如果业务流量不大但要求延迟极低，这笔钱花得值。如果对延迟没那么极致，TYO.Pro.STARTER 月付 $39.90、1000GB 流量，到上海参考延迟约 30ms，性价比更高。

**场景三：纯国际业务，不服务国内用户**
直接看 T1 系列。LAX.T1.TINY 月付 $6.90 起步，1 核 1GB / 20GB / 2000GB，跑个轻量 API 或监控完全够用。如果想年付省心，LAX.T1.WEE 年付 $36.9 是 DMIT 最便宜的入门方案，1 核 1GB / 20GB / 1000GB，适合做备份节点或测试环境。

**场景四：跨境团队协作、远程开发**
HKG.EB.STARTERv2（1 核 2GB / 40GB / 2000GB / 2Gbps，月付 $59.90）是个平衡选择。2Gbps 端口对远程 SSH 和文件同步够用，CMI 线路对国内移动用户友好，比 HKG.Pro 便宜近一半。如果团队主要在美洲，LAX.EB.MINI（4 核 4GB / 80GB / 10000GB / 10Gbps，月付 $58.88）配置更高、流量更大。

## 六、硬件平台：AN5 / AN4 / AS3 的区别

DMIT 当前在官网明确区分了三档硬件平台，这会影响你买到的实际性能。

- **AN5 系列**：AMD EPYC 9005（Zen 5）+ DDR5 + PCIe 5.0 NVMe，单核和多核性能最强，适合高流量站点、数据库、延迟敏感应用。官网 Geekbench 6 单核分数约 1728，是当前旗舰。
- **AN4 系列**：AMD EPYC 9004（Zen 4）+ DDR4，性能均衡稳定，是大多数通用工作负载的主力平台。
- **AS3 系列**：AMD EPYC 7003（Zen 3），最成熟的平台，单核价格比最优，适合预算敏感、测试环境、入门部署。官方已注明 LAX AS3 仍在优化中，磁盘性能和 SLA 可能低于成熟平台。

下单时如果套餐页没有明确标注平台，建议先和客服确认你买的是哪一代，特别是高配套餐，AN5 和 AS3 的实际体验差距不小。

## 七、几个下单前必须知道的限制

**退款政策**：DMIT 提供 3 天内全额退款（扣除支付网关手续费），前提是服务购买不超过 3 天且流量使用不超过 30GB。超过 3 天但不超过 30 天可申请部分退款，按已用流量或剩余服务时间折算（取较低值）。如果同一系列已退款 3 次、被 DDoS 攻击、网络体验不佳、IP 地理位置原因等，不予退款。

**IP 更换**：Premium 和 Eyeball 系列，未购买 IP Care+ 服务的情况下，月付或非月付都是每 15 天可免费更换一次；购买 IP Care+ 后每 7 天可换一次。Tier 1 系列不保证 IP 在所有国家可用（尤其中国、俄罗斯等有网络审查的地区），可加购 IP Guarantee+ 保证首次连接。任何情况下加 $5 可立即换 IP。

**SLA**：DMIT 当前只承诺 99% SLA。低于 99% 补偿半个月，低于 95% 补偿一个月，低于 90% 补偿两个月。

**支付**：支持 PayPal、信用卡、支付宝，对中国用户友好。但 DMIT 不接受来自古巴、伊朗、黎巴嫩、利比亚、缅甸、朝鲜、索马里、苏丹、叙利亚的订单（OFAC 限制）。

**服务性质**：DMIT 大部分服务是**非托管服务**，工单回复时效 72 小时内。这意味着服务器环境配置、安全加固、故障排查基本要自己搞定，不适合完全不懂 Linux 的小白。

## 八、关于"DMIT 到底值不值"的判断

回到"vps云服务器"这个搜索意图的核心：如果你只是想找一台最便宜的 VPS 跑点小东西，DMIT 不是你的最优解——市面上 $2/月、$3/月的国际 VPS 一抓一大把，配置还更高。

但如果你卡在"国内访问体验"这个点上，试过便宜 VPS 在晚高峰丢包丢到怀疑人生，那 DMIT 的价值就出现了：CN2 GIA 线路的稳定性、自有骨干网对路由的掌控力、不超售带来的性能一致性，这些都是它溢价的底气。圈内对 DMIT 的常见评价是"除了贵没有其他缺点"，这话虽然夸张，但反映了它的定位——它不是走量的商家，而是走质的。

具体到选择：**预算紧 + 不服务国内 → T1 系列**；**预算紧 + 要服务国内 → EB 系列**；**预算充足 + 体验优先 → Pro 系列**；**延迟敏感 → 香港 Pro 或东京 Pro**。把这三件事想清楚，再对照上面的全套餐表，基本就不会选错。

如果你已经确定方向，可以直接 👉 [前往 DMIT 套餐页面下单](https://bit.ly/DmiT)，结账时别忘了把上面列出的对应优惠码贴进去验证一下——能省一笔是一笔，循环折扣长期算下来差距不小。
