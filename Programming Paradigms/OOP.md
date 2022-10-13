# OOP

**OOP** is programming paradigm based on classes and objects that used to structure code units in clasess and contain a list of properties and methods. It's easier for people to think in terms of objects they see every day. For example, a car has wheels and many other things. And OOP will allow to realize these objects in programming. Also oop providing major concepts such as abstraction, inheritance, polymorphism, and encapsulation.

---

OOP pros:
1. It allows for parallel development.
2. The modular classes are often reusable.
3. The coding is easier to maintain.


## Наследование (Inheritance)

Наследование является механизмом повторного использования кода.

Идея наследования заключается в том, что некоторый класс или функция-конструктор, может наследовать свойства и методы уже существующего класса или функции-конструктора.

---

Существует четыре модели наследованяи в ЯП:
- Классовая-динамическая
- Классовая-статическая
- Прототипная-делигирующая (Используется в языке JS и его надмножествах)
- Прототипная-конкатенирующая

Не смотря на существования абстракции в виде классов, в рельности это лишь альтернативный способ записи функций-конструкторов, работающих на прототипной модели. ( Разбор реализаци прототипной модели в языке JavaScript [[Prototype]]. )

---

Существует два вида наследования классов:
- Простое наследование - когда класс может наследоваться только от одного класса.
- Множественное наследование - когда класс может наследоваться сразу от нескольких других классов. 

**Inheritance** is the design technique in object-oriented programming to implement **is-a** relationship between objects.

If a class inherits from another class, it automatically obtains much of the same functionality and properties from that class and can be extended to contain separate code and data.

```ad-warning
**Является ли** кресло автомобилем? Нет, и наследоваться мы не можем.
Есть автомобиль и можно сделать легковой или грузовой автомобиль.
```

---

## Composition 

**Composition** is the design technique in object-oriented programming to implement **has-a** relationship between objects. It describes a class that references one or more objects of other classes in instance variables.

```ad-warning
**Есть ли** у автомобиля двигатель? Да, и это композиция.
```

---

## Composition vs Inheritance

Inheritance and composition are two programming techniques developers use to establish relationships between classes and objects. Inheritance derives **one class from another**, composition defines a class as **the sum of its parts**.

```ad-info
The main difference between inheritance and composition is in the relationship between objects. Inheritance: “is a.” E.g. The car is a vehicle (**No**). Composition: “has a.” E.g. The car has a wheel (**Yes**).
```

---

## Encapsulation

Понятие инкапсуляции относится к объединению данных вместе с методами, которые работают с этими данными, в один объект. 

```ad-attention
Часто приписываемое свойство **сокрытие** является лишь следствием инкопсуляции
```

.

Encapsulation is about hidding things from the end user. In JS we can do it with hash symbol(#)
[[JavaScript/Classes#Пример приватных полей класса|Example]]