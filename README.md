# Steam game Roulette v1.5.0
She will decide what you will play today.

Google's AI - https://google.com/ai - helped me create this game? tool? What is it?   
Play - https://vzvxv.github.io/Steam-Game-Roulette/

----------------------
untranslatable Russian dialect
----------------------
Для использование нужен JSON файл с играми.

Структура файла для примера: test.json
```
[
{ "id": 2990,     "color": "common",   "name": "FlatOut 2" },
{ "id": 2358720,  "color": "mythic",   "name": "Black Myth: Wukong" },
{ "id": 3473610,  "color": "godly",    "name": "Bridge Constructor Studio" }
]
```

Варианты цветов
| color | Цвет | 
| :--- | :--- | 
|trash       | Серый      
|common      | Белый      
|uncommon    | Зеленый    
|rare        | Синий    
|epic        | Фиолетовый    
|legendary   | Золотой    
|mythic      | Красный    
|godly       | Берюзовый 

Для получения "id": и "name": можно воспользоваться консолью стима  
Нажмите на клавиатуре: Win + R   
Введите steam://open/console и нажмите Enter.  
В открывшемся клиенте Steam появится новая вкладка Console.  
Введите команду: apps_installed  
Steam выдаст список всех установленных приложений с их AppID, названием и путем на диске.   
Выделяем все и нажимаем: Ctrl + C  
Делаем текстовый файл и вставляем через: Ctrl + V  

кусок для примера:
```
AppID 2279330 : "Savant - Ascent REMIX" : E:\SteamLibrary\steamapps\common\Savant - Ascent REMIX 
AppID 2296380 : "I Expect You To Die 3" : D:\SteamLibrary\steamapps\common\I Expect You To Die 3 
AppID 2307350 : "Into the Radius 2" : E:\SteamLibrary\steamapps\common\IntoTheRadius2 
```
Через условный: Notepad++  
можно довольно быстро привести это в нужный вид.  
Нажимаем: Ctrl + H   
В окно найти пишем: AppID  
В окно заменить на содержимое в скобках: ({ "id":)   
Нажимаем справа кнопку: Заменить все

В окно найти пишем содержимое в скобках: (: ")  
В окно заменить на содержимое в скобках: ("color": "mythic", "name": ")  
Нажимаем справа кнопку: Заменить все  

В окно найти пишем содержимое в скобках: (" : .*)  
В окно заменить на содержимое в скобках: (" },)   
Нажимаем справа кнопку: Заменить все  

Поздравляю у вас получилось  - к примеру:  
```
{ "id": 2609610 "color": "mythic", "name": "CONVRGENCE" },  
{ "id": 2637940 "color": "mythic", "name": "Used Cars Simulator" },  
{ "id": 2726450 "color": "mythic", "name": "Windowkill" },  
```

Вам остаётся только добавить в начале [ и в конце ]

Чтоб выглядело так:
```
[
{ "id": 2609610 "color": "mythic", "name": "CONVRGENCE" },
{ "id": 2637940 "color": "mythic", "name": "Used Cars Simulator" },
{ "id": 2726450 "color": "mythic", "name": "Windowkill" }, 
]
```
Если нужно меняйте mythic на нужный вам цвет - он тут просто для примера.


















----------------------
