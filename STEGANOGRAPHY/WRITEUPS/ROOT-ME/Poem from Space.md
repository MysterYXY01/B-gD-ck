**Poem from Space**  
Ссылка: https://www.root-me.org/en/Challenges/Steganography/Poem-from-Space  
Описание: Глубоко поймите смысл этого знаменитого стихотворения, чтобы подтвердить этот вызов.  
Решение:  
Данный таск встречает нас текстовым файлом, из названия уже понятно, что задание будет связано с шифрование пробелами, давайте посмотрим на наличие пробелов и табуляций:  
![image](https://github.com/MysterYXY01/B-gD-ck/assets/60554866/e2891673-bf94-4d2b-906e-75e79098433e)  
Мы поняли, что это шифровка, но какая? В таких случаях может быть много вариантов. Например SNOW-стеганография, двоичный код, Whitespace Language и другие. Но в нашем случае - это Whitespace Language. Как до этого дойти? Если вы не знали о сущестовании такого языка раньше, то долго и усредно.  
Теперь можем перейти к технической части, нам нужно вывести все пробелы и табуляции и переносы строки, для этого мной был написан Python-скрипт:  
```
f = open("ch19.txt","r")
a = [i for i in f]
print("------------")
l = ""
for i in a:
    k = ""
    for z in range(len(i)):
        if i[-(z+1)] == " ": 
            k = " "+k
        elif i[-(z+1)] == "\t":
            k = "\t"+k
        elif i[-(z+1)] == "\n":
            k = "\n"+k
        else:
            break
    l = l + k
print("--------------")
print(l)
print("--------------")
```

Данный скрипт выдаст нам пробелы и табуляции:  
![image](https://github.com/MysterYXY01/B-gD-ck/assets/60554866/8bda9008-9a1c-4074-af49-b88ff41ae1cf)  
Теперь просто скопируйте (ПКМ->copy) и идем на первый же сайт с [Whitespace Language decode](https://www.dcode.fr/whitespace-language) и декодируем наш код:  
![image](https://github.com/MysterYXY01/B-gD-ck/assets/60554866/d85f686f-0dfb-4dc3-b61b-c6a4e5f15b54)  
**Ответ: RootMe{Wh1t3_Sp4c3}**  
