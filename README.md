wget  -N --no-check-certificate https://raw.githubusercontent.com/yyyyy1412/cloudflare-api-v4-ddns/master/cf-v4-ddns.sh

API key, see https://www.cloudflare.com/a/account/my-account,
这里填写上一步获取的CFKEY
CFKEY=
输入你需要解析用来DDNS解析的根域名 eg: example.com，比如我的域名是123.com，那么此处填写123.com
CFZONE=
登陆CF的Username, eg: user@example.com(即CF的登录邮箱)
CFUSER=
填写用来DDNS解析的二级域名，与上面设置的要一致, eg: ddns.yourdomain.com（例 ddns.123.com）
CFHOST=



给与权限
chmod +x cf-v4-ddns.sh
./cf-v4-ddns.sh


输入 crontab -e  然后会弹出 vi 编辑界面，在文件里面添加一行：
*/2 * * * * /root/cf-v4-ddns.sh >/dev/null 2>&1


\#如果您需要日志文件，输入下面命令
*/2 * * * * /root/cf-v4-ddns.sh >> /var/log/cf-ddns.log 2>&1
