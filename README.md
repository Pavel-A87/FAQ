# FAQ для PATH for MacOS

1. Ставим Java Dev Kit  с сайта Oracle. 
Перед этим регаемся, иначе не даст скачать.

2. Поставили. Теперь проверяем что поставили. 
Идем в терминал и пишем:
java -version

Видим что-то типа :
openjdk version "15.0.1" 2020-10-20
OpenJDK Runtime Environment (build 15.0.1+9-18)
OpenJDK 64-Bit Server VM (build 15.0.1+9-18, mixed mode, sharing)
admins-MacBook-Pro:~ admin$ 

Пишем опять но для проверки версии компилятора:
javac -version
ЗЫ: буквочка “с” в конце слова javac говорит что это компилятор джава)))

Видим что-то типа :
javac 15.0.1
admins-MacBook-Pro:~ admin$ 

3. Ищем путь куда это добро все проинсталилось. 
Для этого вводим:
/usr/libexec/java_home -v 15.0.1

Видим что-то типа :
/Users/admin/Library/Java/JavaVirtualMachines/openjdk-15.0.1/Contents/Home
admins-MacBook-Pro:~ admin$ 

4. Теперь нужно проверить есть ли у нас файл .bash_profile
Вводим cd
Вводим cat .bash_profile

Если строка ругнулась на отсутсвие оного тогда переходим к п.5

5. Создаем файл .bash_profile
Для этого вводим nano .bash_profile и жмем ввод

Откроется окно редактора

6. В окне редактора вводим:
export JAVA_HOME=/Users/admin/Library/Java/JavaVirtualMachines/openjdk-15.0.1/Contents/Home
export PATH=$PATH:$JAVA_HOME/bin/java
export JAVA_HOME;

Жмем клавиши  control+o
Внизу проверяем имя файла .bash_profile
Жмем enter
Жмем control+x
И ВЫХОДИМ ИЗ ТЕРМИНАЛА, те полностью закрываем приложение а не просто сворачиваем его

7. Опять заходим в терминал и вводим
$JAVA_HOME/bin/java -version

Видим что-то типа :
openjdk version "15.0.1" 2020-10-20
OpenJDK Runtime Environment (build 15.0.1+9-18)
OpenJDK 64-Bit Server VM (build 15.0.1+9-18, mixed mode, sharing)
admins-MacBook-Pro:~ admin$ 


Поздравляю! Все супер!

ЗЫ: не забываем что пути в директориях у вас будут отличаться от моих



