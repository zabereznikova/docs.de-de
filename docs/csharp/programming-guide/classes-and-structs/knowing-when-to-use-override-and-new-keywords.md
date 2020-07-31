---
title: Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden? – C#-Programmierhandbuch
description: Hier erhalten Sie Informationen zum Verwenden der Schlüsselwörter „new“ und „override“ in C# zum Angeben davon, wie Methoden mit demselben Namen in einer Basis-und einer abgeleiteten Klasse miteinander interagieren.
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 732a37c08b4c7bb998a7cc5dcfbd00d4e706b06c
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864539"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="d09f0-103">Wann müssen die Schlüsselwörter "override" und "new" verwendet werden? (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d09f0-103">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>

<span data-ttu-id="d09f0-104">In C# kann eine Methode in einer abgeleiteten Klasse den gleichen Namen wie eine Methode in einer Basisklasse haben.</span><span class="sxs-lookup"><span data-stu-id="d09f0-104">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="d09f0-105">Sie können mit den Schlüsselwörtern [new](../../language-reference/keywords/new-modifier.md) und [override](../../language-reference/keywords/override.md) festlegen, wie die Methoden interagieren.</span><span class="sxs-lookup"><span data-stu-id="d09f0-105">You can specify how the methods interact by using the [new](../../language-reference/keywords/new-modifier.md) and [override](../../language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="d09f0-106">Der `override`-Modifizierer *erweitert* die `virtual`-Methode der Basisklasse, und der `new`-Modifizierer *verbirgt* eine zugängliche Methode der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="d09f0-106">The `override` modifier *extends* the base class `virtual` method, and the `new` modifier *hides* an accessible base class method.</span></span> <span data-ttu-id="d09f0-107">Der Unterschied wird in den Beispielen in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d09f0-107">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="d09f0-108">Deklarieren Sie in einer Konsolenanwendung die folgenden beiden Klassen: `BaseClass` und `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-108">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="d09f0-109">`DerivedClass` erbt von `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-109">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-110">Deklarieren Sie in der `Main`-Methode die Variablen `bc`, `dc` und `bcdc`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-110">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
- <span data-ttu-id="d09f0-111">`bc` ist vom Typ `BaseClass`, und sein Wert ist vom Typ `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-111">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
- <span data-ttu-id="d09f0-112">`dc` ist vom Typ `DerivedClass`, und sein Wert ist vom Typ `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-112">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
- <span data-ttu-id="d09f0-113">`bcdc` ist vom Typ `BaseClass`, und sein Wert ist vom Typ `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-113">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="d09f0-114">Auf diese Variable müssen Sie achten.</span><span class="sxs-lookup"><span data-stu-id="d09f0-114">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="d09f0-115">Da `bc` und `bcdc` vom Typ `BaseClass` sind, können sie nur direkt auf `Method1` zugreifen, es sei denn, sie verwenden Umwandlungen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-115">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="d09f0-116">Die Variable `dc` kann sowohl auf `Method1` als auch auf `Method2` zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-116">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="d09f0-117">Diese Beziehungen werden im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-117">These relationships are shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-118">Fügen Sie als Nächstes die folgende `Method2`-Methode in `BaseClass` hinzu.</span><span class="sxs-lookup"><span data-stu-id="d09f0-118">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="d09f0-119">Die Signatur dieser Methode entspricht der Signatur der `Method2`-Methode in `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-119">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="d09f0-120">Weil `BaseClass` jetzt über eine `Method2`-Methode verfügt, kann eine zweite aufrufende Anweisung für die `BaseClass`-Variablen `bc` und `bcdc` hinzugefügt werden, wie in folgendem Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-120">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="d09f0-121">Wenn Sie das Projekt erstellen, stellen sie fest, dass das Hinzufügen der `Method2`-Methode in `BaseClass` zu einer Warnmeldung führt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-121">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="d09f0-122">In der Warnmeldung steht, dass die `Method2`-Methode in `DerivedClass` die `Method2`-Methode in `BaseClass` verbirgt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-122">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="d09f0-123">Es wird empfohlen, dass Sie das `new`-Schlüsselwort in der `Method2`-Definition verwenden, wenn Sie möchten, dass es zu diesem Ergebnis kommt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-123">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="d09f0-124">Alternativ können Sie eine der `Method2`-Methoden umbenennen, um die Warnung aufzulösen. Dies muss jedoch nicht immer praktikabel sein.</span><span class="sxs-lookup"><span data-stu-id="d09f0-124">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="d09f0-125">Führen Sie das Programm aus, bevor Sie `new` hinzufügen, um die Ausgabe der zusätzlichen aufrufenden Anweisungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-125">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="d09f0-126">Die folgenden Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-126">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="d09f0-127">Das `new`-Schlüsselwort erhält die Beziehungen, die diese Ausgabe verursachen, aber es unterdrückt die Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="d09f0-127">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="d09f0-128">Die Variablen vom Typ `BaseClass` greifen weiterhin auf die Member von `BaseClass` zu, und die Variable des Typs `DerivedClass` greift weiterhin zuerst auf Member in `DerivedClass` zu, und kümmert sich dann um von `BaseClass` geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="d09f0-128">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="d09f0-129">Fügen sie den `new`-Modifizierer in die Definition von `Method2` in `DerivedClass` ein, wie in folgendem Code gezeigt, um die Warnmeldung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="d09f0-129">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="d09f0-130">Der Modifizierer kann vor oder hinter `public` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d09f0-130">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="d09f0-131">Führen Sie das Programm erneut aus, um sicherzustellen, dass die Ausgabe gleich geblieben ist.</span><span class="sxs-lookup"><span data-stu-id="d09f0-131">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="d09f0-132">Überprüfen Sie außerdem, ob die Warnung weiterhin angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d09f0-132">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="d09f0-133">Wenn Sie `new` verwenden, bestätigen Sie, dass Ihnen bewusst ist, dass der davon modifizierte Member einen Member verbirgt, der von der Basisklasse vererbt wird.</span><span class="sxs-lookup"><span data-stu-id="d09f0-133">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="d09f0-134">Weitere Informationen zum Verbergen von Namen durch die Vererbung finden Sie unter [new-Modifizierer](../../language-reference/keywords/new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="d09f0-134">For more information about name hiding through inheritance, see [new Modifier](../../language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="d09f0-135">Fügen Sie die folgende Methode in `DerivedClass` ein, um dieses Verhalten den Auswirkungen durch das Verwenden von `override` gegenüberzustellen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-135">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="d09f0-136">Der `override`-Modifizierer kann vor oder hinter `public` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d09f0-136">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="d09f0-137">Fügen Sie der Definition von `Method1` in `BaseClass` den `virtual`-Modifizierer hinzu.</span><span class="sxs-lookup"><span data-stu-id="d09f0-137">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="d09f0-138">Der `virtual`-Modifizierer kann vor oder hinter `public` eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d09f0-138">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="d09f0-139">Führen Sie das Projekt erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d09f0-139">Run the project again.</span></span> <span data-ttu-id="d09f0-140">Achten Sie besonders auf die letzten beiden Zeilen der folgenden Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d09f0-140">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="d09f0-141">Durch den `override`-Modifizierer kann `bcdc` auf die in `DerivedClass` definierte `Method1`-Methode zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-141">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="d09f0-142">Normalerweise ist dies das gewünschte Verhalten in Vererbungshierarchien.</span><span class="sxs-lookup"><span data-stu-id="d09f0-142">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="d09f0-143">Objekte sollten Werte aufweisen, die aus der abgeleiteten Klasse erzeugt werden, um die Methoden, die in der abgeleiteten Klasse definiert sind, verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="d09f0-143">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="d09f0-144">Dieses Verhalten erzielen Sie, indem Sie `override` verwenden, um die Methode der Basisklasse zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d09f0-144">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="d09f0-145">Der folgende Code umfasst das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d09f0-145">The following code contains the full example.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-146">Das folgende Beispiel veranschaulicht ähnliches Verhalten in unterschiedlichen Kontexten.</span><span class="sxs-lookup"><span data-stu-id="d09f0-146">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="d09f0-147">Im Beispiel werden drei Klassen definiert: eine Basisklasse mit dem Namen `Car` und zwei Klassen, die von dieser Basisklasse abgeleitet werden, `ConvertibleCar` und `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-147">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="d09f0-148">Die Basisklasse enthält eine `DescribeCar`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d09f0-148">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="d09f0-149">Die Methode zeigt eine grundlegende Beschreibung eines Autos und ruft dann `ShowDetails` auf, um zusätzliche Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-149">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="d09f0-150">Jede der drei Klassen definiert eine `ShowDetails`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d09f0-150">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="d09f0-151">Der `new`-Modifizierer wird für die Definition von `ShowDetails` in der `ConvertibleCar`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d09f0-151">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="d09f0-152">Der `override`-Modifizierer wird für die Definition von `ShowDetails` in der `Minivan`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d09f0-152">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-153">In dem Beispiel wird geprüft, welche Version von `ShowDetails` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d09f0-153">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="d09f0-154">Die folgende Methode, `TestCars1`, deklariert eine Instanz jeder Klasse und ruft dann `DescribeCar` auf jeder Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="d09f0-154">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-155">`TestCars1` erzeugt die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d09f0-155">`TestCars1` produces the following output.</span></span> <span data-ttu-id="d09f0-156">Achten Sie besonders auf die Ergebnis für `car2`, die wahrscheinlich nicht dem entsprechen, was Sie erwartet haben.</span><span class="sxs-lookup"><span data-stu-id="d09f0-156">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="d09f0-157">Der Typ des Objekts ist `ConvertibleCar`. Allerdings greift `DescribeCar` nicht auf die Version von `ShowDetails` zu, die in der `ConvertibleCar`-Klasse definiert wurde, da diese Methode mit dem `new`-Modifizierer und nicht dem `override`-Modifizierer deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d09f0-157">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="d09f0-158">Deshalb zeigt ein `ConvertibleCar`-Objekt die gleiche Beschreibung wie ein `Car`-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="d09f0-158">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="d09f0-159">Stellen Sie die Ergebnis von `car3` gegenüber, das ein `Minivan`-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="d09f0-159">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="d09f0-160">In diesem Fall setzt die `ShowDetails`-Methode, die in der `Minivan`-Klasse deklariert wurde, die `ShowDetails`-Methode, die in der `Car`-Klasse deklariert wurde, außer Kraft, und es wird eine Beschreibung eines Minivans angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-160">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-161">`TestCars2` erstellt eine Liste von Objekten des Typs `Car`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-161">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="d09f0-162">Die Werte der Objekte werden von den Klassen `Car`, `ConvertibleCar` und `Minivan` instanziiert.</span><span class="sxs-lookup"><span data-stu-id="d09f0-162">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="d09f0-163">`DescribeCar` wird auf jedem Element in der Liste aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d09f0-163">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="d09f0-164">Der folgende Code veranschaulicht die Definition von `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="d09f0-164">The following code shows the definition of `TestCars2`.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-165">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d09f0-165">The following output is displayed.</span></span> <span data-ttu-id="d09f0-166">Beachten Sie, dass sie der Ausgabe, die von `TestCars1` angezeigt wird, entspricht.</span><span class="sxs-lookup"><span data-stu-id="d09f0-166">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="d09f0-167">Die `ShowDetails`-Methode der `ConvertibleCar`-Klasse wird nicht aufgerufen, unabhängig davon, ob der Typ des Objekts `ConvertibleCar`, wie in `TestCars1`, oder `Car`, wie in `TestCars2`, ist.</span><span class="sxs-lookup"><span data-stu-id="d09f0-167">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="d09f0-168">Umgekehrt ruft `car3` in beiden Fällen die `ShowDetails`-Methode der `Minivan`-Klasse auf, egal, ob es vom Typ `Minivan` oder `Car` ist.</span><span class="sxs-lookup"><span data-stu-id="d09f0-168">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-169">Die Methoden `TestCars3` und `TestCars4` schließen das Beispiel ab.</span><span class="sxs-lookup"><span data-stu-id="d09f0-169">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="d09f0-170">Diese Methoden rufen `ShowDetails` direkt auf. Zuerst von Objekte, die mit den Typen `ConvertibleCar` und `Minivan` (`TestCars3`) deklariert wurden, und anschließend von Objekten, die mit dem Typ `Car` (`TestCars4`) deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="d09f0-170">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="d09f0-171">Der folgende Code definiert diese beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="d09f0-171">The following code defines these two methods.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-172">Die Methoden erzeugen folgende Ausgabe, die den Ergebnissen des ersten Beispiels in diesem Thema entspricht.</span><span class="sxs-lookup"><span data-stu-id="d09f0-172">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
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
  
 <span data-ttu-id="d09f0-173">Der folgende Code veranschaulicht das vollständige Projekt und dessen Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d09f0-173">The following code shows the complete project and its output.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d09f0-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d09f0-174">See also</span></span>

- [<span data-ttu-id="d09f0-175">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d09f0-175">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d09f0-176">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="d09f0-176">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="d09f0-177">Versionsverwaltung mit den Schlüsselwörtern "override" und "new"</span><span class="sxs-lookup"><span data-stu-id="d09f0-177">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="d09f0-178">base</span><span class="sxs-lookup"><span data-stu-id="d09f0-178">base</span></span>](../../language-reference/keywords/base.md)
- [<span data-ttu-id="d09f0-179">abstract</span><span class="sxs-lookup"><span data-stu-id="d09f0-179">abstract</span></span>](../../language-reference/keywords/abstract.md)
