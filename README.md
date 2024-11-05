# zero_pbp_mobile

## Tugas 7
#### Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.
1. Stateless Widget
Stateless widget adalah widget yang tidak memiliki status atau data yang bisa berubah setelah widget tersebut dibangun. Artinya, setiap kali widget tersebut dipanggil atau dirender ulang, widget tersebut akan selalu sama karena tidak tergantung pada perubahan status apapun. Biasanya digunakan untuk elemen UI yang tidak memerlukan interaksi atau perubahan setelah widget tersebut ditampilkan, seperti Text, Icon, atau Container yang hanya menampilkan elemen statis.

2. Stateful Widget
Stateful widget adalah widget yang memiliki status atau data yang bisa berubah setelah widget tersebut dibangun. Stateful widget dapat memperbarui dirinya sendiri ketika status atau data yang terkait berubah. Biasanya digunakan untuk widget yang memerlukan interaksi pengguna atau memiliki status yang berubah seiring waktu, seperti Checkbox, TextField, atau Slider.

#### Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.
- Scaffold:
Menyediakan struktur dasar halaman dengan AppBar dan body.
- AppBar:
Bagian atas halaman yang menampilkan judul aplikasi.
- Text:
Menampilkan teks pada layar.
- Container:
Widget serbaguna yang dapat digunakan untuk mengatur tata letak, ukuran, padding, dan dekorasi.
- Center:
Menyusun widget anak di tengah widget induk.
- Column:
Menyusun widget anak secara vertikal.
- Icon:
Menampilkan ikon dari pustaka ikon bawaan Flutter.
- Padding:
Menambahkan ruang di sekitar widget anak.
- SnackBar:
Menampilkan pesan sementara di bagian bawah layar.
- Card:
Menyediakan kotak dengan bayangan untuk menampilkan konten.
- MediaQuery:
Menyediakan informasi tentang ukuran dan orientasi layar.
- InfoCard:
Kartu informasi yang menampilkan judul dan konten.
- StatelessWidget:
Widget yang tidak memiliki state dan hanya perlu dibangun sekali.
- List:
Menyimpan daftar item yang digunakan dalam aplikasi.
- ItemHomepage:
Kelas yang digunakan untuk menyimpan informasi tentang item pada halaman beranda.

#### Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.
Fungsi setState(): setState() digunakan dalam Stateful Widget untuk memberi tahu Flutter bahwa status widget telah berubah, sehingga Flutter akan merender ulang widget tersebut dan memperbarui tampilan UI sesuai dengan perubahan status yang baru.
Ketika dipanggil, Flutter akan memanggil kembali metode build() pada widget tersebut, dan tampilan UI akan diperbarui berdasarkan perubahan status yang terdeteksi.

Variabel yang Terpengaruh: Semua variabel yang ada di dalam kelas State (kelas yang mengelola status pada widget stateful) dapat terpengaruh oleh pemanggilan setState(). Biasanya, variabel tersebut adalah variabel yang menggambarkan status UI, seperti status input, nilai toggle, dan lainnya. Misalnya, sebuah variabel boolean yang menentukan apakah checkbox dicentang atau tidak dapat diubah melalui setState(), yang kemudian menyebabkan UI diperbarui.

#### Jelaskan perbedaan antara const dengan final.
const dan final adalah kata kunci yang digunakan untuk mendeklarasikan variabel konstan di Dart. Perbedaan antara keduanya adalah:
- const:
Nilai yang ditetapkan dengan const adalah konstan waktu kompilasi. Ini berarti bahwa nilai tersebut sudah diketahui pada saat aplikasi dikompilasi dan tidak dapat diubah selama waktu eksekusi program.
Variabel yang dideklarasikan dengan const juga menjadi konstanta di seluruh kode dan dapat digunakan sebagai konstanta di tempat lain dalam kode, termasuk di dalam struktur data seperti List atau Map.

- final:
final memungkinkan nilai untuk ditetapkan hanya sekali, tetapi nilai tersebut dapat ditetapkan pada waktu eksekusi, tidak perlu diketahui pada saat kompilasi.
Variabel final hanya dapat diinisialisasi sekali, namun nilainya bisa ditentukan selama aplikasi berjalan, seperti pada konstruktor objek atau hasil perhitungan runtime.

#### Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.
1. Membuat repository github baru dan menginisialisasi proyek Flutter.
2. Membuat 3 tombol dengan membuat 3 widget StatelessWidget. Membuat ItemHomepage untuk menyimpan informasi item. Membuat List untuk menyimpan daftar item. Listnya berisi 3 item yang dibuat dengan ItemHomepage.

```dart
class ItemHomepage {
  final String name;
  final IconData icon;
  final Color iconColor;
  final Color backgroundColor;

  ItemHomepage(this.name, this.icon, this.backgroundColor, this.iconColor);
}
```

3. Warna latar belakang setiap item diubah dari `color:` menggunakan `item.backgroundColor`. Lalu menambah parameter backgroundColor pada ItemHomepage, dan menambahkan warna latar belakang pada setiap item.

4. Memunculkan SnackBar ketika item ditekan. Menambahkan `onPressed` pada `ElevatedButton` untuk menampilkan SnackBar ketika tombol ditekan.