---
title: Klassen – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Klassentypen und wie diese erstellt werden
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 8fa8d33ce9ece20a18c5c1542bc44cf569e9fa2e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440405"
---
# <a name="classes-c-programming-guide"></a>Klassen (C#-Programmierhandbuch)

## <a name="reference-types"></a>Verweistypen  

Ein Typ, der als [Klasse](../../language-reference/keywords/class.md) definiert ist, ist ein *Referenztyp*. Wenn Sie zur Laufzeit eine Variable eines Referenztyps deklarieren, enthält die Variable zunächst den Wert [NULL](../../language-reference/keywords/null.md), bis Sie explizit eine Instanz der Klasse mithilfe des Operators [new](../../language-reference/operators/new-operator.md) erstellen oder ihr ein Objekt eines kompatiblen Typs zuweisen, das wie im folgenden Beispiel möglicherweise an anderer Stelle erstellt wurde:

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

Beim Erstellen des Objekts wird im verwalteten Heap für dieses bestimmte Objekt ausreichend Speicherplatz zugewiesen. Die Variable enthält lediglich einen Verweis auf den Speicherort dieses Objekts. Für Typen im verwalteten Heap ist Mehraufwand erforderlich, wenn sie zugewiesen werden und wenn sie von der automatischen Speicherverwaltungsfunktion der CLR freigegeben werden, was als *Garbage Collection* bezeichnet wird. Die Garbage Collection ist jedoch auch stark optimiert. In den meisten Szenarios führt sie nicht zu einem Leistungsproblem. Weitere Informationen zur Garbage Collection finden Sie unter [Automatische Speicherverwaltung und Garbage Collection](../../../standard/garbage-collection/fundamentals.md).  
  
## <a name="declaring-classes"></a>Deklarieren von Klassen

 Klassen werden mithilfe des Schlüsselworts [class](../../language-reference/keywords/class.md) gefolgt von einem eindeutigen Bezeichner deklariert, wie im folgenden Beispiel dargestellt:

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 Das `class`-Schlüsselwort wird der Zugriffsebene vorangestellt. Jeder kann Instanzen dieser Klasse erstellen, da in diesem Fall [public](../../language-reference/keywords/public.md) verwendet wird. Der Name der Klasse folgt dem `class`-Schlüsselwort. Der Name der Klasse muss ein gültiger C#-[Bezeichnername](../inside-a-program/identifier-names.md) sein. Der Rest der Definition ist der Text einer Klasse, in dem das Verhalten und die Daten definiert sind. Felder, Eigenschaften, Methoden und Ereignisse für eine Klasse werden zusammen als *Klassenmember* bezeichnet.  
  
## <a name="creating-objects"></a>Erstellen von Objekten

Obwohl sie manchmal synonym werden, sind eine Klasse und ein Objekt unterschiedliche Dinge. Eine Klasse definiert einen Typ eines Objekts, aber es ist kein Objekt selbst. Ein Objekt ist eine konkrete Entität, basierend auf einer Klasse, und wird manchmal als Instanz einer Klasse bezeichnet.  
  
 Objekte können mithilfe des Schlüsselworts [new](../../language-reference/operators/new-operator.md) erstellt werden, gefolgt vom Namen der Klasse, auf die das Objekt basiert, z.B.:  

 ```csharp
 Customer object1 = new Customer();
 ```

 Wenn eine Instanz einer Klasse erstellt wird, wird ein Verweis auf das Objekt an den Programmierer übergeben. Im vorherigen Beispiel ist `object1` ein Verweis auf ein Objekt, das auf `Customer` basiert. Dieser Verweis bezieht sich auf das neue Objekt, enthält jedoch nicht die Objektdaten selbst. In der Tat können Sie einen Objektverweis erstellen, ohne ein Objekt zu erstellen:  

