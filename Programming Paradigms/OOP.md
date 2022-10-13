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
Часто приписываемое свойство **сокрытие** является лишь следствием инкапсуляции
```

Сокрытие позволяет скрывать детали имплеменации от конечного пользователя.

**Encapsulation in programming has a few key benefits. These include:**

-   **Hiding Data**: Users will have no idea how classes are being implemented or stored. All that users will know is that values are being passed and initialized.
-   **More Flexibility:** Enables you to set variables as red or write-only. Examples include: setName(), setAge() or to set variables as write-only then you only need to omit the get methods like getName(), getAge() etc.  
-   **Easy to Reuse:** With encapsulation it's easy to change and adapt to new requirements.

[[JavaScript/Classes#Пример приватных полей класса|Code Examples]]

```ad-example
When we implementing the perso, we might have private data in the class, such as "secretNumber," that should not be exposed to other objects in the program. By encapsulating this data member as a private variable in the class, outside code would not have direct access and it would remain safe within that person’s object.
```

---
## Abstraction
it's when you can separate the interface of a class from its implementation, and focus on the interface. This is allows to create a system as a **“black box”** where it’s not important to understand the gory inner workings in order to reap the benefits of using it.

### Abstraction vs Inheritance

**Abstraction** allows hiding the internal details and displaying only the functionality to the users, while **Inheritance** allows using properties and methods of an already existing class

```ad-example
Think of a stereo system as an object with a complex logic board on the inside. It has buttons on the outside to allow for interaction with the object. When you press a button, you're not thinking about what happens on the inside because you can't see it. Even though you can't see the logic board completing these functions as a result of pressing a button, it's still performing them
```

## Polymorphism

**Polymorphism** is the provision of a single interface to entities of different types or the use of a single symbol to represent multiple different types. The concept is borrowed from a principle in biology where an organism or species can have many different forms or stages.


The most commonly recognized major classes of polymorphism are:
1. **Ad hoc polymorphism**: defines a common interface for an arbitrary set of individually specified types.
2. **Parametric polymorphism**: not specifying concrete types and instead use abstract symbols that can substitute for any type.
3. **Subtyping** (also called subtype polymorphism or inclusion polymorphism): when a name denotes instances of many different classes related by some common superclass.