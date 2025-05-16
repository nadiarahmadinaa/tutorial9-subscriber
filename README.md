# Reflection

## What is AMQP?
AMQP adalah singkatan dari Advanced Message Queueing Protocol. Standard open-source ini berperan sebagai middleware untuk secure encrypted messaging antar aplikasi dan organisasi. Dengan AMQP, komunikasi antar  sistem dengan beda bahasa dimungkinkan. Selain itu, AMQP juga support message queueing, routing, dan delivery guarantees. Contoh dari AMQP adalah RabbitMQ, yang digunakan pada tutorial ini.

## What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for?
Dalam string `amqp://guest:guest@localhost:5672`, amqp:// berlaku sebagai identifier protocol. Nilai guest pertama adalah username untuk autentikasi ke RabbitMQ (default value). Nilai guest kedua adalah default password untuk autentikasi ke RabbitMQ. Localhost adalah hostname dari AMQP server. 5672 adalah default port untuk RabbitMQ. Jadi keseluruhan string ini guna connect ke RabbitMQ pada localhost port 5672 dengan default credentials.

## Simulation slow subscriber
![Simulation slow subscriber](image/slow.png)
Queue pada screen ini di sekitar 75. Dari kode yang ditambahkan sleep, program menjadi lambat dalam menerima message. Banyaknya message dari sisi publisher dan kelambatan subscriber untuk menerima akan menghasilkan queue pada message broker. Message akan disimpan pada queue sampai bisa di-deliver ke subscriber dengan baik. Khususnya jika kita membuat request banyak dan cepat, queue akan semakin panjang.