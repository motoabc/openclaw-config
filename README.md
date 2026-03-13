# 权限收窄（限制访问范围）
chmod 600 /home/node/.openclaw/openclaw.json
chmod 600 /home/node/.openclaw/devices/paired.json


# 生成基线（首次部署或确认安全后执行）
sha256sum /home/node/.openclaw/openclaw.json > /home/node/.openclaw/.config-baseline.sha256
# 注：paired.json 被 gateway 运行时频繁写入，不纳入哈希基线（避免误报）
# 巡检时对比
sha256sum -c /home/node/.openclaw/.config-baseline.sha256


# 1) 解锁
docker exec -it -u root --privileged openclaw bash
chattr -i /home/node/.openclaw/workspace/scripts/nightly-security-audit.sh
chattr -i /opt/1panel/apps/openclaw/OpenClaw/data/workspace/scripts/nightly-security-audit.sh
# 2) 修改脚本
# 3) 测试：手动执行一次确认无报错
bash /home/node/.openclaw/workspace/scripts/nightly-security-audit.sh
# 4) 复锁
chattr +i /home/node/.openclaw/workspace/scripts/nightly-security-audit.sh
chattr +i /opt/1panel/apps/openclaw/OpenClaw/data/workspace/scripts/nightly-security-audit.sh