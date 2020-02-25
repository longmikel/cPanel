# Quy trình điều chỉnh Webmail (Roundcube) sau khi nâng cấp phiên bản cPanel


## Plugins
Những ghi chú liên quan tới điều chỉnh plugins mặc định

### Return to Webmail
Không cho hiển thị logo cPanel trên mục Email Settings trong plugins (return to webmail)
frame: cp-logo-RGB-v42015.svg to cp-logo-RGB-v42015.svg.bak trong đường dẫn plugins/return_to_webmail/skins/larry/images/

### Header trong skins mặc định larry (những skins khi apply sẽ kế thừa cấu trúc header của skin larry)
skins/larry/includes/header.html
frame:
<!--div id="topline" role="banner" aria-labelledby="aria-label-topnav">
        <h2 id="aria-label-topnav" class="voice"><roundcube:label name="arialabeltopnav" /></h2>
        <div class="topleft">
                <roundcube:container name="topline-left" id="topline-left" />
                <roundcube:if condition="template:name != 'error'" />
                        <roundcube:button name="about" type="link" label="about" class="about-link" onclick="UI.show_about(this);return false" condition="!env:extwin" />
                <roundcube:endif />
                <roundcube:if condition="config:support_url" />
                <a href="<roundcube:var name='config:support_url' />" target="_blank" class="support-link" id="supportlink"><roundcube:label name="support" /></a>
                <roundcube:endif />
        </div>
        <roundcube:container name="topline-center" id="topline-center" />
        <div class="topright">
        <roundcube:container name="topline-right" id="topline-right" />
        <roundcube:if condition="!env:extwin &amp;&amp; !env:framed" />
                <span class="username"><roundcube:object name="username" /></span>
                <roundcube:button command="logout" label="logout" class="button-logout" />
        <roundcube:elseif condition="env:extwin" />
                <roundcube:button name="close" type="link" label="close" class="closelink" onclick="self.close()" />
        <roundcube:endif />
        </div>
</div-->

### Compose trong skin mặc định larry (những skins khi apply sẽ kế thừa cấu trúc compose của skin larry)
public_html/skins/larry/templates/compose.html
