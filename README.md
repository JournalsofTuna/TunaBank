# TunaBank
atm = {
    100: {
        "Name": "Account 1",
        "Surname": "",
        "Bakiye": 250,
    },
    101: {
        "Name": "Account 2",
        "Surname": "",
        "Bakiye": 500,
    },
    102: {
        "Name": "Account 3",
        "Surname": "",
        "Bakiye": 400,
    }
}

while True:
    user = int(input("KARTINIZI GİRİNİZ: "))
    if user not in atm:
        print("Geçersiz Kart Numarası!")
        continue

    secim = int(input(f"\nTunaBank'a hoş geldiniz {atm[user]['Name']} Ne yapmak istersiniz?\n1-Bakiye Sorgulama\n2-Para Çekme\n3-Para Yatırma\n4-Kart İadesi\n"))

    if secim == 4:
        print("Çıkış yapılıyor...")
        break
    elif secim == 1:
        print(f"Bakiyeniz: {atm[user]['Bakiye']} TL")
        break
    elif secim == 2:
        money_out = int(input("Ne Kadar Para Çekmek İstiyorsunuz:  "))
        if money_out <= atm[user]['Bakiye']:
            atm[user]['Bakiye'] -= money_out
            print("Paranızı Çekebilirsiniz.")
            print(f"Bakiyeniz: {atm[user]['Bakiye']} TL")
            break
        else:
            print("Yeterli Paranız Bulunmamaktadır.")
            break
    elif secim == 3:
        money_in = int(input("Ne Kadar Para Yatırmak İstersiniz: "))
        atm[user]['Bakiye'] += money_in
        print(f"Bakiyeniz: {atm[user]['Bakiye']} TL")
        break
    else:
        print("Yanlış seçim yaptınız!")
        exit()
