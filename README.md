# digital_peter_aij2020

baseline.ipynb - Ноутбук с бейзлайном задачи.

Данные лежат вот [тут](https://drive.google.com/file/d/1kDmRCl692k6s9kQnNryq5ByAaHZX2uEw/view?usp=sharing).

### Краткое описание задачи и метрики

Участникам предлагается построчно распознавать рукописный текст Петра 1.

В качестве метрик качества мы используем следующие:
* CER - mean character error rate 

![CER](cer.png)

* WER - mean word error rate

![WER](wer.png)

* Sentence Accuracy - число полностью совпавших строк в test разделить на общее число строк в test.

![ACC](sentence.png)

В формулах для CER и WER dist - это расстояние Левенштейна. Только для CER токеном является символ (dist_c), а для WER токеном является слово (dist_w). Методику подсчета метрик можно изучить подробнее в скрипте evaluate.py. Он принимает на вход два параметра - pred.txt и true.txt. Это файлы со строками предсказаний и со строками реальных ответов соответственно.


Главная метрика, по которой сортируется лидерборд, - CER (меньше - лучше). В случае совпадения CER у двух или более участников, сортировка для них будет вестись по WER (меньше - лучше). Если и CER, и WER совпадают, - смотрим на Sentence Accuracy (больше - лучше).

Про метрики дополнительно можно прочитать вот здесь https://sites.google.com/site/textdigitisation/qualitymeasures/computingerrorrates.
