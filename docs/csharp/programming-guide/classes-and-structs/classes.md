---
title: Klassen (C#-Programmierhandbuch)
description: Erfahren Sie mehr über die Klassentypen und wie diese erstellt werden
ms.date: 04/05/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 808e25315b0010fd55112f2ed237485c3d0c40d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="classes-c-programming-guide"></a>Klassen (C#-Programmierhandbuch)
Ein *Klasse* ist ein Konstrukt, das Ihnen ermöglicht, Ihre eigenen benutzerdefinierten Typen erstellen, indem Variablen anderer Typen, Methoden und Ereignisse zusammengefasst werden. Eine Klasse ist mit einem Entwurf vergleichbar. Sie definiert die Daten und das Verhalten eines Typs. Wenn die Klasse nicht als statisch deklariert wird, kann der Clientcode *Instanzen* von ihr erstellen. Diese Instanzen sind *Objekte*, die einer Variable zugewiesen werden. Die Instanz einer Klasse verbleibt im Arbeitsspeicher, bis alle Verweise darauf ihre Gültigkeit verlieren. Zu diesem Zeitpunkt markiert die CLR sie als geeignet für die Garbage Collection. Wenn die Klasse als [statisch](../../../csharp/language-reference/keywords/static.md) deklariert wird, können Sie keine Instanzen erstellen, und der Clientcode kann nur über die Klasse selbst auf sie zugreifen. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  

## <a name="reference-types"></a>Verweistypen  
Ein Typ, der als [Klasse](../../../csharp/language-reference/keywords/class.md) definiert ist, ist ein *Referenztyp*. Wenn Sie zur Laufzeit eine Variable eines Referenztyps deklarieren, enthält die Variable zunächst den Wert [NULL](../../../csharp/language-reference/keywords/null.md), bis Sie explizit eine Instanz der Klasse mithilfe des Operators [new](../../../csharp/language-reference/keywords/new.md) erstellen oder ihr ein Objekt zuweisen, das wie im folgenden Beispiel an anderer Stelle erstellt wurde:

```csharp
MyClass mc = new MyClass();
MyClass mc2 = mc;
```

Beim Erstellen des Objekts wird der Speicher im verwalteten Heap belegt. Die Variable enthält lediglich einen Verweis auf den Speicherort des Objekts. Für Typen im verwalteten Heap ist Mehraufwand erforderlich, wenn sie zugewiesen werden und wenn sie von der automatischen Speicherverwaltungsfunktion der CLR freigegeben werden, was als *Garbage Collection* bezeichnet wird. Die Garbage Collection ist jedoch auch stark optimiert. In den meisten Szenarios führt sie nicht zu einem Leistungsproblem. Weitere Informationen zur Garbage Collection finden Sie unter [Automatische Speicherverwaltung und Garbage Collection](../../../standard/garbage-collection/gc.md).  
  
## <a name="declaring-classes"></a>Deklarieren von Klassen  
 Klassen werden mithilfe des Schlüsselworts [class](../../../csharp/language-reference/keywords/class.md) deklariert, so wie im folgenden Beispiel dargestellt:

 ```csharp
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 Das `class`-Schlüsselwort wird der Zugriffsebene vorangestellt. Jeder kann Instanzen dieser Klasse erstellen, da in diesem Fall [public](../../../csharp/language-reference/keywords/public.md) verwendet wird. Der Name der Klasse folgt dem `class`-Schlüsselwort. Der Rest der Definition ist der Text einer Klasse, in dem das Verhalten und die Daten definiert sind. Felder, Eigenschaften, Methoden und Ereignisse für eine Klasse werden zusammen als *Klassenmember* bezeichnet.  
  
## <a name="creating-objects"></a>Erstellen von Objekten  
 Obwohl sie manchmal synonym werden, sind eine Klasse und ein Objekt unterschiedliche Dinge. Eine Klasse definiert einen Typ eines Objekts, aber es ist kein Objekt selbst. Ein Objekt ist eine konkrete Entität, basierend auf einer Klasse, und wird manchmal als Instanz einer Klasse bezeichnet.  
  
 Objekte können mithilfe des Schlüsselworts [new](../../../csharp/language-reference/keywords/new.md) erstellt werden, gefolgt vom Namen der Klasse, auf die das Objekt basiert, z.B.:  

 ```csharp
 Customer object1 = new Customer();
 ```
  
 Wenn eine Instanz einer Klasse erstellt wird, wird ein Verweis auf das Objekt an den Programmierer übergeben. Im vorherigen Beispiel ist `object1` ein Verweis auf ein Objekt, das auf `Customer` basiert. Dieser Verweis bezieht sich auf das neue Objekt, enthält jedoch nicht die Objektdaten selbst. In der Tat können Sie einen Objektverweis erstellen, ohne ein Objekt zu erstellen:  
  
  ```csharp
  Customer object2;
  ```
  
 Es wird nicht empfohlen, einen Objektverweis wie diesen zu erstellen, der auf kein Objekt verweist. Der Versuch, auf ein Objekt über solch einen Verweis zuzugreifen, schlägt während der Laufzeit fehl. Allerdings kann ein solcher Verweis dazu veranlasst werden, auf ein Objekt zu verweisen, indem entweder ein neues Objekt erstellt wird oder indem es einem vorhandenen Objekt zugewiesen wird, z.B.:  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
 ```
  
 Dieser Code erstellt zwei Objektverweise, die beide auf dasselbe Objekt verweisen. Aus diesem Grund werden alle Änderungen am Objekt, die über `object3` getätigt worden sind, bei nachfolgenden Verwendungen von `object4` berücksichtigt. Da auf Objekte, die auf Klassen basieren, durch Verweise zurückgegriffen werden, sind Klassen als Verweistypen bekannt.  
  
## <a name="class-inheritance"></a>Klassenvererbung  

 Klassen unterstützen die *Vererbung* vollständig. Dies ist ein wesentliches Merkmal der objektorientierten Programmierung. Wenn Sie eine Klasse erstellen, können Sie von einer anderen Schnittstelle oder Klasse erben, die nicht als [versiegelt](../../../csharp/language-reference/keywords/sealed.md) definiert ist. Andere Klassen können von Ihrer Klasse erben und die virtuellen Methoden überschreiben.

 Die Vererbung erfolgt durch Verwendung einer *Ableitung*, d.h., dass eine Klasse mithilfe einer *Basisklasse* deklariert wird, aus der Sie Daten und das Verhalten erbt. Eine Basisklasse wird durch Anhängen eines Doppelpunkts sowie den Namen der Basisklasse angegeben, die dem abgeleiteten Klassennamen folgt, z.B.:  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```
  
 Wenn eine Klasse eine Basisklasse deklariert, erbt sie alle Member der Basisklasse mit Ausnahme der Konstruktoren. Weitere Informationen finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).
  
 Anders als in C++ kann eine Klasse in C# nur direkt von einer Basisklasse erben. Da jedoch eine Basisklasse von einer anderen Klasse erben kann, kann eine Klasse indirekt von mehreren Basisklassen erben. Darüber hinaus kann eine Klasse mehr als eine Schnittstelle direkt implementieren. Weitere Informationen finden Sie unter [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md).  
  
 Eine Klasse kann als [abstrakt](../../../csharp/language-reference/keywords/abstract.md) deklariert werden. Eine abstrakte Klasse enthält abstrakte Methoden, die über eine Signaturdefinition, aber keine Implementierung verfügen. Abstrakte Klassen dürfen nicht instanziiert werden. Sie können nur mithilfe von abgeleiteten Klassen verwendet werden, die die abstrakten Methoden implementieren. Im Gegensatz dazu lässt eine [versiegelte](../../../csharp/language-reference/keywords/sealed.md) Klasse nicht zu, dass andere Klassen von ihr ableiten. Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Klassendefinitionen können zwischen verschiedenen Quelldateien aufgeteilt werden. Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="description"></a>description  
 Im folgenden Beispiel wird eine öffentliche Klasse definiert, die ein einzelnes Feld, eine Methode und eine spezielle Methode namens Konstruktor enthält. Weitere Informationen finden Sie unter [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md). Die Klasse wird mit dem Schlüsselwort `new` instanziiert.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)] 
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Objektorientierte Programmierung](../concepts/object-oriented-programming.md)  
 [Polymorphismus](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [Mitglieder](../../../csharp/programming-guide/classes-and-structs/members.md)  
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [Objekte](../../../csharp/programming-guide/classes-and-structs/objects.md)
