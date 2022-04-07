# WebHookSpammer
A webhook spammer Using discordjs

- install
```js
npm install discord.js
```
```
const Content = ``; //สิ่งที่ต้องการจะส่ง
const webhookUrl = ``; //ลิ้ง webhook
const name = ``; //ชือ webhook
const avatar = ``; //โปรไฟล์ webhook

if(!Content || !webhookUrl) return console.log('Content or webhookUrl Not Found'); /*เช็คว่าเจอ content หรือ webhookUrl หรือไม่ ถ้าเป็นจริงจะรีเทิน ข้อความกลับโดยไม่ทำคำสั่งที่เหลือ*/
const { MessageEmbed, WebhookClient } = require('discord.js'); //ใช้โมดุลของ discord.js
const webhookClient = new WebhookClient({ url: webhookUrl }); //ตั้งค่าwebhookUrl

//const embed = new MessageEmbed().setTitle('I like Hee 2D').setColor('#0099ff');  //เป็นembed เป็นการส่่งข้อความอีกเเบบ

let i = 1; //ประกาศตัวเเปร
setInterval(() =>{ //คือ loop เเบบไม่มีที่สิ้นสุด
    webhookClient.send({
        content: Content, //ส่ง content
        username: name || null, //ส่ง username หรือ ไม่พบให้เป็น null
        avatarURL: avatar || null, //ส่ง avatar หรือ ไม่พบให้เป็น null
    });
    console.log(i); //เเสดงผลจำนวนการส่ง
    i++; // i = i +1
},1000); //เวลารอในการทำ้ำอีกครั้ง (millisecond)
```
