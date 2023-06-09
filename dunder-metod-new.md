# 7⃣ Dunder метод (New)

Dunder-метод `__new__` является одним из базовых методов Python, который вызывается при создании нового объекта. Он отвечает за выделение памяти для объекта и возвращает этот объект. Этот метод вызывается до метода `__init__`, который инициализирует объект.

Метод **new** принимает класс в качестве первого аргумента, а затем любое количество аргументов, которые были переданы при создании объекта. Он должен вернуть новый экземпляр класса.

```python
class MyClass: 
    def new(cls, *args, **kwargs): 
        print("Creating new instance") 
        instance = super().new(cls) 
        return instance

    def __init__(self, arg1, arg2):
        print("Initializing instance")
        self.arg1 = arg1
        self.arg2 = arg2 
        
my_obj = MyClass("hello", 123)
```

В этом примере мы создаем класс `MyClass` с методом **new** и методом `__init__`. При создании объекта `my_obj` с помощью `MyClass("hello", 123)` сначала вызывается метод **new**, который выводит сообщение "Creating new instance" и возвращает новый экземпляр класса. Затем вызывается метод `__init__`, который выводит сообщение "Initializing instance" и инициализирует атрибуты объекта.

Метод `__new__` может быть полезен, например, для создания объектов нескольких разных классов на основе переданных аргументов или для изменения способа создания объектов. Он также может использоваться вместе с метаклассами для изменения поведения создания объектов класса.
