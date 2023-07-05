## Pengertian Docker

Docker adalah platform open-source yang digunakan untuk mengelola kontainer aplikasi. Kontainer adalah unit terisolasi yang mengemas aplikasi beserta dependensinya dan menjalankannya di lingkungan yang konsisten di berbagai sistem operasi.

Docker memanfaatkan fitur virtualisasi tingkat OS (operating system-level virtualization) yang disebut "containerization" untuk mengisolasi aplikasi dalam kontainer. Setiap kontainer berjalan secara independen, tetapi berbagi kernel host yang sama, yang membuatnya lebih ringan dan efisien dibandingkan dengan virtual machine (VM) tradisional.

Perbedaan antara container dan mesin virtual (virtual machine/VM) terletak pada pendekatan virtualisasi yang digunakan.

Virtual Machine (VM) adalah replika virtual dari sistem operasi yang berjalan di atas host fisik. Setiap VM memiliki sistem operasi yang lengkap, termasuk kernel, driver, dan aplikasi. VM menjalankan isolasi penuh antara satu sama lain, sehingga setiap VM dapat menjalankan sistem operasi yang berbeda. Setiap VM juga memerlukan sumber daya yang signifikan, seperti memori, prosesor, dan ruang penyimpanan.

Di sisi lain, kontainer adalah lingkungan yang terisolasi secara logika di dalam sistem operasi yang sama. Kontainer menggunakan fitur virtualisasi tingkat OS (operating system-level virtualization), yang memanfaatkan fitur seperti cgroups dan namespaces di Linux. Kontainer berbagi kernel host dan menggunakan layering file sistem untuk menyediakan isolasi dan lingkungan yang terpisah. Kontainer lebih ringan dan lebih cepat dibandingkan dengan VM karena mereka tidak perlu menjalankan sistem operasi yang lengkap, melainkan hanya membutuhkan dependensi yang diperlukan oleh aplikasi yang berjalan di dalamnya.

Dalam hal manfaatnya, kontainer lebih cepat untuk memulai, lebih efisien dalam penggunaan sumber daya, dan lebih mudah diatur dan didistribusikan. Mereka juga memungkinkan pengembang untuk mengemas aplikasi beserta dependensinya ke dalam unit yang portabel dan dapat dijalankan di lingkungan mana pun yang mendukung Docker atau teknologi kontainer lainnya.

Sementara itu, VM lebih fleksibel karena dapat menjalankan berbagai sistem operasi yang berbeda dan menawarkan isolasi yang lebih kuat antara VM yang berbeda.

Jadi, perbedaan utama antara kontainer dan VM adalah pendekatan virtualisasi yang digunakan, tingkat isolasi, dan penggunaan sumber daya.

### Container VS Visual Machine
| No | Container | Visual Machine |
| :--: | :------- | :------------ |
| 1 | Ringan | Berat |
| 2 | Ukuran Kecil | Ukuran Besar |
| 3 | Resource Fleksible | Resource Terbatas |
