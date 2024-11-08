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

## Tugas 8
#### Apa kegunaan `const` di Flutter? Jelaskan apa keuntungan ketika menggunakan `const` pada kode Flutter. Kapan sebaiknya kita menggunakan `const`, dan kapan sebaiknya tidak digunakan?
Kegunaan const di Flutter: const digunakan untuk mendeklarasikan variabel konstan di Dart. Dalam Flutter, const digunakan untuk membuat widget yang tidak berubah dan tidak memerlukan pembaruan status. Widget yang dideklarasikan dengan const akan dianggap sebagai widget yang sama jika dibangun ulang, sehingga Flutter tidak akan merender ulang widget tersebut. Ini dapat meningkatkan kinerja aplikasi dengan mengurangi waktu yang diperlukan untuk merender ulang widget yang tidak berubah. 

#### Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!
Column dan Row adalah dua widget yang digunakan untuk menyusun widget anak secara vertikal (Column) atau horizontal (Row). Perbedaan utama antara keduanya adalah arah susunan widget anaknya.

Column:
- Column digunakan untuk menyusun widget anak secara vertikal, dari atas ke bawah.
- Widget anak disusun berdasarkan urutan penambahan, sehingga widget pertama ditempatkan di bagian atas dan widget terakhir ditempatkan di bagian bawah.
- Jika widget anak melebihi ukuran layar, maka widget anak akan diatur dalam ScrollView agar dapat di-scroll.
- Contoh penggunaan Column: menyusun widget anak dalam bentuk daftar vertikal, seperti daftar item pada aplikasi berita atau daftar kontak.

```dart
Column(
  children: <Widget>[
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

Row:
- Row digunakan untuk menyusun widget anak secara horizontal, dari kiri ke kanan.
- Widget anak disusun berdasarkan urutan penambahan, sehingga widget pertama ditempatkan di sebelah kiri dan widget terakhir ditempatkan di sebelah kanan.
- Jika widget anak melebihi lebar layar, maka widget anak akan diatur dalam ScrollView agar dapat di-scroll.
- Contoh penggunaan Row: menyusun widget anak dalam bentuk baris horizontal, seperti menu navigasi atau tombol aksi.

```dart
Row(
  children: <Widget>[
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

####  Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!
Elemen input yang digunakan pada halaman form adalah:
1. TextFormField: digunakan untuk membuat input teks yang dapat menerima masukan dari pengguna.
2. ElevatedButton: digunakan untuk membuat tombol yang dapat ditekan oleh pengguna.
3. Form: digunakan untuk mengelompokkan elemen-elemen input dalam satu kesatuan form.
4. SingleChildScrollView: digunakan untuk membuat tata letak yang dapat di-scroll jika elemen-elemen input melebihi ukuran layar.
5. AlertDialog: digunakan untuk menampilkan dialog konfirmasi setelah pengguna mengirimkan form.

#### Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?
Caranya adalah dengan mengatur dan membuat aplikasi menggunakan ThemeData di MaterialApp. ThemeData berisi konfigurasi warna, tipografi, dan gaya yang digunakan dalam aplikasi. Dengan menggunakan ThemeData, kita dapat membuat aplikasi yang konsisten dengan mengatur tema secara global.

```dart
MaterialApp(
  title: 'Zero PBP Mobile',
  theme: ThemeData(
    colorScheme: ColorScheme.fromSeed(seedColor: Colors.cyan),
    useMaterial3: true,
    fontFamily: 'Roboto',
  ),
  home: MyHomePage(),
);
```

#### Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?
Navigasi dalam aplikasi dengan banyak halaman pada Flutter dapat ditangani dengan menggunakan Navigator dan Route. Navigator digunakan untuk mengelola tumpukan halaman (routes) dalam aplikasi, sedangkan Route digunakan untuk menentukan halaman yang akan ditampilkan. Contoh penggunaan Navigator untuk berpindah halaman:

```dart
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondPage()),
);
```