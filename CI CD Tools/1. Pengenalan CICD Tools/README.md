# CI/CD

## Pengertian CI/CD

CI/CD (Continuous Integration Continuous Deployment) CI/CD adalah pendekatan dalam pengembangan perangkat lunak yang bertujuan untuk secara otomatis mengintegrasikan kode yang dikembangkan oleh tim pengembang, melakukan serangkaian pengujian otomatis, dan kemudian menerapkan perubahan kode ke berbagai environment secara berkelanjutan.

Continuous Integration (CI) adalah proses di mana setiap kali pengembang melakukan perubahan pada kode, perubahan tersebut diintegrasikan ke dalam repositori bersama dengan kode yang sudah ada. Setelah integrasi dilakukan, CI akan menjalankan automation test untuk memastikan bahwa perubahan tersebut tidak menyebabkan masalah atau kerusakan pada aplikasi.

Continuous Deployment (CD) adalah langkah selanjutnya setelah CI. Setelah perubahan kode melewati serangkaian tes dan dianggap siap untuk diterapkan, perubahan tersebut secara otomatis diterapkan ke berbagai environmet. Dengan menggunakan otomatisasi dalam proses ini, perubahan dapat cepat diterapkan dan aplikasi dapat segera tersedia bagi pengguna.

CI/CD membantu meningkatkan efisiensi dan kualitas dalam pengembangan perangkat lunak. Dengan menerapkan pendekatan ini, tim pengembang dapat secara teratur dan cepat mengintegrasikan perubahan, mengidentifikasi masalah dengan cepat, dan memperbaiki masalah tersebut sebelum merilis ke lingkungan produksi. Hal ini memungkinkan pengembang untuk merespons permintaan pelanggan dengan cepat dan memberikan perangkat lunak yang lebih handal dan stabil kepada pengguna akhir.

Proses CI/CD mengacu ke SDLC (Software Development Life Cycle) dengan 8 langkah yang membentuk infinity loop karena terus berulang, langkah tersebut diantaranya :

<img width="500" alt="Screen Shot 2022-05-11 at 15 08 20" src="https://user-images.githubusercontent.com/38523284/167800689-fb03ef06-e97a-4475-aa1b-4d0ac6756c8d.png">


1. Code
2. Build
3. Test
4. Release
5. Deploy
6. Operate
7. Monitor
8. Plan

Dengan meningkatnya untuk mengadopsi praktik agile, beberapa tools CI/CD telah banyak dirilis dalam beberapa tahun terakhir. Ini sering menyebabkan kebingungan dan menyulitkan seorang engineer perangkat lunak yang bercita-cita tinggi untuk memilih tools CI/CD terbaik untuk dikuasai bagi perkembangan karier.

-----

## Macam - macam CI/CD yang biasa digunakan :

### 1. Gitlab CI
Gitlab CI merupakan CI tools yang khusus dibuat oleh gitlab yang sangat mudah. Untuk menjalankan gitlab CI hanya butuh membuat file .gitlab-ci.yml. Gitlab CI menyediakan layanan gratis dengan batasan tiap bulanya.

### 2. Jenkins
Diklasifikasikan di antara tools CI/CD terbaik yang tersedia saat ini, Jenkins adalah tools berbasis open source, lintas platform, dan berbasis Java yang memungkinkan pengguna untuk menguji dan melaporkan secara real time. Jenkins dapat diinstall secara manual di infrastruktur yang kita punya.

### 3. Github Action
Seperti gitlab CI, github action juga merupakan CI/CD tools bawaan dari github. Github action juga menyediakan layanan gratis dengan batasan tiap bulanya.

### 4. AWS CodePipeline
[AWS CodePipeline](https://aws.amazon.com/id/codepipeline/)
Merupakan salah satu layanan AWS yang dapat membantu dalam pengotomatisasian pembaruan aplikasi dan infrastruktur dengan cepat. Mengotomatisasi fase build, pengujian dan deploy.

### 5. AWS CodeDeploy
[AWS CodePipeline](https://aws.amazon.com/id/codedeploy/)
Merupakan layanan AWS yang mengotomatiskan penerapan perangkat lunak untuk berbagai layanan komputasi antara lain Amazon EC2, AWS Fargate, AWS Lambda, dan server yang dijalankan di lokasi

### 6. AWS CodeBuild
[AWS CodePipeline](https://aws.amazon.com/id/codebuild/)
Merupakan layanan integrasi berkelanjutan yang sepenuhnya terkelola untuk mengompilasi kode sumber, menjalankan pengujian, dan menghasilkan paket perangkat lunak yang siap digunakan


-----

## Istilah yang perlu diketahui
### 1. SCM (Source Code Management)
Merupakan salah satu tools yang digunakan sebagai lokasi penyimpanan script code, jadi developer dapat saling berkolaborasi dalam proses developing aplikasi

### 2. Pipeline
Merupakan suatu cara yang digunakan untuk melakukan sejumlah kerja secara bersamaan tetapi dalam tahap yang berbeda yang dialirkan secara kontiniu pada unit pemrosesan 
