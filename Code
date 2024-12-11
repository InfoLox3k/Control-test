from random import *

def deco(input_func):
    def Out_func():
        print('******************************')
        input_func()
    return Out_func()

try:
    def log(**kwargs):
        name_of_person = kwargs.get('name')
        normal_age = kwargs.get('age')

        if normal_age < 14:
            print('Not allowed')
        else:
            print('Allowed')
            if name_of_person in admins:
                @deco
                def admin():
                    print('Вы вошли в аккаунт администратора')
                    Game()
            elif name_of_person not in admins:
                Game()
except:
    print('Произошла техническая ошибка')


try:
    def Game():
        global rand_num
        win = 0
        num_hint = 0
        while True:
            rand_num = randint(0, 100)
            while win != 1:
                print(' ')



                num = int(input('Я загадал число от 0 до 100\n'
                      'Отгадай его: '))

                if num > rand_num and name in admins:
                    print('Ваше число великовато: ')
                elif num < rand_num and name in admins:
                    print('Ваше число мелковато: ')
                elif num == rand_num and name in admins:
                    @deco
                    def WIN():
                        win = 0
                        print('ВЫ ПОБЕДИЛИ!!!')
                        win += 1


                if num_hint == 0:
                    num_hint += 1
                    Hint(num_hint)

                elif num_hint != 0:
                    print('sorry')


                if (num > rand_num and name not in admins) or (num < rand_num and name not in admins):
                    print('Неверно')
                elif num == rand_num and name not in admins:
                    print('Вы победили!')
                    win += 1

            print('Ещё раз?')
            accept = input('(Да/Нет): ')
            if accept == 'Да':
                Game()
            elif accept == 'Нет':
                break
except:
    print('Произошла техническая ошибка')

def Hint(num_hint):
    if name in admins:

        print('Хотите подсказку?')
        hint = input('(Да/Нет): ')
        if hint == 'Да':
            range = rand_num // 10
            print(f'Попробуйте в {range}-м десятке или в {range + 1}-м десятке')

admins = ['Артём', 'Сан-Саныч']

name = input('Введите имя: ')
age = int(input('Введите возраст: '))

person_1 = {'name': name, 'age': age}
log(**person_1)
