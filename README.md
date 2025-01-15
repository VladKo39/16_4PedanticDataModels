# Домашнее задание по теме "Модели данных Pydantic"
# Цель: 
>научиться описывать и использовать Pydantic модель.

# Задача "Модель пользователя":
## Подготовка:
Используйте CRUD запросы из предыдущей задачи.

Создайте пустой список **`users = []`**

Создайте класс(модель) **User**, наследованный от **BaseModel**, который будет содержать следующие поля:
>1.**id** - номер пользователя (int)
>
>2.**username** - имя пользователя (str)
>
>3.**age** - возраст пользователя (int)

**Измените и дополните ранее описанные 4 CRUD запроса:*

***get*** запрос по маршруту **`'/users'`** теперь возвращает список ***users***.
***post*** запрос по маршруту **`'/user/{username}/{age}'`**, теперь:

>1.Добавляет в список **users** объект **User.**
>
>2.***id*** этого объекта будет на 1 больше, чем у последнего в списке **users**. Если список **users** пустой, то 1.
>
>3.Все остальные параметры объекта **User** - переданные в функцию ***username*** и ***age*** соответственно.
>
>4.В конце возвращает созданного пользователя.

**put** запрос по маршруту **`'/user/{user_id}/{username}/{age}'`** теперь:
>1.Обновляет **username** и **age** пользователя, если пользователь с таким **user_id** есть в списке **users** и возвращает его.
>
>2.В случае отсутствия пользователя выбрасывается исключение HTTPException с описанием ***`"User was not found"`*** и кодом **`404`**.

**delete** запрос по маршруту **`'/user/{user_id}'`**, теперь:

>1.Удаляет пользователя, если пользователь с таким **user_id** есть в списке **users** и возвращает его.
>
>2.В случае отсутствия пользователя выбрасывается исключение HTTPException с описанием **`"User was not found"`** и кодом **`404`**.

**Выполните каждый из этих запросов по порядку. Ответы должны совпадать:**

**1. GET '/users'**

[]

**2. POST '/user/{username}/{age}' # username - UrbanUser, age - 24**

![image](https://github.com/user-attachments/assets/d4d6819e-936e-4a74-ae39-f47c1af64909)


**3. POST '/user/{username}/{age}' # username - UrbanTest, age - 36**

![image](https://github.com/user-attachments/assets/5135512a-da9a-4e08-a31b-7e3195a4c977)

**4. POST '/user/{username}/{age}' # username - Admin, age - 42**

![image](https://github.com/user-attachments/assets/f9e3bc65-17b8-4b68-91c9-0b893879580f)


**5. PUT '/user/{user_id}/{username}/{age}' # user_id - 1, username - UrbanProfi, age - 28**

![image](https://github.com/user-attachments/assets/bb62cdfd-b3b8-4045-9cef-954a3aace60f)


**6. DELETE '/user/{user_id}' # user_id - 2**


![image](https://github.com/user-attachments/assets/2a3ae87c-45c5-4e53-ae01-e933b2070951)


**7. GET '/users'**

![image](https://github.com/user-attachments/assets/53554a69-ab05-4f9a-957e-fe8e7ee439d7)


**8. DELETE '/user/{user_id}' # user_id - 2**

![image](https://github.com/user-attachments/assets/6ef86134-d279-4720-a5c3-c34b6c8d8202)


**Файл module_16_4.py загрузите на ваш GitHub репозиторий. В решении пришлите ссылку на него.**
