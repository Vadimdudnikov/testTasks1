Авторизация происходит через модель User, данная модель обращается к другой модели LoginForm, где происходит валидация логина:
    1.Прстое правило на то, что почта нужного формата
    2.Функция ValidateEmail, проверяет был ли нацден пользователь в базе, если нет, записывает ошибку
Пользовательская часть:
    1.После авторизации пользователя функцией redirect перенаправляет на экшн form
    2.Сам экшн и контроллер были созданы с помощью Gii
    3.На странице form, при вооде данных и нажатия кнопки Сохранить, в созданную ранее модель дописывается user_id (он берётся из метода Yii::$app->user->id), затем модель записывает данные в бд функцией save()
    4.Кнопка изменить добавлена на странице index
    5.После её нажатия создаётся запрос к бд, полученная строка вставляется в поле, после нажатия кнопки сохранить данные записываются в бд тем же способом что и при создании
Гостевая часть:
    1.Был создать котроллер и экшн к нему (DefaultController, default/view), в качестве параметра экшн принимает id пользователя, берёт он его через get запрос
    2.Был создан виджет в папке component, виджет принимает данные из бд и выводит на страницу