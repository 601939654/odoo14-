# odoo14字段跟踪，消息通知机制
odoo14字段跟踪，消息通知机制



1、 添加依赖
'depends': [ 'mail']


2、 继承相应模型
_inherit = ['mail.thread', 'mail.activity.mixin'] 


3、 在form视图添加对于的消息机制所需要的字段（一般都是放在form最底下）
<div class="oe_chatter">
    <field name="message_follower_ids"/>
    <field name="activity_ids"/>
    <field name="message_ids"/>
</div>


4、 在具体需要监听的字段上添加监听的属性
tracking属性设置
例如：design_concept = fields.Html(string='设计理念', tracking=True)
之前的版本
track_visibility设置：可设置两个值：onchange和always
14版本都统一为tracking=True

