---
title: Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden? – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 493c6c5f5bf47c6b2cd140ac0f6922f91ca4252b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170259"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a>Wann müssen die Schlüsselwörter "override" und "new" verwendet werden? (C#-Programmierhandbuch)

In C# kann eine Methode in einer abgeleiteten Klasse den gleichen Namen wie eine Methode in einer Basisklasse haben. Sie können mit den Schlüsselwörtern [new](../../language-reference/keywords/new-modifier.md) und [override](../../language-reference/keywords/override.md) festlegen, wie die Methoden interagieren. Der `override`-Modifizierer *erweitert* die `virtual`-Methode der Basisklasse, und der `new`-Modifizierer *verbirgt* eine zugängliche Methode der Basisklasse. Der Unterschied wird in den Beispielen in diesem Thema veranschaulicht.  
  
 Deklarieren Sie in einer Konsolenanwendung die folgenden beiden Klassen: `BaseClass` und `DerivedClass`. `DerivedClass` erbt von `BaseClass`.  
  
```csharp  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
```  
  
 Deklarieren Sie in der `Main`-Methode die Variablen `bc`, `dc` und `bcdc`.  
  
- `bc` ist vom Typ `BaseClass`, und sein Wert ist vom Typ `BaseClass`.  
  
- `dc` ist vom Typ `DerivedClass`, und sein Wert ist vom Typ `DerivedClass`.  
  
- `bcdc` ist vom Typ `BaseClass`, und sein Wert ist vom Typ `DerivedClass`. Auf diese Variable müssen Sie achten.  
  
 Da `bc` und `bcdc` vom Typ `BaseClass` sind, können sie nur direkt auf `Method1` zugreifen, es sei denn, sie verwenden Umwandlungen. Die Variable `dc` kann sowohl auf `Method1` als auch auf `Method2` zugreifen. Diese Beziehungen werden im folgenden Code gezeigt.  
  
```csharp  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
```  
  
 Fügen Sie als Nächstes die folgende `Method2`-Methode in `BaseClass` hinzu. Die Signatur dieser Methode entspricht der Signatur der `Method2`-Methode in `DerivedClass`.  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 Weil `BaseClass` jetzt über eine `Method2`-Methode verfügt, kann eine zweite aufrufende Anweisung für die `BaseClass`-Variablen `bc` und `bcdc` hinzugefügt werden, wie in folgendem Code gezeigt.  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 Wenn Sie das Projekt erstellen, stellen sie fest, dass das Hinzufügen der `Method2`-Methode in `BaseClass` zu einer Warnmeldung führt. In der Warnmeldung steht, dass die `Method2`-Methode in `DerivedClass` die `Method2`-Methode in `BaseClass` verbirgt. Es wird empfohlen, dass Sie das `new`-Schlüsselwort in der `Method2`-Definition verwenden, wenn Sie möchten, dass es zu diesem Ergebnis kommt. Alternativ können Sie eine der `Method2`-Methoden umbenennen, um die Warnung aufzulösen. Dies muss jedoch nicht immer praktikabel sein.  
  
 Führen Sie das Programm aus, bevor Sie `new` hinzufügen, um die Ausgabe der zusätzlichen aufrufenden Anweisungen zu überprüfen. Die folgenden Ergebnisse werden angezeigt.  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 Das `new`-Schlüsselwort erhält die Beziehungen, die diese Ausgabe verursachen, aber es unterdrückt die Warnmeldung. Die Variablen vom Typ `BaseClass` greifen weiterhin auf die Member von `BaseClass` zu, und die Variable des Typs `DerivedClass` greift weiterhin zuerst auf Member in `DerivedClass` zu, und kümmert sich dann um von `BaseClass` geerbte Member.  
  
 Fügen sie den `new`-Modifizierer in die Definition von `Method2` in `DerivedClass` ein, wie in folgendem Code gezeigt, um die Warnmeldung zu unterdrücken. Der Modifizierer kann vor oder hinter `public` eingefügt werden.  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 Führen Sie das Programm erneut aus, um sicherzustellen, dass die Ausgabe gleich geblieben ist. Überprüfen Sie außerdem, ob die Warnung weiterhin angezeigt wird. Wenn Sie `new` verwenden, bestätigen Sie, dass Ihnen bewusst ist, dass der davon modifizierte Member einen Member verbirgt, der von der Basisklasse vererbt wird. Weitere Informationen zum Verbergen von Namen durch die Vererbung finden Sie unter [new-Modifizierer](../../language-reference/keywords/new-modifier.md).  
  
 Fügen Sie die folgende Methode in `override` ein, um dieses Verhalten den Auswirkungen durch das Verwenden von `DerivedClass` gegenüberzustellen. Der `override`-Modifizierer kann vor oder hinter `public` eingefügt werden.  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 Fügen Sie der Definition von `virtual` in `Method1` den `BaseClass`-Modifizierer hinzu. Der `virtual`-Modifizierer kann vor oder hinter `public` eingefügt werden.  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 Führen Sie das Projekt erneut aus. Achten Sie besonders auf die letzten beiden Zeilen der folgenden Ausgabe.  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 Durch den `override`-Modifizierer kann `bcdc` auf die in `Method1` definierte `DerivedClass`-Methode zugreifen. Normalerweise ist dies das gewünschte Verhalten in Vererbungshierarchien. Objekte sollten Werte aufweisen, die aus der abgeleiteten Klasse erzeugt werden, um die Methoden, die in der abgeleiteten Klasse definiert sind, verwenden zu können. Dieses Verhalten erzielen Sie, indem Sie `override` verwenden, um die Methode der Basisklasse zu erweitern.  
  
 Der folgende Code umfasst das vollständige Beispiel.  
  
