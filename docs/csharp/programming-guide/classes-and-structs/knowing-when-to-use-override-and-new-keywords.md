---
title: Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden? – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 0a209b9522202649765654013fdc3a468913c6b1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714777"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="bad5e-102">Wann müssen die Schlüsselwörter "override" und "new" verwendet werden? (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bad5e-102">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>

<span data-ttu-id="bad5e-103">In C# kann eine Methode in einer abgeleiteten Klasse den gleichen Namen wie eine Methode in einer Basisklasse haben.</span><span class="sxs-lookup"><span data-stu-id="bad5e-103">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="bad5e-104">Sie können mit den Schlüsselwörtern [new](../../language-reference/keywords/new-modifier.md) und [override](../../language-reference/keywords/override.md) festlegen, wie die Methoden interagieren.</span><span class="sxs-lookup"><span data-stu-id="bad5e-104">You can specify how the methods interact by using the [new](../../language-reference/keywords/new-modifier.md) and [override](../../language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="bad5e-105">Der `override`-Modifizierer *erweitert* die `virtual`-Methode der Basisklasse, und der `new`-Modifizierer *verbirgt* eine zugängliche Methode der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="bad5e-105">The `override` modifier *extends* the base class `virtual` method, and the `new` modifier *hides* an accessible base class method.</span></span> <span data-ttu-id="bad5e-106">Der Unterschied wird in den Beispielen in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bad5e-106">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="bad5e-107">Deklarieren Sie in einer Konsolenanwendung die folgenden beiden Klassen: `BaseClass` und `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-107">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="bad5e-108">`DerivedClass` erbt von `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-108">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-109">Deklarieren Sie in der `Main`-Methode die Variablen `bc`, `dc` und `bcdc`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-109">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
- <span data-ttu-id="bad5e-110">`bc` ist vom Typ `BaseClass`, und sein Wert ist vom Typ `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-110">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
- <span data-ttu-id="bad5e-111">`dc` ist vom Typ `DerivedClass`, und sein Wert ist vom Typ `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-111">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
- <span data-ttu-id="bad5e-112">`bcdc` ist vom Typ `BaseClass`, und sein Wert ist vom Typ `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-112">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="bad5e-113">Auf diese Variable müssen Sie achten.</span><span class="sxs-lookup"><span data-stu-id="bad5e-113">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="bad5e-114">Da `bc` und `bcdc` vom Typ `BaseClass` sind, können sie nur direkt auf `Method1` zugreifen, es sei denn, sie verwenden Umwandlungen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-114">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="bad5e-115">Die Variable `dc` kann sowohl auf `Method1` als auch auf `Method2` zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-115">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="bad5e-116">Diese Beziehungen werden im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-116">These relationships are shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-117">Fügen Sie als Nächstes die folgende `Method2`-Methode in `BaseClass` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bad5e-117">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="bad5e-118">Die Signatur dieser Methode entspricht der Signatur der `Method2`-Methode in `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-118">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="bad5e-119">Weil `BaseClass` jetzt über eine `Method2`-Methode verfügt, kann eine zweite aufrufende Anweisung für die `BaseClass`-Variablen `bc` und `bcdc` hinzugefügt werden, wie in folgendem Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-119">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="bad5e-120">Wenn Sie das Projekt erstellen, stellen sie fest, dass das Hinzufügen der `Method2`-Methode in `BaseClass` zu einer Warnmeldung führt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-120">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="bad5e-121">In der Warnmeldung steht, dass die `Method2`-Methode in `DerivedClass` die `Method2`-Methode in `BaseClass` verbirgt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-121">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="bad5e-122">Es wird empfohlen, dass Sie das `new`-Schlüsselwort in der `Method2`-Definition verwenden, wenn Sie möchten, dass es zu diesem Ergebnis kommt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-122">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="bad5e-123">Alternativ können Sie eine der `Method2`-Methoden umbenennen, um die Warnung aufzulösen. Dies muss jedoch nicht immer praktikabel sein.</span><span class="sxs-lookup"><span data-stu-id="bad5e-123">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="bad5e-124">Führen Sie das Programm aus, bevor Sie `new` hinzufügen, um die Ausgabe der zusätzlichen aufrufenden Anweisungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-124">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="bad5e-125">Die folgenden Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-125">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="bad5e-126">Das `new`-Schlüsselwort erhält die Beziehungen, die diese Ausgabe verursachen, aber es unterdrückt die Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="bad5e-126">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="bad5e-127">Die Variablen vom Typ `BaseClass` greifen weiterhin auf die Member von `BaseClass` zu, und die Variable des Typs `DerivedClass` greift weiterhin zuerst auf Member in `DerivedClass` zu, und kümmert sich dann um von `BaseClass` geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="bad5e-127">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="bad5e-128">Fügen sie den `new`-Modifizierer in die Definition von `Method2` in `DerivedClass` ein, wie in folgendem Code gezeigt, um die Warnmeldung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="bad5e-128">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="bad5e-129">Der Modifizierer kann vor oder hinter `public` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bad5e-129">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="bad5e-130">Führen Sie das Programm erneut aus, um sicherzustellen, dass die Ausgabe gleich geblieben ist.</span><span class="sxs-lookup"><span data-stu-id="bad5e-130">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="bad5e-131">Überprüfen Sie außerdem, ob die Warnung weiterhin angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bad5e-131">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="bad5e-132">Wenn Sie `new` verwenden, bestätigen Sie, dass Ihnen bewusst ist, dass der davon modifizierte Member einen Member verbirgt, der von der Basisklasse vererbt wird.</span><span class="sxs-lookup"><span data-stu-id="bad5e-132">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="bad5e-133">Weitere Informationen zum Verbergen von Namen durch die Vererbung finden Sie unter [new-Modifizierer](../../language-reference/keywords/new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="bad5e-133">For more information about name hiding through inheritance, see [new Modifier](../../language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="bad5e-134">Fügen Sie die folgende Methode in `DerivedClass` ein, um dieses Verhalten den Auswirkungen durch das Verwenden von `override` gegenüberzustellen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-134">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="bad5e-135">Der `override`-Modifizierer kann vor oder hinter `public` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bad5e-135">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="bad5e-136">Fügen Sie der Definition von `Method1` in `BaseClass` den `virtual`-Modifizierer hinzu.</span><span class="sxs-lookup"><span data-stu-id="bad5e-136">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="bad5e-137">Der `virtual`-Modifizierer kann vor oder hinter `public` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bad5e-137">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="bad5e-138">Führen Sie das Projekt erneut aus.</span><span class="sxs-lookup"><span data-stu-id="bad5e-138">Run the project again.</span></span> <span data-ttu-id="bad5e-139">Achten Sie besonders auf die letzten beiden Zeilen der folgenden Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bad5e-139">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="bad5e-140">Durch den `override`-Modifizierer kann `bcdc` auf die in `DerivedClass` definierte `Method1`-Methode zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-140">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="bad5e-141">Normalerweise ist dies das gewünschte Verhalten in Vererbungshierarchien.</span><span class="sxs-lookup"><span data-stu-id="bad5e-141">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="bad5e-142">Objekte sollten Werte aufweisen, die aus der abgeleiteten Klasse erzeugt werden, um die Methoden, die in der abgeleiteten Klasse definiert sind, verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="bad5e-142">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="bad5e-143">Dieses Verhalten erzielen Sie, indem Sie `override` verwenden, um die Methode der Basisklasse zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="bad5e-143">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="bad5e-144">Der folgende Code umfasst das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bad5e-144">The following code contains the full example.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-145">Das folgende Beispiel veranschaulicht ähnliches Verhalten in unterschiedlichen Kontexten.</span><span class="sxs-lookup"><span data-stu-id="bad5e-145">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="bad5e-146">Im Beispiel werden drei Klassen definiert: eine Basisklasse mit dem Namen `Car` und zwei Klassen, die von dieser Basisklasse abgeleitet werden, `ConvertibleCar` und `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-146">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="bad5e-147">Die Basisklasse enthält eine `DescribeCar`-Methode.</span><span class="sxs-lookup"><span data-stu-id="bad5e-147">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="bad5e-148">Die Methode zeigt eine grundlegende Beschreibung eines Autos und ruft dann `ShowDetails` auf, um zusätzliche Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-148">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="bad5e-149">Jede der drei Klassen definiert eine `ShowDetails`-Methode.</span><span class="sxs-lookup"><span data-stu-id="bad5e-149">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="bad5e-150">Der `new`-Modifizierer wird für die Definition von `ShowDetails` in der `ConvertibleCar`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="bad5e-150">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="bad5e-151">Der `override`-Modifizierer wird für die Definition von `ShowDetails` in der `Minivan`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="bad5e-151">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-152">In dem Beispiel wird geprüft, welche Version von `ShowDetails` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bad5e-152">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="bad5e-153">Die folgende Methode, `TestCars1`, deklariert eine Instanz jeder Klasse und ruft dann `DescribeCar` auf jeder Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="bad5e-153">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-154">`TestCars1` erzeugt die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bad5e-154">`TestCars1` produces the following output.</span></span> <span data-ttu-id="bad5e-155">Achten Sie besonders auf die Ergebnis für `car2`, die wahrscheinlich nicht dem entsprechen, was Sie erwartet haben.</span><span class="sxs-lookup"><span data-stu-id="bad5e-155">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="bad5e-156">Der Typ des Objekts ist `ConvertibleCar`. Allerdings greift `DescribeCar` nicht auf die Version von `ShowDetails` zu, die in der `ConvertibleCar`-Klasse definiert wurde, da diese Methode mit dem `new`-Modifizierer und nicht dem `override`-Modifizierer deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="bad5e-156">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="bad5e-157">Deshalb zeigt ein `ConvertibleCar`-Objekt die gleiche Beschreibung wie ein `Car`-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="bad5e-157">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="bad5e-158">Stellen Sie die Ergebnis von `car3` gegenüber, das ein `Minivan`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="bad5e-158">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="bad5e-159">In diesem Fall setzt die `ShowDetails`-Methode, die in der `Minivan`-Klasse deklariert wurde, die `ShowDetails`-Methode, die in der `Car`-Klasse deklariert wurde, außer Kraft, und es wird eine Beschreibung eines Minivans angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-159">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-160">`TestCars2` erstellt eine Liste von Objekten des Typs `Car`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-160">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="bad5e-161">Die Werte der Objekte werden von den Klassen `Car`, `ConvertibleCar` und `Minivan` instanziiert.</span><span class="sxs-lookup"><span data-stu-id="bad5e-161">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="bad5e-162">`DescribeCar` wird auf jedem Element in der Liste aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bad5e-162">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="bad5e-163">Der folgende Code veranschaulicht die Definition von `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="bad5e-163">The following code shows the definition of `TestCars2`.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-164">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad5e-164">The following output is displayed.</span></span> <span data-ttu-id="bad5e-165">Beachten Sie, dass sie der Ausgabe, die von `TestCars1` angezeigt wird, entspricht.</span><span class="sxs-lookup"><span data-stu-id="bad5e-165">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="bad5e-166">Die `ShowDetails`-Methode der `ConvertibleCar`-Klasse wird nicht aufgerufen, unabhängig davon, ob der Typ des Objekts `ConvertibleCar`, wie in `TestCars1`, oder `Car`, wie in `TestCars2`, ist.</span><span class="sxs-lookup"><span data-stu-id="bad5e-166">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="bad5e-167">Umgekehrt ruft `car3` in beiden Fällen die `ShowDetails`-Methode der `Minivan`-Klasse auf, egal, ob es vom Typ `Minivan` oder `Car` ist.</span><span class="sxs-lookup"><span data-stu-id="bad5e-167">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-168">Die Methoden `TestCars3` und `TestCars4` schließen das Beispiel ab.</span><span class="sxs-lookup"><span data-stu-id="bad5e-168">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="bad5e-169">Diese Methoden rufen `ShowDetails` direkt auf. Zuerst von Objekte, die mit den Typen `ConvertibleCar` und `Minivan` (`TestCars3`) deklariert wurden, und anschließend von Objekten, die mit dem Typ `Car` (`TestCars4`) deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="bad5e-169">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="bad5e-170">Der folgende Code definiert diese beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="bad5e-170">The following code defines these two methods.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-171">Die Methoden erzeugen folgende Ausgabe, die den Ergebnissen des ersten Beispiels in diesem Thema entspricht.</span><span class="sxs-lookup"><span data-stu-id="bad5e-171">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
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
  
 <span data-ttu-id="bad5e-172">Der folgende Code veranschaulicht das vollständige Projekt und dessen Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bad5e-172">The following code shows the complete project and its output.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bad5e-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bad5e-173">See also</span></span>

- [<span data-ttu-id="bad5e-174">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bad5e-174">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bad5e-175">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="bad5e-175">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="bad5e-176">Versionsverwaltung mit den Schlüsselwörtern "override" und "new"</span><span class="sxs-lookup"><span data-stu-id="bad5e-176">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="bad5e-177">base</span><span class="sxs-lookup"><span data-stu-id="bad5e-177">base</span></span>](../../language-reference/keywords/base.md)
- [<span data-ttu-id="bad5e-178">abstract</span><span class="sxs-lookup"><span data-stu-id="bad5e-178">abstract</span></span>](../../language-reference/keywords/abstract.md)
