---
title: "Wann m&#252;ssen die Schl&#252;sselw&#246;rter &quot;override&quot; und &quot;new&quot; verwendet werden? (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new-Schlüsselwort [C#]"
  - "override-Schlüsselwort [C#]"
  - "Polymorphismus [C#], Verwenden von override und new [C#]"
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Wann m&#252;ssen die Schl&#252;sselw&#246;rter &quot;override&quot; und &quot;new&quot; verwendet werden? (C#-Programmierhandbuch)
In C\# kann eine Methode in einer abgeleiteten Klasse den gleichen Namen wie eine Methode in der Basisklasse haben.  Sie können angeben, wie die Methoden interagieren, indem Sie die Schlüsselwörter [new](../../../csharp/language-reference/keywords/new.md) und [override](../../../csharp/language-reference/keywords/override.md) verwenden.  Der `override`\-Modifizierer *erweitert* die Basisklassenmethode, und der `new`\-Modifizierer *blendet* sie aus.  Der Unterschied wird in den Beispielen in diesem Thema veranschaulicht.  
  
 In einer Konsolenanwendung deklarieren Sie die folgenden beiden Klassen `BaseClass` und `DerivedClass`.  `DerivedClass` erbt von `BaseClass`.  
  
```c#  
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
  
 Deklarieren Sie in der `Main`\-Methode die Variablen `bc`, `dc` und `bcdc`.  
  
-   `bc` ist vom Typ `BaseClass` und sein Wert ist vom Typ `BaseClass`.  
  
-   `dc` ist vom Typ `DerivedClass` und sein Wert ist vom Typ `DerivedClass`.  
  
-   `bcdc` ist vom Typ `BaseClass` und sein Wert ist vom Typ `DerivedClass`.  Dabei handelt es sich um die Variable, die beachtet werden muss.  
  
 Da `bc` und `bcdc` vom Typ `BaseClass` sind, können sie nur direkt auf `Method1`zugreifen, falls keine Umwandlung verwendet wird.  Die Variable `dc` kann auf `Method1` und `Method2` zugreifen.  Diese Beziehungen werden im folgenden Code gezeigt.  
  
```c#  
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
  
 Fügen Sie dann die folgende `Method2`\-Methode `BaseClass` hinzu.  Die Signatur dieser Methode entspricht der Signatur der `Method2`\-Methode in `DerivedClass`.  
  
```c#  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
  
```  
  
 Da `BaseClass` nun eine `Method2`\-Methode aufweist, kann eine zweite Aufrufanweisung für `BaseClass`\-Variablen `bc` und `bcdc` hinzugefügt werden, wie im folgenden Code dargestellt.  
  
```c#  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
  
```  
  
 Wenn Sie das Projekt erstellen, sehen Sie, dass das Hinzufügen der `Method2`\-Methode in `BaseClass` eine Warnung auslöst.  Die Warnung besagt, dass die `Method2`\-Methode in `DerivedClass` die `Method2`\-Methode in `BaseClass` ausblendet.  Es wird empfohlen, das `new`\-Schlüsselwort in der `Method2`\-Definition zu verwenden, wenn Sie beabsichtigen, dieses Ergebnis zu verursachen.  Alternativ dazu können Sie eine der `Method2`\-Methoden umbenennen, um die Warnung zu vermeiden, doch dies ist nicht immer zweckmäßig.  
  
 Führen Sie vor dem Hinzufügen von `new` das Programm aus, um die durch die zusätzlichen Aufrufanweisungen erzeugte Ausgabe anzuzeigen.  Die folgenden Ergebnisse werden angezeigt.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
  
```  
  
 Das `new`\-Schlüsselwort behält die Beziehungen bei, die diese Ausgabe erzeugen, unterdrückt jedoch die Warnung.  Die Variablen vom Typ `BaseClass` greifen weiterhin auf die Member von `BaseClass` zu, und die Variable vom Typ `DerivedClass` greift weiterhin zuerst auf Member in `DerivedClass` zu und berücksichtigt anschließend von `BaseClass` vererbte Member.  
  
 Um die Warnung zu unterdrücken, fügen Sie den `new`\-Modifizierer zur Definition von `Method2` in `DerivedClass` hinzu, wie im folgenden Code gezeigt.  Der Modifizierer kann vor oder nach `public` hinzugefügt werden.  
  
```c#  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
  
```  
  
 Führen Sie das Programm erneut aus, um sicherzustellen, dass die Ausgabe nicht geändert wurde.  Stellen Sie außerdem sicher, dass die Warnung nicht mehr angezeigt wird.  Durch Verwenden von `new` bestätigen Sie, dass Ihnen klar ist, dass der ändernde Member einen aus der Basisklasse geerbten Member ausblendet.  Weitere Informationen zum Verbergen des Namens durch Vererbung finden Sie unter [new\-Modifizierer](../../../csharp/language-reference/keywords/new-modifier.md).  
  
 Um dieses Verhalten mit den Auswirkungen der Verwendung von `override` zu vergleichen, fügen Sie die folgende Methode zu `DerivedClass` hinzu.  Der `override`\-Modifizierer kann vor oder nach `public` hinzugefügt werden.  
  
```c#  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
  