```csharp
 Customer object2;
```

 Es wird nicht empfohlen, einen Objektverweis wie diesen zu erstellen, der auf kein Objekt verweist. Der Versuch, auf ein Objekt über solch einen Verweis zuzugreifen, schlägt während der Laufzeit fehl. Allerdings kann ein solcher Verweis dazu veranlasst werden, auf ein Objekt zu verweisen, indem entweder ein neues Objekt erstellt wird oder indem es einem vorhandenen Objekt zugewiesen wird, z. B.:  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 Dieser Code erstellt zwei Objektverweise, die beide auf dasselbe Objekt verweisen. Aus diesem Grund werden alle Änderungen am Objekt, die über `object3` getätigt worden sind, bei nachfolgenden Verwendungen von `object4` berücksichtigt. Da auf Objekte, die auf Klassen basieren, durch Verweise zurückgegriffen werden, sind Klassen als Verweistypen bekannt.  
  
## <a name="class-inheritance"></a>Klassenvererbung  

Klassen unterstützen die *Vererbung* vollständig. Dies ist ein wesentliches Merkmal der objektorientierten Programmierung. Wenn Sie eine Klasse erstellen, können Sie von einer anderen Klasse erben, die nicht als [versiegelt](../../language-reference/keywords/sealed.md) definiert ist. Andere Klassen können von Ihrer Klasse erben und die virtuellen Methoden überschreiben. Außerdem kann eine Struktur eine oder mehrere Schnittstellen implementieren.

Die Vererbung erfolgt durch Verwendung einer *Ableitung*, d.h., dass eine Klasse mithilfe einer *Basisklasse* deklariert wird, aus der Sie Daten und das Verhalten erbt. Eine Basisklasse wird durch Anhängen eines Doppelpunkts sowie den Namen der Basisklasse angegeben, die dem abgeleiteten Klassennamen folgt, z.B.:  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

Wenn eine Klasse eine Basisklasse deklariert, erbt sie alle Member der Basisklasse mit Ausnahme der Konstruktoren. Weitere Informationen finden Sie unter [Vererbung](inheritance.md).
  
Anders als in C++ kann eine Klasse in C# nur direkt von einer Basisklasse erben. Da jedoch eine Basisklasse von einer anderen Klasse erben kann, kann eine Klasse indirekt von mehreren Basisklassen erben. Darüber hinaus kann eine Klasse mehr als eine Schnittstelle direkt implementieren. Weitere Informationen finden Sie unter [Schnittstellen](../interfaces/index.md).  
  
Eine Klasse kann als [abstrakt](../../language-reference/keywords/abstract.md) deklariert werden. Eine abstrakte Klasse enthält abstrakte Methoden, die über eine Signaturdefinition, aber keine Implementierung verfügen. Abstrakte Klassen dürfen nicht instanziiert werden. Sie können nur mithilfe von abgeleiteten Klassen verwendet werden, die die abstrakten Methoden implementieren. Im Gegensatz dazu lässt eine [versiegelte](../../language-reference/keywords/sealed.md) Klasse nicht zu, dass andere Klassen von ihr ableiten. Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](abstract-and-sealed-classes-and-class-members.md).  
  
Klassendefinitionen können zwischen verschiedenen Quelldateien aufgeteilt werden. Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](partial-classes-and-methods.md).  
  
## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine öffentliche Klasse definiert, die [eine automatisch implementierte Eigenschaft](auto-implemented-properties.md), eine Methode und eine spezielle Methode, einen sogenannten Konstruktor, enthält. Weitere Informationen finden Sie in den Artikeln zu [Eigenschaften](properties.md), [Methoden](methods.md) und [Konstruktoren](constructors.md). Die Instanzen der Klasse werden mit dem Schlüsselwort `new` instanziiert.  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Objektorientierte Programmierung](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [Polymorphismus](polymorphism.md)
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
- [Mitglieder](members.md)
- [Methoden](methods.md)
- [Konstruktoren](constructors.md)
- [Finalizer](destructors.md)
- [Objekte](objects.md)
