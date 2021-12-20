   На начальном этапе разработки нейтронного генератора возникает необходимость оценки нейтронного выхода для различных ядерных реакций. 
Чтобы оценить нейтронный выход для различных реакций можно воспользоваться данными о сечении взаимодействия налетающей частицы с атомами мишени (например из JANIS) и данными о 
потерях энергии налетающей частицей в материале и глубине ее проникновения в мишень (с помощью SRIM). Для оценки зависимости нейтронного выхода от энергии налетающей частицы может быть использована приложенная программа:
[Y(E0).txt](https://github.com/APSkripnik/research-instruments.github.io/files/7694143/Y.E0.txt)

Инструкция по использованию:
1) Найти данные об интересующих взаимодействиях налетающего иона с мишенью из заданного материала: 
- Сечение взаимодействия в зависимости от энергии. Записать в файл 1.csv, где первая строка - величина энергии иона в кэВ, вторая - сечение взаимодействия в см2.
   Можно найти с помощью JANIS
- Величину потерь энергии (продольных и поперечных) и максимальную глубину проникновения в зависимости от энергии иона. 
   Записать в файл 2.csv, где первая строчка - энергия в кэВ (если МэВ - то после числа должно стоять MeV), вторая - потери энергии dE/dx продольные,
   3-я - поперечные потери энергии, 4-я - максимальная глубина проникновения (в мкм или в ангстремах, если в ангстремах - после числа поставить A). Можно получить с помощью SRIM.
2) Оба файла поместить в одну папку с запускаемым файлом программы.
3) Запустить программу. Указать концентрацию атомов вещества мишени (в м-3) и шаг расчета в мкм.
4) В результате работы программа создает в той же папке файл Y(E0).dat в котором 1-ая строчка - энергия налетающих частиц, вторая строчка - выход нейтронов в размерности "число нейтронов на каждый падающий на мишень ион" (если исходная реакция - нейтронообразующая).
Пример получаемых результатов для нескольких реакций (после обработки полученных точек):
![Y(E0)(all)](https://user-images.githubusercontent.com/95928573/145608782-fa3e7df6-c970-4853-a6ca-b8a3254e0e58.jpg)