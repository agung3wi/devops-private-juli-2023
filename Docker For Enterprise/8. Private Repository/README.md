## Private Repositori

hub.docker.com memberikan layanan gratis untuk private repository. Namun kita hanya bisa menyimpan satu image saja untuk private jika menggunakan layanan yang gratis. Ada beberapa layanan populer seperti Docker Hub, GitHub Container Registry, atau layanan cloud seperti Amazon Elastic Container Registry (ECR) atau Google Container Registry. Kita juga bisa menginstall repo sendiri di server.



### Membuat Repo di Server Sendiri

Untuk membuat repositori Docker pribadi yang dapat diinstal di server sendiri, dapat menggunakan Docker Registry. Docker Registry adalah perangkat lunak open-source yang memungkinkan untuk menjalankan repositori Docker pribadi di infrastruktur sendiri. Berikut adalah langkah-langkah umum untuk mengatur repositori Docker pribadi menggunakan Docker Registry:

1. Instal Docker Registry pada server yang ingin kita gunakan sebagai repositori Docker. kita dapat mengunduh perangkat lunak Docker Registry dari repositori resmi di GitHub: https://github.com/docker/distribution.

2. Konfigurasi Docker Registry. kita dapat mengedit file konfigurasi config.yml untuk mengatur opsi seperti port yang digunakan, keamanan, dan penyimpanan data. Pastikan untuk mengacu pada dokumentasi resmi Docker Registry untuk informasi lebih lanjut tentang opsi konfigurasi yang tersedia.

3. Setelah konfigurasi selesai, jalankan Docker Registry menggunakan perintah berikut:

```
docker run -d -p 5000:5000 --restart=always --name registry -v /path/to/registry/data:/var/lib/registry registry:2
```
Pastikan untuk mengganti /path/to/registry/data dengan direktori yang kita inginkan untuk menyimpan data repositori Docker.

4. Docker Registry sekarang akan berjalan di server kita pada port 5000. kita dapat mengonfigurasi Docker CLI agar dapat berinteraksi dengan repositori Docker pribadi ini dengan menambahkan konfigurasi berikut ke file ~/.docker/config.json pada mesin kita:

```
{
  "insecure-registries": ["your-registry-domain:5000"]
}
```
5. Ganti your-registry-domain dengan alamat IP atau nama domain server kita.

Sekarang kita dapat menggunakan perintah docker tag dan docker push untuk mengunggah image ke repositori Docker pribadi yang dijalankan oleh Docker Registry pada server kita.


### Create AWS ECR Repo
Untuk membuat private repositori di AWS ECR kita bisa menggunakan AWS CLI, dengan mengikuti langkah-langkah berikut:

1. Pastikan kita telah menginstal AWS CLI dan dikonfigurasi dengan akun AWS yang ingin kita gunakan untuk membuat repositori.

2. Buka terminal atau command prompt.

Jalankan perintah berikut untuk membuat repositori Docker di Amazon ECR:

```
aws ecr create-repository --repository-name <nama-repositori> --region <region>
```
Gantilah <nama-repositori> dengan nama yang ingin kita berikan pada repositori Docker kita, dan <region> dengan kode wilayah yang sesuai (misalnya us-east-1).

3. Contoh perintahnya adalah:

```
aws ecr create-repository --repository-name my-ecr-repo --region us-east-1
```
Setelah perintah dijalankan, kita akan menerima output yang berisi informasi tentang repositori yang telah dibuat, termasuk URL repositori dan konfigurasi lainnya.

4. Dengan menggunakan perintah di atas, kita dapat membuat repositori Docker pribadi di Amazon ECR melalui AWS CLI. Pastikan kita menggantikan <nama-repositori> dan <region> sesuai dengan preferensi kita.

### Push Image to AWS ECR

Untuk mengunggah (push) image Docker ke Amazon Elastic Container Registry (ECR) menggunakan AWS CLI, ikuti langkah-langkah berikut:

1. Login ke ECR.

```
aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.region.amazonaws.com
```

2. Build image Docker yang ingin kita unggah menggunakan perintah docker build.
   
3. Setelah image dibuild, beri tag pada image dengan menggunakan perintah docker tag. Format penamaan tag yang umum adalah <ECR-URL>/<nama-repositori>:<tag>. kita dapat menggantikan <ECR-URL> dengan URL repositori ECR yang sesuai, <nama-repositori> dengan nama repositori yang telah kita buat di ECR, dan <tag> dengan tag yang kita inginkan.

4. Contoh perintahnya adalah:

```
docker tag local-image:tag <ECR-URL>/<nama-repositori>:tag
```
Misalnya, jika URL repositori ECR adalah 123456789012.dkr.ecr.us-east-1.amazonaws.com dan nama repositori adalah my-ecr-repo, maka perintahnya akan menjadi:

```
docker tag local-image:tag 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-ecr-repo:tag
```

5. Jalankan perintah docker push untuk mengunggah image ke ECR:

```
docker push <ECR-URL>/<nama-repositori>:tag
```
Misalnya:

```
docker push 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-ecr-repo:tag
```

