Birthday Tracker
=
Напоминание о днях рождения.

### Выполнено по книге
Coding iPhone Apps for Kids: A Playful Introduction to Swift<br>
by Gloria Winquist and Matt McCarthy

### Описание
В приложении используется два контроллера навигации:
- первый управляет переходом из таблицы к модальному окну создания новой записи;
- второй позволяет сохранить новую запись или отменить изменения.

Дни рождения загружаются в таблицу из БД, управляемой средствами фреймворка CoreData.

Описание структуры БД находится в файле BirthdayTracker.xcdatamodeld

Обновление контента БД выполняется:
- из модального окна создания новой записи, по кнопке Save;
- при удалении записи из таблицы.

Ленивое вычисляемое свойство persistentContainer (класс AppDelegate) предоставляет актуальное значение контекста БД.

Добавление или удаление записи БД выполняется командой:  
```swift
persistentContainer.viewContext.save()
```

При старте приложения выполняется запрос на разрешение отправлять уведомления.  
Запрос реализован в функции application(_:didFinishLaunchingWithOptions:) класса AppDelegate.

Для управления уведомлениями использован фреймворк UserNotifications.

### Компоненты
UIApplication, UITableViewController, UITableView

UIDatePicker, UITextField, UILabel

UINavigationController, UINavigationBar, UINavigationItem, UIBarButtonItem

NSPersistentContainer, NSFetchRequest, NSSortDescriptor, NSError, UUID

UNUserNotificationCenter, UNNotificationRequest, UNMutableNotificationContent, UNNotificationSound, UNCalendarNotificationTrigger, Calendar