```csharp  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
```  
  
 Das folgende Beispiel veranschaulicht ähnliches Verhalten in unterschiedlichen Kontexten. Im Beispiel werden drei Klassen definiert: eine Basisklasse mit dem Namen `Car` und zwei Klassen, die von dieser Basisklasse abgeleitet werden, `ConvertibleCar` und `Minivan`. Die Basisklasse enthält eine `DescribeCar`-Methode. Die Methode zeigt eine grundlegende Beschreibung eines Autos und ruft dann `ShowDetails` auf, um zusätzliche Informationen bereitzustellen. Jede der drei Klassen definiert eine `ShowDetails`-Methode. Der `new`-Modifizierer wird für die Definition von `ShowDetails` in der `ConvertibleCar`-Klasse verwendet. Der `override`-Modifizierer wird für die Definition von `ShowDetails` in der `Minivan`-Klasse verwendet.  
  
```csharp  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
```  
  
 In dem Beispiel wird geprüft, welche Version von `ShowDetails` aufgerufen wird. Die folgende Methode, `TestCars1`, deklariert eine Instanz jeder Klasse und ruft dann `DescribeCar` auf jeder Instanz auf.  
  
```csharp  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
```  
  
 `TestCars1` erzeugt die folgende Ausgabe. Achten Sie besonders auf die Ergebnis für `car2`, die wahrscheinlich nicht dem entsprechen, was Sie erwartet haben. Der Typ des Objekts ist `ConvertibleCar`. Allerdings greift `DescribeCar` nicht auf die Version von `ShowDetails` zu, die in der `ConvertibleCar`-Klasse definiert wurde, da diese Methode mit dem `new`-Modifizierer und nicht dem `override`-Modifizierer deklariert wird. Deshalb zeigt ein `ConvertibleCar`-Objekt die gleiche Beschreibung wie ein `Car`-Objekt an. Stellen Sie die Ergebnis von `car3` gegenüber, das ein `Minivan`-Objekt ist. In diesem Fall setzt die `ShowDetails`-Methode, die in der `Minivan`-Klasse deklariert wurde, die `ShowDetails`-Methode, die in der `Car`-Klasse deklariert wurde, außer Kraft, und es wird eine Beschreibung eines Minivans angezeigt.  
  
```csharp  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 `TestCars2` erstellt eine Liste von Objekten des Typs `Car`. Die Werte der Objekte werden von den Klassen `Car`, `ConvertibleCar` und `Minivan` instanziiert. `DescribeCar` wird auf jedem Element in der Liste aufgerufen. Der folgende Code veranschaulicht die Definition von `TestCars2`.  
  
```csharp  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
```  
  
 Die folgende Ausgabe wird angezeigt. Beachten Sie, dass sie der Ausgabe, die von `TestCars1` angezeigt wird, entspricht. Die `ShowDetails`-Methode der `ConvertibleCar`-Klasse wird nicht aufgerufen, unabhängig davon, ob der Typ des Objekts `ConvertibleCar`, wie in `TestCars1`, oder `Car`, wie in `TestCars2`, ist. Umgekehrt ruft `car3` in beiden Fällen die `ShowDetails`-Methode der `Minivan`-Klasse auf, egal, ob es vom Typ `Minivan` oder `Car` ist.  
  
```csharp  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 Die Methoden `TestCars3` und `TestCars4` schließen das Beispiel ab. Diese Methoden rufen `ShowDetails` direkt auf. Zuerst von Objekte, die mit den Typen `ConvertibleCar` und `Minivan` (`TestCars3`) deklariert wurden, und anschließend von Objekten, die mit dem Typ `Car` (`TestCars4`) deklariert wurden. Der folgende Code definiert diese beiden Methoden.  
  
```csharp  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
```  
  
 Die Methoden erzeugen folgende Ausgabe, die den Ergebnissen des ersten Beispiels in diesem Thema entspricht.  
  
```csharp  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
```  
  
 Der folgende Code veranschaulicht das vollständige Projekt und dessen Ausgabe.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Versionsverwaltung mit den Schlüsselwörtern "override" und "new"](./versioning-with-the-override-and-new-keywords.md)
- [base](../../language-reference/keywords/base.md)
- [abstract](../../language-reference/keywords/abstract.md)