```  
  
 Fügen Sie den `virtual`\-Modifizierer der Definition von `Method1` in `BaseClass` hinzu.  Der `virtual`\-Modifizierer kann vor oder nach `public` hinzugefügt werden.  
  
```c#  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
  
```  
  
 Führen Sie das Projekt erneut aus.  Beachten Sie vor allem die letzten beiden Zeilen der folgenden Ausgabe.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
  
```  
  
 Mit dem `override`\-Modifizierer kann `bcdc` auf die `Method1`\-Methode zugreifen, die in `DerivedClass` definiert ist.  In der Regel ist das das gewünschte Verhalten in Vererbungshierarchien.  Sie möchten, dass Objekte, die über Werte verfügen, die von der abgeleiteten Klasse erstellt werden, die Methoden verwenden, die in der abgeleiteten Klasse definiert sind.  Sie erzielen dieses Verhalten, indem Sie `override` verwenden, um die Basisklassenmethode zu erweitern.  
  
 Der folgende Code umfasst das vollständige Beispiel.  
  
```c#  
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
  
 Im folgenden Beispiel wird ähnliches Verhalten in einem anderen Kontext veranschaulicht.  Das Beispiel definiert drei Klassen: eine Basisklasse mit dem Namen `Car` und zwei Klassen, die davon abgeleitet wurden, `ConvertibleCar` und `Minivan`.  Die Basisklasse enthält eine `DescribeCar`\-Methode.  Die Methode zeigt eine einfache Beschreibung eines Autos an und ruft anschließend `ShowDetails` auf, um zusätzliche Informationen bereitzustellen.  Jede der drei Klassen definiert eine `ShowDetails`\-Methode.  Der `new`\-Modifizierer wird verwendet, um `ShowDetails` in der `ConvertibleCar`\-Klasse zu definieren.  Der `override`\-Modifizierer wird verwendet, um `ShowDetails` in der `Minivan`\-Klasse zu definieren.  
  
```c#  
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
  
 Im Beispiel wird getestet, welche Version von `ShowDetails` aufgerufen wird.  Die folgende Methode, `TestCars1`, deklariert eine Instanz jeder Klasse und ruft dann `DescribeCar` für jede Instanz auf.  
  
```c#  
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
  
 `TestCars1` erzeugt die folgende Ausgabe.  Beachten Sie vor allem die Ergebnisse für `car2`, die wahrscheinlich nicht das sind, was Sie erwartet haben.  Der Typ des Objekts ist `ConvertibleCar`, doch `DescribeCar` greift nicht auf die Version von `ShowDetails` zu, die in der `ConvertibleCar`\-Klasse definiert wird, da diese Methode mit dem `new`\-Modifizierer und nicht mit dem `override`\-Modifizierer deklariert wird.  Daher zeigt ein `ConvertibleCar`\-Objekt dieselbe Beschreibung wie ein `Car`\-Objekt an.  Vergleichen Sie die Ergebnisse für `car3`, das ein `Minivan`\-Objekt ist.  In diesem Fall überschreibt die `ShowDetails`\-Methode, die in der `Minivan`\-Klasse deklariert wurde, die `ShowDetails`\-Methode, die in der `Car`\-Klasse deklariert wurde, und die angezeigte Beschreibung beschreibt einen Minivan.  
  
```c#  
  
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
  
 `TestCars2` erstellt eine Liste von Objekten, die über Typ `Car` verfügen.  Die Werte der Objekte werden von den Klassen `Car`, `ConvertibleCar` und `Minivan` instanziiert.  `DescribeCar` wird für jedes Element der Liste aufgerufen.  Im folgenden Code wird die Definition von `TestCars2` veranschaulicht.  
  
```c#  
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
  
 Folgende Ausgabe wird angezeigt.  Beachten Sie, dass dies dasselbe wie die Ausgabe ist, die von `TestCars1` angezeigt wird.  Die `ShowDetails`\-Methode der `ConvertibleCar`\-Klasse wird nicht aufgerufen, unabhängig davon, ob der Typ des Objekts `ConvertibleCar` ist wie in `TestCars1` oder `Car` wie in `TestCars2`.  Dagegen ruft `car3` die `ShowDetails`\-Methode aus der `Minivan`\-Klasse in beiden Fällen auf, egal ob vom Typ `Minivan` oder `Car`.  
  
```c#  
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
  
 Die Methoden `TestCars3` und `TestCars4` schließen das Beispiel ab.  Diese Methoden rufen `ShowDetails` direkt zuerst von Objekten auf, die mit Typ `ConvertibleCar` und `Minivan` \(`TestCars3`\) deklariert wurden, und anschließend von Objekten, die mit Typ `Car` \(`TestCars4`\) deklariert wurden.  Der folgende Code definiert diese beiden Methoden.  
  
```c#  
  
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
  
 Die Methoden erzeugen die folgende Ausgabe, die den Ergebnissen aus dem ersten Beispiel in diesem Thema entspricht.  
  
```c#  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
  
```  
  
 Im folgenden Code wird das gesamte Projekt und seine Ausgabe angezeigt.  
  
```c#  
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
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Versionsverwaltung mit den Schlüsselwörtern "override" und "new"](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [Basis](../../../csharp/language-reference/keywords/base.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)