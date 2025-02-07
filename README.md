# Led Parlakligi

Bu proje, bir potansiyometre kullanarak bir LED'in parlaklığını kontrol etmeyi amaçlar. Potansiyometrenin konumu, LED'in parlaklığını doğrudan etkiler.

## Gerekli Malzemeler

*   Arduino Uno
*   1 adet LED
*   1 adet 220-330 ohm direnç (LED için)
*   1 adet 10k ohm potansiyometre
*   Jumper kabloları
*   Breadboard (isteğe bağlı)

## Bağlantı Şeması

1.  LED'in uzun bacağını (anot) bir 220-330 ohm direnç ile Arduino'nun 4 numaralı dijital pinine bağlayın.
2.  LED'in kısa bacağını (katot) Arduino'nun GND pinine bağlayın.
3.  Potansiyometrenin bir ucunu Arduino'nun 5V pinine bağlayın.
4.  Potansiyometrenin diğer ucunu Arduino'nun GND pinine bağlayın.
5.  Potansiyometrenin orta ucunu Arduino'nun A0 analog pinine bağlayın.  
  ![Image](https://github.com/user-attachments/assets/5648a5f7-7cc6-40a9-8039-a17ba5438c16)

## Kod

```c++
int led = 4;     // LED'in bağlı olduğu pin
int parlaklik;   // Parlaklık değerini saklamak için değişken

void setup() {
  pinMode(led, OUTPUT);   // LED pinini çıkış olarak ayarla
  pinMode(A0, INPUT);    // Potansiyometre pinini giriş olarak ayarla
}

void loop() {
  parlaklik = analogRead(A0);   // Potansiyometreden değeri oku (0-1023)
  analogWrite(led, parlaklik);  // LED'in parlaklığını ayarla (0-255)
}
```

## Kullanım
*  Devreyi şemaya göre kurun.
*  Kodu Arduino'ya yükleyin.
*  Potansiyometreyi çevirerek LED'in parlaklığını ayarlayabilirsiniz.