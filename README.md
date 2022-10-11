# Собеседование Junior+
### ?. ODM
?

### ?. ООП
**Объектно-ориентированное программирование (ООП)** - это методология программирования с использованием объектов и классов. 

**Класс в Java** - это шаблон для создания объекта, а **объект** - это экземпляр класса. 
Класс определяет структуру и поведение, которые будут совместно использоваться набором объектов. Класс содержит переменные и методы, которые называются элементами класса, членами класса.

Выделяют следующие основные принципы ООП:  

**1. Абстракция** - означает выделение наиболее значимой информации и исключение из рассмотрения незначимой. С точки зрения программирования это правильное разделение программы на объекты. Абстракция позволяет отобрать главные характеристики и опустить второстепенные.  

**2. Инкапсуляция** - ограничение доступа к данным и возможностям их изменения. Инкапсуляция достигается с помощью **модификаторов доступа**:
- public - доступ из любого места программы;
- protected - доступ на уровне пакета и классов-наследников;
- default - доступ на уровне пакета;
- private - доступ только на уровне класса.

**3. Наследование** - механизм, который позволяет описать новый класс на основе уже существующего. При этом свойства и функциональность родительского класса заимствуются новым классом.  

Класс, от которого наследуются свойства и методы, называется **суперклассом (родительским классом)**. Классы, которые наследуют их, называются **подклассами (дочерними классами)**. 

Для создания дочернего класса используется ключевое слово `extends`. Для обращения к суперклассу из подкласса используется ключевое слово `super`.

_Прим:_
Множественное наследование классов в Java не допускается.

**4. Полиморфизм** - разная реализация одного и того же интерфейса.  
Полиморфизм в Java бывает статическим (полиморфизм времени компиляции) и динамическим (полиморфизм времени выполнения).  

**Перегрузка метода** является примером статического полиморфизма, а **переопределение метода** – примером динамического полиморфизма.

**Перегрузка метода** - механизм, при котором несколько методов имеют одинаковое название, но разные типы, порядок и количество параметров.
```
public int method(int a) { ... }
public int method(double a) { ... }
public int method(int a, String b) { ... }
public int method(String a, int b) { ... }
```
**Переопределение метода** - это изменение поведения в дочернем классе  уже существующего  в суперклассе метода (override).  В новом методе должны быть те же сигнатура и тип возвращаемого результата, что и у метода родительского класса.

_Прим:_
Методы с модификатором private нельзя переопределить.

### ?. Принципы SOLID
**1. Single Responsibility Principle - принцип единственной ответственности**.  
Каждый класс должен отвечать только за одну задачу. Если же существуют методы, которые не соответствуют цели сущестствования класса, их необходимо вынести за рамки этого класса.

**2. Open Closed Principle (Принцип открытости/закрытости)**.  
Классы должны быть открыты для расширений, но закрыты для модификаций. Если есть класс, функционал которого предусматривает множество ответвлений либо ряд последовательных шагов, и есть высокая вероятность, что их количество будет возрастать, тогда необходимо спроектировать класс таким образом, чтобы новые ответвления или шаги не приводили к его модификации.

**3. Liskov’s Substitution Principle (Принцип подстановки Барбары Лисков)**.  
Подклассы должны дополнять, а не замещать поведение базового класса. Если объект базового класса заменить объектом его производного класса, то программа должна продолжить работать корректно.
Если мы переопределяем производные методы от родительского класса, то новое поведение не должно противоречить поведению базового класса.

**4. Interface Segregation Principle (Принцип разделения интерфейса)**.  
Лучше, когда есть множество специализированных интерфейсов, чем один общий. Не следует ставить клиент в зависимость от методов, которые он не использует. Когда классу приходится производить действия, не несущие никакой реальной пользы, это выливается в пустую трату ресурса, а в случае, если класс выполнять эти действия не способен, ведёт к возникновению багов.

![image](https://user-images.githubusercontent.com/73114969/195052244-5a7437ac-6e90-4165-a8a9-85a0f718a34e.png)


**5. Dependency Inversion Principle (Принцип инверсии зависимостей)**.  
Модули верхнего уровня не должны зависеть от модулей нижнего уровня. И те, и другие должны зависеть от абстракций. Абстракции не должны зависеть от деталей. Детали должны зависеть от абстракций. Этот принцип служит для того, чтобы устранить зависимость классов верхнего уровня от классов нижнего уровня за счёт введения интерфейсов.
