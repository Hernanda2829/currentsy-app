# Currency Apps
Aplikasi ini mencakup fungsi perhitungan nilai tukar mata uang i dollar ke rupiah.
 Satu dollar dianggap senilai Rp.15.000

## Scope & functionalities
- User dapat memasukkan angka
- User dapat menyentuh tombol hitung
- User mendapat invo "INVALID" jika yang dimasukkan berupa text

## How Does it Works?

Diawali dari method `MainWindow` pada class MainWindow.xaml.cs, untuk selengkapnya sebagai berikut:

```csharp
    public MainWindow()
        {
            InitializeComponent();
            currencyController = new CurrencyController();
        }
```

Dibawah ini adalah fungsi button hitung:

```csharp
 {
            var nominalInput = Input_TextBox.Text;
            var result = "Invalid";
            if (currencyController.isAllowed(nominalInput))
            {
                result = currencyController.usdToIdr(nominalInput);
            }
            ResultLabel.Content = result;
        }
```

Logika perhitungan terdapat pada class `CurrencyController.cs` sebagai berikut:

```csharp
 public string usdToIdr(string nominal)
        {
            var nominalDouble = Convert.ToDouble(nominal);
            var result = nominalDouble * 15000;
            return Convert.ToString(result);
        }
```

# Latihan
1. Review kembali percobaan 1 sampai dengan 3 dengan menjawab pertanyaan-pertanyaan pada latihan tersebut.
2. Mengapa perlu membuat class CurrencyController.cs pada percobaan 4 ?
3. Jelaskan kegunaan method isAllowed pada percobaan 4!
4. Jelaskan secara singkat mengenai Regex pada percobaan 4!
5. Buatlah class diagramnya pada percobaan 4! 

# Jawaban no.1
- Percobaan 1, jika kita memasukkan sembarang angka maka jika kita mengklik “HITUNG” akan keluara angka yang sama seperti yang kita inputkan.
- Percobaan ke 2, jika kita menginputkan angka maka angka tersebut akan dikali dengan 10000, dan jika kita menginputkan huruf maka akan terjadi error.
- Percobaan ke 3, jika kita menginputkan angka maka akan dikali 4, dan jika kita menginputkan huruf maka akan terdapat tulisan “INVALID”.

# Jawaban no.2
- Untuk memisahkan logika fungsi perhitungan “CurrencyController” dengan logika tampilan “MainWindow.Xaml.cs

# Jawaban no.3
- Untuk mengizinkan inputtextbox, jika kita menginputkan angka maka akan melakukan fungsi perhitungan matematika dan jika kita menginputkan huruf maka akan mengembalikan “INVALID” karena tidak diizinkan.

# Jawaban no.4
- Untuk mencari suatu pola spesifik dari fungsi “Regex(“[^0-9.-]+)”);

# Jawaban no.5

