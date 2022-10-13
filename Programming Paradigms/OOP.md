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

Упомянутый в определении термин класс, описаны тут [[11 Классы|JavaScript]] и [TypeScript]

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


## Encapsulation

Encapsulation is about hidding things from the end user. In js we can do it with hash symbol(#)