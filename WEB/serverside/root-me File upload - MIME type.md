<--https://www.root-me.org/en/Challenges/Web-Server/File-upload-MIME-type-->

1. Первое, что я понял, это то, что бекенд пускает картинку, с соотвествующим MIME-type. Для этого я скачал рандомную 
   картинку из интернета и с помощью exiftool проверил её метаданные:
![изображение](https://github.com/MysterYXY01/B-gD-ck/assets/132662542/cf3674bf-1833-4d7d-8d99-e714a3c6bbe8)  

2. Далее я добавил в комментарий исполняемый php код с помощью: ```exiftool -comment="<?php phpinfo(); ?>"``` answer.php.png
3. Далее я попытался отправить изображение, однако php код не выполнялся.
4. В burp'e я поменял имя файла на answer.php.png.php (добавил еще php), написал в конец еще один исполняемый код:
    ```<?php $section=file_get_contents('../../../.passwd'); var_dump($section); ?>```
5. Отправил запрос и получил нужные ответ

