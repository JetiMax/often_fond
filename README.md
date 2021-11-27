# often_fond
Напишите программу, которая получает от пользователя имя файла, открывает этот файл в текущем каталоге, читает его и выводит два слова: наиболее часто встречающееся из тех, что имеют размер более трех символов, и наиболее длинное слово на английском языке.
often_fond = []
qty_often_found = 0


def exclude(text):
    for i in '!"\'#$%&()*+-,/:;<=>?@[\\]^_{|}~':
        text = text.replace(i, '')
    return text.split()


def frequentlyooccurring(text, lenght=0):

 for i in text:
    if len(i) > lenght:
        qty = text.count(i)
        if qty > qty_often_found and qty > 2:
         qty_often_found = qty
         frequentlyOccurring = [i]
        elif qty == qty_often_found:
            often_fond.append(i)
 return list(set(often_fond))

def mostLenght(text):

 most_lenght = []
 qty_most_lenght = 0
 most_lenght = []
 qty_most_lenght = 0
 alphabet = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
 for item in text:
     for char in item:
         if char not in alphabet:
             charEn = False
         else:
             charEn = True

     if charEn:
         qty = len(item)
         if qty > qty_most_lenght:
             qty_most_lenght = qty
             most_lenght = [item]
         elif qty == qty_most_lenght:
             most_lenght.append(item)

 return list(set(most_lenght))


nameFile = input('Название файла: ')

with open(nameFile, encoding='utf8') as f:
    fileText = f.read()
fileText = changeText(fileText)
print(f'Список самых частых слов длинной более трёх символов: {often_fond(fileText, 3)}')
print(f'Список самых длинных английских слов: {often_fond(fileText)}')
