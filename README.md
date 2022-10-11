# **Membuat Microservice Sederhana**

## About
##### Menggunakan Maven Spring
##### Menggunakan Spring Boot versi 2.6.11
##### Menggunakan Apache NetBeans IDE 13
##### Menggunakan Bahasa Java
##### Menggunakan JDK 17
##### Menggunakan Browser Chrome

## Download Project Marven
**Langkah 1  :** <br>Buat project Maven menggunakan Spring Initializr https://start.spring.io/
<br>**Langkah 2  :** <br>Pilih Maven Project pada pilihan project dan java pada pilihan bahasa
<br>**Langkah 3  :**<br> Pilih Spring Boot versi 2.6.11 M6 atau versi yang lebih tinggi. Jangan memilih versi snapshot.
<br>**Langkah 3  :** <br>Berikan nama grup pada project yang telah dibuat yaitu com.raihanefelmaulana
<br>**Langkah 4  :** <br>Berikan id Artefak pada projeck yaitu latihan-service yang otomatis akan mengisi bagian name
<br>**Langkah 5  :** <br>Tambahkan description untuk project yang akan kita buat
<br>**Langkah 6  :**<br>Pilih 17 pada bagian java, pastikan sesuai dengan jdk yang ada di pc/laptop.
<br>**Langkah 7  :** <br>Tambahkan dependensi yaitu Spring Web
![image.png](https://drive.google.com/uc?export=view&id=1KWmreT8Eg7OfjCieYgQ7rTlJL0zg4ZnH)
<br>**Langkah 8  :** <br>Klik tombol Generate the project . File zip akan diunduh, ekstrak ke dalam hard disk.
<br>**Langkah 9  :**<br> Jalankan netbins lalu impor proyek pakar yang dibuat. Butuh beberapa waktu untuk mengunduh file yang diperlukan.
<br>**Langkah 10 :** <br>Lalu build and dependencies pada project yang sudah kita import
<br>**Langkah 11 :**<br> Sekarang jalankan LimitsServiceApplication, memulai Tomcat pada port (s) 8080 (http).

## Proyek Spring Boot
**Langkah 1 :** 
<br>  Menggunakan mulai.spring.io untuk membuat proyek "web". Dalam dialog "Dependenciesn" cari dan tambahkan Dependencies "web" seperti yang ditunjukkan pada tangkapan layar. Tekan tombol "Generate", unduh zip, dan buka kemasannya ke dalam folder di PC.
Proyek yang dibuat oleh start.spring.io berisi Spring Boot,framework yang membuat Spring siap bekerja di dalam aplikasi Anda, tetapi tanpa banyak kode atau konfigurasi yang diperlukan. Spring Boot adalah cara tercepat dan terpopuler untuk memulai proyek Spring.

**Langkah 2:**
Buka proyek di IDE Anda dan cari file LatihanServiceApplication.java di Source Packages pada folder com.raihanefelmaulana.latihan2service. Sekarang ubah isi file dengan menambahkan metode tambahan dan anotasi yang ditunjukkan pada kode di bawah ini. Anda dapat menyalin dan menempelkan kode atau cukup mengetiknya.
```java
package com.raihanefelmaulana.latihan2service;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
public class Latihan2ServiceApplication {

    public static void main(String[] args) {
        SpringApplication.run(Latihan2ServiceApplication.class, args);
    }

    @GetMapping("/hello")
    public String hello(@RequestParam(value = "name", defaultValue = "latihan2") String name) {
        return String.format("Hello %s!", name);
    }

}
```
Metode hello() yang di tambahkan dirancang untuk mengambil parameter String yang disebut name, dan kemudian menggabungkan parameter ini dengan kata "Hello"dalam kode. Ini berarti bahwa jika Anda menyetel name dengan “Latihan 2” dalam permintaan, responsnya adalah “Hello Latihan 2”.

Anotasi @RestController memberi tahu Spring bahwa kode ini menjelaskan titik akhir yang harus tersedia melalui web. @GetMapping(“/hello”) memberi tahu Spring untuk menggunakan method hello() untuk menjawab permintaan yang dikirim ke alamat http://localhost:8080/hello. Akhirnya, @RequestParamSpring memberi tahu Spring untuk mengharapkan nilai name dalam permintaan, tetapi jika tidak ada, itu akan menggunakan kata "Dunia" secara default.

**Langkah 4:**
<br>Run file LatihanService2Application.java.
![image.png](https://drive.google.com/uc?export=view&id=1cxnjhIrWvG6I2VT0jjxnx_0I1FgDNxIo )
Beberapa baris terakhir di sini memberi tahu kami bahwa Spring telah dimulai. Server Apache Tomcat tertanam pada Spring Boot bertindak sebagai server web dan mendengarkan permintaan pada localhost port 8010. Buka browser Anda dan di bilah alamat di bagian atas enter http://localhost:8081/halo. Anda harus mendapatkan respons ramah yang bagus seperti ini:
![image.png](https://drive.google.com/uc?export=view&id=16hlt3hGMuC36VWow6ZUU9PUe6KcQ7d-v)

