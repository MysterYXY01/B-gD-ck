**Mimic - Dummy sight**  
Ссылка: [https://www.root-me.org/en/Challenges/Steganography/TXT-George-and-Alfred](https://www.root-me.org/en/Challenges/Steganography/Mimic-Dummy-sight)  
Описание: Друг детства знает, что вы работаете в сфере кибербезопасности, и думает, что получил мошенническое электронное письмо, содержащее два вложения. Он просит вас проверить, не является ли он вредоносным.  
Решение:  
Данный таск встречает нас двумя файлами, ciphertext и plaintext. Так же к данному таску прикреплена ссылка на форум, где обсуждают стеганографию в текстах. Мы не будем вдоваться в подробности, просто прикреплю ссылку: https://news.ycombinator.com/item?id=8721475, на этом сайте можно найти ссылку на github репозиторий с утилитой, которая поможет нам: https://github.com/rw/plainsight.  
Далее читаем, что утилита умеет шифровать и дешифровать. Для расшифровки воспользуемся такой командой:  
```cat ciphertext | plainsight -m decipher -f plaintext > deciphered``` - в итоге мы получим файл с расшифрованной фразой:  
```
$ROO =  "MV93!fbjB0X200bDFjMTB1NV#F80b^h".Replace("!","NHN").Replace("@","q").Replace("#","80d").Replace("<","ZXI=").Replace("%","GVF").Replace("^","Gw").Replace("&","cTW").Replace("*","zb2Z").Replace("[","T").Replace("]","iZW1").Replace("{","Fdi");
$TME = [Text.Encoding]::UTF8.GetString([Convert]::FromBase64String($ROO));
```
Как видно по синтаксису это PowerShell код, исполним:  
![image](https://github.com/MysterYXY01/B-gD-ck/assets/60554866/b0d3932a-7a3a-4760-a833-120a0b6c3e57)  
И выведем результат переменной $TME:  
![image](https://github.com/MysterYXY01/B-gD-ck/assets/60554866/01c79fc3-7858-481e-a150-c81b7b9b3894)  
Получаеш нам долгожданный ответ.  
**Ответ:1_w4s_n0t_m4l1c10u5_4t_4ll!**  
