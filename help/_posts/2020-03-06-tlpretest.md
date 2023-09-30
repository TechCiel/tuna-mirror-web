---
category: help
layout: help
mirrorid: tlpretest
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
<div class="z-help"><h1>TeXLive Pretest 软件仓库</h1>
<p>tlpretest 是 TeX Live 在官方镜像之外发布的测试版本，详情可见 <a href="https://www.tug.org/texlive/pretest.html">官方介绍</a>。</p>
<p>在 TeX Live 官方版更新冻结期间（通常为每年 2 到 4 月），用户可以通过 tlpretest 提前获得新版本的 TeX Live 及其包含的宏包更新。</p>
<p>在命令行中执行：</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
tlmgr option repository {{endpoint}}
</tmpl>
<p>即可永久更改镜像源。</p>
<p>如果只需要临时切换，可以用如下命令：</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl z-lang="bash">
tlmgr update --all --repository {{endpoint}}
</tmpl>
<p>其中的 <code>update --all</code> 指令可根据需要修改。</p><script id="z-config" type="application/x-mirrorz-help">eyJfIjogIlRlWExpdmUgUHJldGVzdCBcdThmNmZcdTRlZjZcdTRlZDNcdTVlOTMiLCAiYmxvY2siOiBbInRscHJldGVzdCJdLCAiaW5wdXQiOiB7fSwgIm5hbWUiOiAidGxwcmV0ZXN0In0=</script>
</div>

{% endraw %}

<script src="/static/js/mustache.js?{{ site.data['hash'] }}"></script>
<script src="/static/js/zdocs.js?{{ site.data['hash'] }}"></script>
