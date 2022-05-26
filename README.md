# **МИНИСТЕРСТВО ОБРАЗОВАНИЯ И НАУКИ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ АВТОНОМНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ОБРАЗОВАНИЯ «РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ»**
Факультет <ins>физико-математических и естественных наук.</ins>  
Кафедра <ins>информационных технологий</ins>  
## Отчет по лабораторной работе
Тема "Программирование в командном процессоре OC Unix. Ветвления и циклы"  
Выполнил:  
Студент группы <ins>НПИбд-02-21</ins>  
Студенческий билет <ins>№ 1032211222</ins>  
<ins>Снимщиков Иван Игоревич</ins>  
<ins>"26" мая 2022г.</ins>  
Москва 2022  
- **Цель работы:**
 - Изучить основы программирования в оболочке ОС UNIX/Linux. Научиться писать
более сложные командные файлы с использованием логических управляющих конструкций и циклов.  
- **Ход работы:**
 - Заходим в терминал в системе Linux.
 - Используя команды getopts grep, напишем командный файл, анализирующий командную строку с ключами.
![image](https://user-images.githubusercontent.com/104266946/170489535-c0187c8b-c228-410b-82c8-b0c1bebb9486.png)  

 - Создаем файл программы и запускаем его  
 - Наблюдаем за работой файла:  
![image](https://user-images.githubusercontent.com/104266946/170489631-86b2fb96-708d-4f93-885e-4e69ef1faf02.png)  
 - Создаем еще один файл и пишем новую программу.  
![image](https://user-images.githubusercontent.com/104266946/170489734-a7d561d2-6a88-429d-93cd-3732fc9317c5.png)  
 - Теперь напишем командный файл:  
![image](https://user-images.githubusercontent.com/104266946/170489839-1f609c20-fd68-4db3-9cd1-43721a588eba.png)  

 - Наблюдаем за работой программы:  
![image](https://user-images.githubusercontent.com/104266946/170489947-17e6d7f0-8fba-4faf-a728-119d562a75e5.png)  
 - Пишем третью программу:  
![image](https://user-images.githubusercontent.com/104266946/170490012-671a308f-f525-4365-84c4-de24423ed1b3.png)  
 - Работа программы:  
![image](https://user-images.githubusercontent.com/104266946/170490110-61081d1a-7a0f-494e-981f-51167a9b155c.png)  
 - Напишем последнюю программу:  
![image](https://user-images.githubusercontent.com/104266946/170490176-df97a03e-46ce-47ef-a735-ba7fa47990f4.png)  
 - Результат работы программы:  
![image](https://user-images.githubusercontent.com/104266946/170490278-653fd444-b657-4cca-bf68-a22a5e402cc3.png)  
 


Ответы на контрольные вопросы:  

1).Каково предназначение команды getopts?

 Команда getopts осуществляет синтаксический анализ командной строки, выделяя флаги, ииспользуется для объявления переменных. Синтаксис команды следующий: getopts option-string variable [arg...] Флаги − это опции командной строки, обычно помеченные знаком минус; Например,для команды ls флагом может являться -F. Строка опций option-string − эт осписок возможных букв и чисел соответствующего флага. Если ожидается, что некоторый флаг будет сопровождаться некоторым аргументом, то за символом, обозначающим этот флаг, должно следовать двоеточие. Соответствующей переменной присваивается буква данной опции. Еслик оманда getopts может распознать аргумент, то она возвращает истину. Принято включать getopts в цикл while и анализировать введённые данные с помощью оператора case. Функция getopts включает две специальные переменные среды −OPTARG и OPTIND. Если ожидается доплнительное значение,то OPTARG устанавливается в значение этого аргумента. Функция getopts также понимает переменные типа массив, следовательно, можно использовать её в функции не только для синтаксического анализа аргументов функций, но и для анализа введённых пользователем данных.

2).Какое отношение метасимволы имеют к генерации имён файлов?

 При перечислении имён файлов текущего каталога можно использовать следующие символы:

*−соответствует произвольной, в том числе и пустой строке;
?−соответствует любому одинарному символу;
[c1-c2] − соответствует любому символу, лексикографически находящемуся между символами с1 и с2. Например, 1.1 echo* − выведет имена всех файлов текущего каталога, что представляет собой простейший аналог команды ls; 1.2. ls*.c−выведет все файлы с последними двумя символами, совпадающими с.c. 1.3. echoprog.?−выведет все файлы, состоящие из пяти или шести символов, первыми пятью символами которых являются prog.. 1.4.[a-z]*−соответствует произвольному имени файла в текущем каталоге, начинающемуся с любой строчной буквы латинского алфавита.

3). Какие операторы управления действиями вы знаете?

Часто бывает необходимо обеспечить проведение каких-либо действий циклически и управление дальнейшими действиями в зависимости от результатов проверки некоторого условия. Для решения подобных задач язык программирования bash предоставляет возможность использовать такие управляющие конструкции, как for, case, if иwhile. С точки зрения командного процессора эти управляющие конструкции являются обычными командами и могут использоваться как при создании командных файлов, так и при работе в интерактивном режиме. Команды,реализующие подобные конструкции, по сути, являются операторами языка программирования bash. Поэтому при описании языка программирования bash термин оператор будет использоваться наравне с термином команда. Команды ОСUNIX возвращают код завершения, значение которого может быть использовано для принятия решения о дальнейших действиях. Команда test, например, создана специально для использования в командных файлах. Единственная функция этой команды заключается в выработке кода завершения.

4).Какие операторы используются для прерывания цикла

 Два несложных способа позволяют вам прерывать циклы в оболочке bash. Команда break завершает выполнение цикла, а команда continue завершает данную итерацию блока операторов. Команда break полезна для завершения цикла while в ситуациях, когда условие перестаёт быть правильным. Команда continue используется в ситуациях, когда больше нет необходимости выполнять блок операторов, но вы можете захотеть продолжить проверять данный блок на других условных выражениях.

5).Для чего нужны команды false и true?

 Следующие две команды ОС UNIX используются только совместно с управляющими конструкциями языка программирования bash: это команда true,которая всегда возвращает код завершения, равный нулю(т.е.истина),и команда false,которая всегда возвращает код завершения,неравный нулю(т.е.ложь).

6). . Что означает строка if test -f man$s/$i.$s, встреченная в командном файле?

 Строка if test-fman$s/$i.$s проверяет,существует ли файл man$s/$i.$s и является ли этот файл обычным файлом.Если данный файл является каталогом,то команда вернет нулевое значение (ложь).

7). Объясните различия между конструкциями while и until

 Выполнение оператора цикла while сводится к тому,что сначала выполняется последовательность команд(операторов),которую задаёт список-команд в строке,содержащей служебное слово while,а затем,если последняя выполненная команда из этой последовательности команд возвращает нулевой код завершения(истина),выполняется последовательность команд(операторов),которую задаёт список-команд в строке,содержащей служебное слово do,после чего осуществляется безусловный переход на начало оператора цикла while.Выход из цикла будет осуществлён тогда,когда последняя выполненная команда из последовательности команд (операторов),которую задаёт список-команд в строке,содержащей служебное слово while, возвратит ненулевой код завершения(ложь). При замене в операторе цикла while служебного слова while на until условие,при выполнении которого осуществляется выход из цикла,меняется на противоположное.В остальном оператор цикла while и оператор цикла until идентичны.  
 
### Вывод: Я изучил основы программирования в оболочке ОС UNIX/Linux, научился писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.
