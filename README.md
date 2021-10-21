# Инструкция

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
5. Переименовываем комп, вводим в домен
6. Заходим под пользователем домена, чтоб создалась папка профиля
7. Выходим и зайдем под другим чтоб заменить сохраненный профиль
8. Возвращаем базы и лог файлы

   >Сначало нужно остановить службу SQL Server
   
   >База данных EAS должна называться DB628400.mdf - ваш индекс. Подключается база руками во время выпонения скрипта см. ниже

   >Если База EAS лежала на SSD не забыть проверить\добавить права на папку

9. Меняем настройки в файле C:\InstallEAS\region_setup.xml

    <img src="https://github.com/anti37/Win10_EAS/blob/main/region_setup.png">
   
10. Запускаем от администратора C:\InstallEAS\!Запуск скрипта!.lnk

    >Действуем по инструкции...
    
    + Когда дошли до восстановления БД, заходим в MSSQL Server и подключаем базу DB628400 и после нажимаем Продолжить в скрипте
        
        <img src="https://github.com/anti37/Win10_EAS/blob/main/connectDB.png">
     
    + При заапросе выгрузить нулевую реплику говорим Нет
        
        <img src="https://github.com/anti37/Win10_EAS/blob/main/replica.png">

11. Заходим в SQL Server под sa и присоединяем оставшиеся базы
12. Настраиваем Справочник сертификатов

    Создаем профиль
    <img src="https://github.com/anti37/Win10_EAS/blob/main/certProfile.png">
    
    И экспортируем в системное хранилище из меню Сервис

13. Настраиваем и запускаем криптосервер

    >Запускать от администратора

    <img src="https://github.com/anti37/Win10_EAS/blob/main/crypto.png">
    
    >Не забываем поставить галочку в службе криптосервера, хотя проверено работает и без неё)

    <img src="https://github.com/anti37/Win10_EAS/blob/main/cryptoservice.png">
   
14. Проверить криптосервер можно настроив АРМ УКС

    <img src="https://github.com/anti37/Win10_EAS/blob/main/armuks.png">
   
15. Установка драйвера для принтера
16. Установка драйвера для считывателя
