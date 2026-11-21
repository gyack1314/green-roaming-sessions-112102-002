# 原始资料约定

区间左闭右开，时间包含偏移。station_alias.csv 用 operator/local/connector/有效期定位 port。telemetry.jsonl 中 start/stop 是服务边界，sample 是累积 Wh 观测，session 只在运营商内唯一。bridges.csv 给出 port 在 from_boot 到 to_boot 时的旧新计数器对应。
authorizations.jsonl 给出服务商授权。cdr.jsonl 的 parts 为 session/start/end/amount_minor 的明确分项；未给分项金额不可推算。confirmation 针对 operator/cdr/revision 和 accepted_parts；party=operator/provider，status=accept/reject。claims.jsonl 是人工输入，包括候选和选中身份。只有新版本明确 supersedes 才替代旧 CDR。
bridges.csv 是已登记的有效交接；updates/bridges.jsonl 撤回指定交接的现行证据。原会话的原始采样仍保留，不等于删除发生过的电量。

所有名称与数值均为本地合成数据，不代表真实企业、监管结论或生态调查。data/catalog.json 保存文件哈希、原始行数与列；data/updates/ 为后到修订资料，可独立接收。JSON null 表示尚无该值，不与数值零等同；CSV保留原字符串，金额和数量应按十进制解释。来源身份相同且内容相同的重送不产生新业务事实，同身份版本不同内容需保留争议，除明确替代关系外不按到达顺序判定权威。
