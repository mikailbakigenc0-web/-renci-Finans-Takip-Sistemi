import json
import os
from datetime import datetime

FILENAME = "harcamalar.json"

def verileri_yukle():
    if not os.path.exists(FILENAME):
        return []
    with open(FILENAME, "r", encoding="utf-8") as f:
        try:
            return json.load(f)
        except:
            return []

def harcama_ekle(harcamalar):
    print("\n--- Yeni Harcama Ekle ---")
    islem = input("İşlem adı (Örn: Kitap, Yemek): ")
    miktar = float(input("Miktar (TL): "))
    kategori = input("Kategori (Eğitim/Ulaşım/Gıda): ")
    
    yeni_kayit = {
        "tarih": datetime.now().strftime("%Y-%m-%d %H:%M"),
        "islem": islem,
        "miktar": miktar,
        "kategori": kategori
    }
    
    harcamalar.append(yeni_kayit)
    with open(FILENAME, "w", encoding="utf-8") as f:
        json.dump(harcamalar, f, indent=4, ensure_ascii=False)
    print(">> Kayıt başarıyla eklendi!")

def listele(harcamalar):
    print("\n--- Tüm Harcamalar ---")
    toplam = 0
    for h in harcamalar:
        print(f"[{h['tarih']}] {h['islem']} ({h['kategori']}): {h['miktar']} TL")
        toplam += h['miktar']
    print(f"\nTOPLAM HARCAMA: {toplam} TL")

def ana_menu():
    harcamalar = verileri_yukle()
    while True:
        print("\n1. Harcama Ekle")
        print("2. Harcamaları Listele")
        print("3. Çıkış")
        secim = input("Seçiminiz: ")
        
        if secim == "1":
            harcama_ekle(harcamalar)
        elif secim == "2":
            listele(harcamalar)
        elif secim == "3":
            print("Görüşmek üzere!")
            break
        else:
            print("Geçersiz seçim!")

if __name__ == "__main__":
    ana_menu()
