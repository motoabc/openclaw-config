# 权限收窄（限制访问范围）
chmod 600 /home/node/.openclaw/openclaw.json
chmod 600 /home/node/.openclaw/devices/paired.json


# 生成基线（首次部署或确认安全后执行）
sha256sum /home/node/.openclaw/openclaw.json > /home/node/.openclaw/.config-baseline.sha256
# 注：paired.json 被 gateway 运行时频繁写入，不纳入哈希基线（避免误报）
# 巡检时对比
sha256sum -c /home/zbb/.openclaw/.config-baseline.sha256


bash /mnt/openclaw/scripts/nightly-security-audit.sh 