# Инструкция, картинки будут позже

1. Копируем профиль.
    
    Пример C:\Users\ops628410
    
2. Копируем Stunnel.conf

   C:\Program Files\Validata\zpki\stunnel.conf
   
3. Копируем базы и лог файлы

   >Сначало нужно остановить службу SQL Server

   + DB628000 - ваш индекс   
   + AddrExt1.mdf   
   + AddrExt1Aux.mdf   
   + AddrExt2.mdf   
   + AddrExt2Aux.mdf   
   + ESPP

4. Восстановливаемся из образа
5. Вводим в домен
6. Заходим под пользователем домена, чтоб создалась папка профиля
7. Выходим и зайдем под другим чтоб заменить сохраненный профиль
8. Копируем базы и лог файлы

   >Сначало нужно остановить службу SQL Server
   
   >База данных EAS должна называться DB628400.mdf - ваш индекс иначе скрипт её не найдёт.

9. Меняем настройки в файле C:\InstallEAS\region_setup.xml

   <img src="https://github.com/anti37/Win10_EAS/blob/main/region_setup.png">
   
10. Запускаем от администратора C:\InstallEAS\!Запуск скрипта!.lnk

   >Действуем по инструкции... здесь надо уточнить что базу может не найти

11. Заходим в SQL Server под sa и присоединяем оставшиеся базы
12. Настраиваем Справочник сертификатов

    Создаем профиль
    <img src="https://github.com/anti37/Win10_EAS/blob/main/certProfile.png">
    
    И экспортируем в системное хранилище из меню Сервис

13. Настраиваем и запускаем криптосервер

   >Запускать от администратора

   <img src="https://github.com/anti37/Win10_EAS/blob/main/crypto.png">
   
14. Проверить криптосервер можно настроив АРМ УКС

   <img src="https://github.com/anti37/Win10_EAS/blob/main/armuks.png">
   
15. Установка драйвера для принтера    - опционально, можно делать в последнюю очередь
16. Установка драйвера для считывателя - опционально, можно делать в последнюю очередь
