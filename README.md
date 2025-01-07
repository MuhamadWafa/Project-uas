# NAMA        : MUHAMAD WAFA MUFIDA ZULFI
# KELAS       : TI.24.A4
# NIM         : 312410334
# MATA KULIAH : BAHASA PEMOGRAMAN

![WhatsApp Image 2025-01-06 at 21 24 08_915c3b88](https://github.com/user-attachments/assets/fec81526-e7cc-4773-b109-c13715a2195d)

Program ini adalah aplikasi sederhana untuk berjualan bebek rica rica di terminal. Program ini dibuat dengan pendekatan modular dan menggunakan prinsip OOP (Object-Oriented Programming). 

## BERIKUT PROGRAM INPUT TERSEBUT

```PYTHON

class Mattress:
    def __init__(self, quantity):
        self.quantity = quantity
        self.price_per_unit = 20000

    def total_price(self):
        return self.quantity * self.price_per_unit


class View:
    @staticmethod
    def display_table(customer_name, date, quantity, total_price):
        print("\n+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
        print("|                     Hasil                       |")
        print("+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
        print(f"| Nama Pelanggan: {customer_name}                  |")
        print(f"| Tanggal: {date}                                 |")
        print(f"| Jumlah bebek rica rica : {quantity}                        |")
        print(f"| Total Harga: Rp{total_price}                    |")
        print("+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")


class Process:
    @staticmethod
    def validate_input(input_value):
        try:
            quantity = int(input_value)
            if quantity < 1:
                raise ValueError("Jumlah bebek rica rica tidak boleh kurang dari 1.")
            return quantity
        except ValueError as e:
            print(e)
            return None

    @staticmethod
    def validate_date(input_date):
        from datetime import datetime
        try:
            date_obj = datetime.strptime(input_date, "%m/%Y")
            return date_obj.strftime("%B %Y")  # Mengembalikan dalam format Bulan Tahun
        except ValueError:
            print("Format tanggal tidak valid. Gunakan MM/YYYY.")
            return None


def main():
    # Input dari pengguna
    customer_name = input("Masukkan nama pelanggan: ")
    user_input = input("Masukkan jumlah bebek rica rica: ")
    date_input = input("Masukkan tanggal (bulan/tahun - MM/YYYY): ")
    
    # Validasi input
    quantity = Process.validate_input(user_input)
    if quantity is None:
        return  # Menghentikan program jika input tidak valid

    date = Process.validate_date(date_input)
    if date is None:
        return  # Menghentikan program jika input tanggal tidak valid

    # Proses data
    mattress = Mattress(quantity)
    total_price = mattress.total_price()

    # Tampilkan hasil
    View.display_table(customer_name, date, quantity, total_price)


if __name__ == "__main__":
    main()

    ```


di atas merupakan program yang mensimulasikan pemesanan bebek rica rica, di mana pengguna dapat memasukkan nama pelanggan, jumlah bebek rica rica yang dipesan, dan tanggal pemesanan. Program ini menghitung total harga dan menampilkan hasilnya dalam format yang terstruktur.
