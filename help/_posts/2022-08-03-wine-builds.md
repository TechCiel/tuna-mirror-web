---
category: help
layout: help
mirrorid: wine-builds
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
<div class="z-help"><h1>Wine builds 软件仓库</h1>
<p>由于上游并未提供 rsync，镜像站只同步了 ubuntu/debian 部分。</p>
<p>首先启用 32 位架构</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
{{sudo}}dpkg --add-architecture i386
</tmpl>
<p>之后信任来自 https://dl.winehq.org/ 的公钥</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
{{sudo}}wget -nc -O /usr/share/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key
</tmpl>
<p>新增 <code>/etc/apt/sources.list.d/winehq.list</code>，内容为</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"><div><label for="3eb0f615" title>发行版</label><select id="3eb0f615" name="release" title><option value="bookworm">Debian 12 (bookworm)</option><option value="bullseye">Debian 11 (bullseye)</option><option value="buster">Debian 10 (buster)</option><option value="jammy">Ubuntu 22.04 LTS (jammy)</option><option value="focal">Ubuntu 20.04 LTS (focal)</option><option value="bionic">Ubuntu 18.04 LTS (bionic)</option></select></div></form><pre class="z-code"></pre></div><tmpl z-input="release" z-path="/etc/apt/sources.list.d/winehq.list">

deb [arch=amd64,i386 signed-by=/usr/share/keyrings/winehq-archive.key] {{endpoint}}/{{os}}/ {{release}} main
</tmpl>
<p>通过以下命令安装 winehq</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
{{sudo}}apt update
{{sudo}}apt install --install-recommends winehq-stable
</tmpl><script id="z-config" type="application/x-mirrorz-help">eyJfIjogIldpbmUgYnVpbGRzIFx1OGY2Zlx1NGVmNlx1NGVkM1x1NWU5MyIsICJibG9jayI6IFsid2luZS1idWlsZHMiXSwgImlucHV0IjogeyJyZWxlYXNlIjogeyJfIjogIlx1NTNkMVx1ODg0Y1x1NzI0OCIsICJvcHRpb24iOiB7ImJvb2t3b3JtIjogeyJfIjogIkRlYmlhbiAxMiAoYm9va3dvcm0pIiwgIm9zIjogImRlYmlhbiJ9LCAiYnVsbHNleWUiOiB7Il8iOiAiRGViaWFuIDExIChidWxsc2V5ZSkiLCAib3MiOiAiZGViaWFuIn0sICJidXN0ZXIiOiB7Il8iOiAiRGViaWFuIDEwIChidXN0ZXIpIiwgIm9zIjogImRlYmlhbiJ9LCAiamFtbXkiOiB7Il8iOiAiVWJ1bnR1IDIyLjA0IExUUyAoamFtbXkpIiwgIm9zIjogInVidW50dSJ9LCAiZm9jYWwiOiB7Il8iOiAiVWJ1bnR1IDIwLjA0IExUUyAoZm9jYWwpIiwgIm9zIjogInVidW50dSJ9LCAiYmlvbmljIjogeyJfIjogIlVidW50dSAxOC4wNCBMVFMgKGJpb25pYykiLCAib3MiOiAidWJ1bnR1In19fX0sICJuYW1lIjogIndpbmUtYnVpbGRzIn0=</script>
</div>

{% endraw %}

<script src="/static/js/mustache.js?{{ site.data['hash'] }}"></script>
<script src="/static/js/zdocs.js?{{ site.data['hash'] }}"></script>
