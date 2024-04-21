# Tutorial for Advance Programming Course 2023/2024

**Nama** : **Restu Ahmad Ar Ridho** <br/>
**NPM** : **2206028951** <br/>
**Kelas** : **Advance Programming - A**

## Module 8 - Software Architectures
1. How many data your publisher program will send to the message broker in one run?  
    Berdasarkan kode yang disediakan, program Publisher akan mengirimkan lima pesan ke broker pesan dalam satu kali proses. Setiap pemanggilan ke `p.publish_event` akan mengirimkan satu pesan. Setiap pesan adalah sebuah instance dari `UserCreatedEventMessage` dengan nilai `user_id` dan `user_name` yang berbeda, dan semuanya dipublikasikan ke antrean "user_created".
2. The url of: `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?  
    URL `amqp://guest:guest@localhost:5672` adalah sebuah string koneksi yang digunakan untuk menyambung ke sebuah message broker yang menggunakan protokol AMQP.
    Jika URL ini sama pada program Publisher dan Subscriber, itu berarti kedua program tersebut menyambung ke message broker yang sama.
    - `guest:guest` adalah nama pengguna dan kata sandi yang digunakan untuk autentikasi.
    - `localhost` adalah nama host atau alamat IP dari mesin di mana message broker berjalan. Dalam kasus ini, ia berjalan pada mesin yang sama dengan klien.
    - `5672` adalah nomor port di mana message broker mendengarkan. Ini adalah port default untuk RabbitMQ, sebuah message broker populer yang menggunakan AMQP.

    Jadi, baik penerbit dan pelanggan berinteraksi dengan message broker yang sama, mungkin menerbitkan dan mengkonsumsi pesan dari antrian yang sama.

#### Running RabbitMQ
![RabbitMQ](src\images\rabbitmq.png)
> Tampilan awal pada RabbitMQ

![Console](src\images\console.png)
> Publisher mengirimkan pesan ke RabbitMQ, dan Subscriber mengkonsumsi dan memproses pesan-pesan ini, seperti yang ditunjukkan pada console. Ini menunjukkan fungsionalitas dasar dari Publisher-Subsriber yang menggunakan RabbitMQ sebagai perantara pesan.

![Spike RabbitMQ](src\images\spikerabbitmq.png)
> Dengan mengamati kenaikan pada grafik RabbitMQ ketika menjalankan publisher berulang kali, hal ini menunjukan secara visual bagaimana aktivitas publisher berdampak pada antrian pesan di RabbitMQ. Hal ini membantu dalam memahami antrian pesan dan pemrosesan dalam menggunakan RabbitMQ.

