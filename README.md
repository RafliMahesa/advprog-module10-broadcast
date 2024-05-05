## 2.1. Original code of broadcast chat.

![3 Client with 1 Server](image.png) <br>
Berdasarkan lampiran gambar diatas, terlihat bahwa masing-masing dari ketiga client tersebut mengirim pesan. Pada gambar tersebut juga terlihat bahwa server akan menerima pesan dari masing-masing client dan mengirimnya kembali ke semua client. Langkah-langkah yang saya lakukan untuk menjalankan program tersebut seperti pada gambar adalah membuka 4 terminal. Lalu untuk 3 terminal melakukan command `cargo run --bin client` untuk membuat 3 client dan untuk 1 terminal melakukan command `cargo run --bin server` untuk menjadi server. Nantinya, terminal yang berperan sebagai client bisa dilakukan pengetikan pesan untuk kemudian dikirimkan. <br>

## 2.2. Modifying the websocket port

Berikut perubahan yang saya lakukan pada `src/bin/server.rs` <br>
![8080 on Server](image2.png) <br>

Berikut perubahan yang saya lakukan pada `src/bin/client.rs` <br>
![8080 on Client](image3.png) <br>

Berdasarkan kode pada `src/bin/server.rs` dan `src/bin/client.rs` dapat terlihat menggunakan protokol WebSocket yang sama, yang dikelola oleh library `tokio_websockets`. Dengan ini, dipastikan bahwa agar kedua sisi yaitu baik client maupun server dapat berkomunikasi dengan protokol yang konsisten dan terdefinisi dengan baik. <br>

Lalu dapat terlihat juga pada foto dibawah ini bahwa program masih berjalan dengan baik walaupun port yang digunakan sudah dirubah. <br>
![Coba run](image4.png) <br>

## 2.3. Small changes. Add some information to client

Berikut hasil setelah dilakukan perubahan pada output <br>
![Using hostname](image5.png) <br>

Berikut modifikasi yang saya lakukan: <br>
![Perubahan 1](image6.png) <br>
![Perubahan 2](image7.png) <br>
![Perubahan 3](image8.png) <br>

Beberapa perubahan diatas yang saya lakukan untuk memberikan broadcast *addr* yang berisi addres dari mana pesan dikirim. Lalu, saya juga menambahkan asal dari komputer Rafli untuk beberapa pesan. <br>


