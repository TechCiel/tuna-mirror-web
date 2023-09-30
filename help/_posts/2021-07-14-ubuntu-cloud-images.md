---
category: help
layout: help
mirrorid: ubuntu-cloud-images
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
<div class="z-help"><h1>Ubuntu Cloud Images</h1>
<p>收录官方的云 Ubuntu 镜像，由 Canonical 定制，提供 Ubuntu 认证镜像，可 Openstack、LXD 等的公共云上运行。</p>
<p>收录官方对 KVM，Hyper-v，XEN 等虚拟结构的官方定制镜像</p>
<p>使用以下链接进行查找所需要的镜像</p>
<div class="z-wrap"><form class="z-form" onchange="form_update(event)" onsubmit="return false"></form><pre class="z-code"></pre></div><tmpl>
{{endpoint}}/locator/
</tmpl><script id="z-config" type="application/x-mirrorz-help">eyJfIjogIlVidW50dSBDbG91ZCBJbWFnZXMiLCAiYmxvY2siOiBbInVidW50dS1jbG91ZC1pbWFnZXMiXSwgImlucHV0Ijoge30sICJuYW1lIjogInVidW50dS1jbG91ZC1pbWFnZXMifQ==</script>
</div>

{% endraw %}

<script src="/static/js/mustache.js?{{ site.data['hash'] }}"></script>
<script src="/static/js/zdocs.js?{{ site.data['hash'] }}"></script>
