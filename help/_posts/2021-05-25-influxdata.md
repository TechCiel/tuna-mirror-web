---
category: help
layout: help
mirrorid: influxdata
---

<!-- 本 markdown 从 tuna/mirrorz-help-ng 自动生成，如需修改，请修改其对应部分 -->

<style>.z-help tmpl { display: none }</style>

<div class="z-wrap">
    <form class="z-form z-global" onchange="form_update(null)" onsubmit="return false">
        <div>
            <label for="e0a5cecb">线路选择</label>
            <select id="e0a5cecb" name="host">
                <option selected="selected" value="{{ site.url }}">自动</option>
                <option value="{{ site.urlv4 }}">IPv4</option>
                <option value="{{ site.urlv6 }}">IPv6</option>
            </select>
        </div>
        <div>
            <input id="144d763c" name="_scheme" type="checkbox" checked>
            <label for="144d763c">是否使用 HTTPS</label>
        </div>
        <div>
            <input id="4659e7da" name="_sudo" type="checkbox">
            <label for="4659e7da">是否使用 sudo</label>
        </div>
    </form>
</div>
{% raw %}
<div class="z-help"><h1>Influxdata 软件仓库</h1>
<p>本目录是 <code>influxdb</code> ， <code>telegraf</code> 等时序型数据库的相关组件的镜像软件源。</p>
<h3>Debian / Ubuntu 用户</h3>
<p>首先信任来自 <a href="https://docs.influxdata.com/telegraf/v1.18/introduction/installation/">influxdata</a> 的 PGP 公钥：</p>
<p><em>注：Influxdata 在 2023-01-26 使用了新的 GPG 密钥，详情可参考<a href="https://www.influxdata.com/blog/linux-package-signing-key-rotation/">此处</a></em></p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
wget -q https://repos.influxdata.com/influxdata-archive_compat.key
cat influxdata-archive_compat.key | gpg --dearmor | {{sudo}}tee /etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg &gt; /dev/null
</tmpl>
<p>将下方文本框中的内容写入 <code>/etc/apt/sources.list.d/influxdata.list</code></p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-path="/etc/apt/sources.list.d/influxdata.list">
deb {{endpoint}}/debian/ stable main
</tmpl>
<p>即可安装相关软件，如：</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
{{sudo}}apt install influxdb
</tmpl>
<h3>CentOS / RedHat 用户</h3>
<h4>TUNA/BFSU/NJU 等</h4>
<p>新建 <code>/etc/yum.repos.d/influxdata.repo</code>，内容为</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"><div><label for="8df25a8a" title>发行版</label><select id="8df25a8a" name="release" title><option value="el7-x86_64">CentOS/RHEL 7 (x86_64)</option></select></div></form><pre class="z-code"></pre></div><tmpl z-input="release" z-lang="ini" z-path="/etc/yum.repos.d/influxdata.repo">
[influxdata]
name = InfluxData Repository - RHEL $releasever
baseurl={{endpoint}}/yum/{{release}}
enabled=1
gpgcheck=1
gpgkey=https://repos.influxdata.com/influxdata-archive_compat.key
</tmpl>
<h4>USTC</h4>
<p>新建 <code>/etc/yum.repos.d/influxdata.repo</code>，内容为</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="ini" z-path="/etc/yum.repos.d/influxdata.repo">
[influxdata]
name = InfluxData Repository - Stable
baseurl = {{endpoint}}/stable/$basearch/main
enabled = 1
gpgcheck = 1
gpgkey = https://repos.influxdata.com/influxdata-archive_compat.key
</tmpl>
<h4>共有部分</h4>
<p>再执行</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
{{sudo}}yum makecache
</tmpl>
<p>即可安装相关软件，如：</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
{{sudo}}yum install influxdb
</tmpl><script id="z-config" type="application/x-mirrorz-help">eyJfIjogIkluZmx1eGRhdGEgXHU4ZjZmXHU0ZWY2XHU0ZWQzXHU1ZTkzIiwgImJsb2NrIjogWyJpbmZsdXhkYXRhIl0sICJpbnB1dCI6IHsicmVsZWFzZSI6IHsiXyI6ICJcdTUzZDFcdTg4NGNcdTcyNDgiLCAib3B0aW9uIjogeyJlbDcteDg2XzY0IjogeyJfIjogIkNlbnRPUy9SSEVMIDcgKHg4Nl82NCkifX19fSwgIm5hbWUiOiAiaW5mbHV4ZGF0YSJ9</script>
</div>

{% endraw %}

<script src="/static/js/mustache.js?{{ site.data['hash'] }}"></script>
<script src="/static/js/zdocs.js?{{ site.data['hash'] }}"></script>
