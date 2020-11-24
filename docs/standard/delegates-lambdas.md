---
title: Delegaten und Lambdas
description: Erfahren Sie, wie Delegaten, die einen Typ definieren, der eine bestimmte Methodensignatur angibt, direkt aufgerufen oder erst an eine andere Methode übergeben und dann aufgerufen werden können.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 9be4fcdc29eac433dc7416578acbc664ac2e431c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821683"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="37316-103">Delegaten und Lambdas</span><span class="sxs-lookup"><span data-stu-id="37316-103">Delegates and lambdas</span></span>

<span data-ttu-id="37316-104">Delegaten definieren einen Typ, der eine bestimmte Methodensignatur angibt.</span><span class="sxs-lookup"><span data-stu-id="37316-104">Delegates define a type that specifies a particular method signature.</span></span> <span data-ttu-id="37316-105">Eine Methode (statische Methode oder Instanzmethode), die dieser Signatur entspricht, kann einer Variablen dieses Typs zugewiesen werden. Anschließend kann sie (mit den entsprechenden Argumenten) direkt aufgerufen oder selbst als Argument an eine andere Methode übergeben und dann aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="37316-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="37316-106">Das folgende Beispiel veranschaulicht die Verwendung von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="37316-106">The following example demonstrates delegate use.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* <span data-ttu-id="37316-107">In Zeile `public delegate string Reverse(string s);` wird ein Delegattyp mit einer bestimmten Signatur erstellt – in diesem Fall eine Methode, die einen Zeichenfolgenparameter akzeptiert und dann einen Zeichenfolgenparameter zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="37316-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="37316-108">Die Methode `static string ReverseString(string s)`, die über die gleiche Signatur wie der definierte Delegattyp verfügt, implementiert den Delegaten.</span><span class="sxs-lookup"><span data-stu-id="37316-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="37316-109">Die Zeile `Reverse rev = ReverseString;` zeigt, dass Sie eine Methode einer Variable des entsprechenden Delegattyps zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="37316-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="37316-110">Die Zeile `Console.WriteLine(rev("a string"));` zeigt, wie eine Variable eines Delegattyps benutzt wird, um den Delegaten aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="37316-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="37316-111">Um den Entwicklungsprozess zu optimieren, enthält .NET eine Reihe von Delegattypen, die Programmierer verwenden können, damit sie keine neuen Typen erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="37316-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="37316-112">Diese Typen lauten `Func<>`, `Action<>` und `Predicate<>`. Sie können verwendet werden, ohne dass neue Delegattypen definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="37316-112">These types are `Func<>`, `Action<>` and `Predicate<>`, and they can be used without having to define new delegate types.</span></span> <span data-ttu-id="37316-113">Es gibt einige Unterschiede zwischen den drei Typen, und diese betreffen ihren jeweiligen Verwendungszweck:</span><span class="sxs-lookup"><span data-stu-id="37316-113">There are some differences between the three types that have to do with the way they were intended to be used:</span></span>

* <span data-ttu-id="37316-114">`Action<>` wird verwendet, wenn eine Aktion mithilfe der Argumente des Delegaten ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="37316-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span> <span data-ttu-id="37316-115">Die von dem Typ gekapselte Methode gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="37316-115">The method it encapsulates does not return a value.</span></span>
* <span data-ttu-id="37316-116">`Func<>` wird üblicherweise verwendet, wenn eine Transformation ausgeführt werden muss, Sie also die Argumente des Delegaten in ein anderes Ergebnis transformieren müssen.</span><span class="sxs-lookup"><span data-stu-id="37316-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="37316-117">Projektionen sind ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="37316-117">Projections are a good example.</span></span> <span data-ttu-id="37316-118">Die von dem Typ gekapselte Methode gibt einen angegebenen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="37316-118">The method it encapsulates returns a specified value.</span></span>
* <span data-ttu-id="37316-119">`Predicate<>` wird verwendet, wenn Sie ermitteln müssen, ob das Argument die Bedingung des Delegaten erfüllt.</span><span class="sxs-lookup"><span data-stu-id="37316-119">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="37316-120">Sie können auch die Schreibweise `Func<T, bool>` verwenden. In diesem Fall gibt die Methode einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="37316-120">It can also be written as a `Func<T, bool>`, which means the method returns a boolean value.</span></span>

<span data-ttu-id="37316-121">Wir schreiben jetzt das obige Beispiel neu, indem wir den `Func<>`-Delegaten anstelle eines benutzerdefinierten Typs verwenden.</span><span class="sxs-lookup"><span data-stu-id="37316-121">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="37316-122">Das Programm wird weiterhin genau gleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37316-122">The program will continue running exactly the same.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

<span data-ttu-id="37316-123">In diesem einfachen Beispiel erscheint es überflüssig, eine Methode außerhalb der `Main`-Methode zu definieren.</span><span class="sxs-lookup"><span data-stu-id="37316-123">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="37316-124">In .NET Framework 2,0 wurde das Konzept der *anonymen Delegaten* eingeführt, mit denen Sie „Inline“-Delegaten erstellen können, ohne einen zusätzlichen Typ oder eine zusätzliche Methode angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="37316-124">.NET Framework 2.0 introduced the concept of *anonymous delegates*, which let you create "inline" delegates without having to specify any additional type or method.</span></span>

<span data-ttu-id="37316-125">Im folgenden Beispiel filtert ein anonymer Delegat eine Liste nach geraden Zahlen und gibt sie dann an die Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="37316-125">In the following example, an anonymous delegate filters a list to just the even numbers and then prints them to the console.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="37316-126">Wie Sie sehen, besteht der Haupttext des Delegaten einfach nur aus einer Reihe von Ausdrücken, wie bei jedem anderen Delegaten auch.</span><span class="sxs-lookup"><span data-stu-id="37316-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="37316-127">Anstatt aber eine separate Definition zu erstellen, haben wir ihn _ad hoc_ in den Aufruf der Methode <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> eingeführt.</span><span class="sxs-lookup"><span data-stu-id="37316-127">But instead of it being a separate definition, we've introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="37316-128">Selbst bei dieser Vorgehensweise bleibt immer noch zu viel Code übrig, den wir nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="37316-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="37316-129">Hier kommen *Lambdaausdrücke* ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="37316-129">This is where *lambda expressions* come into play.</span></span> <span data-ttu-id="37316-130">Lambdaausdrücke (sogenannte Lambdas) wurden in C# 3.0 eingeführt und stellen einen der wichtigsten Bausteine von LINQ (Language Integrated Query) dar.</span><span class="sxs-lookup"><span data-stu-id="37316-130">Lambda expressions, or just "lambdas" for short, were introduced in C# 3.0 as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="37316-131">Sie sind einfach eine praktischere Syntax für die Verwendung von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="37316-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="37316-132">Sie deklarieren eine Signatur und einen Methodentext, besitzen aber keine eigene formale Identität, sofern sie nicht einem Delegaten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="37316-132">They declare a signature and a method body, but don't have a formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="37316-133">Im Gegensatz zu Delegaten können sie direkt als rechte Seite der Ereignisregistrierung oder in verschiedenen LINQ-Klauseln und -Methoden zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="37316-133">Unlike delegates, they can be directly assigned as the right-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="37316-134">Da ein Lambdaausdruck einfach nur eine weitere Möglichkeit ist, einen Delegaten anzugeben, können wir das obige Beispiel neu schreiben und einen Lambdaausdruck anstelle eines anonymen Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="37316-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="37316-135">Im vorherigen Beispiel wird der Lambdaausdruck `i => i % 2 == 0` verwendet.</span><span class="sxs-lookup"><span data-stu-id="37316-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="37316-136">Wie bereits erläutert, handelt es sich einfach um eine praktischere Syntax für die Verwendung von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="37316-136">Again, it is just a convenient syntax for using delegates.</span></span> <span data-ttu-id="37316-137">Die Ausführung des Codes erfolgt auf die gleiche Weise wie für anonyme Delegaten.</span><span class="sxs-lookup"><span data-stu-id="37316-137">What happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="37316-138">Noch einmal: Lambdas sind einfach Delegaten. Das bedeutet, dass sie problemlos als Ereignishandler verwendet werden können, wie im folgenden Codeausschnitt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="37316-138">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

<span data-ttu-id="37316-139">Der `+=`-Operator in diesem Kontext wird zum Abonnieren eines [Ereignisses](../csharp/language-reference/keywords/event.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="37316-139">The `+=` operator in this context is used to subscribe to an [event](../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="37316-140">Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="37316-140">For more information, see [How to subscribe to and unsubscribe from events](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="37316-141">Weitere Informationen und Ressourcen</span><span class="sxs-lookup"><span data-stu-id="37316-141">Further reading and resources</span></span>

* [<span data-ttu-id="37316-142">Delegaten</span><span class="sxs-lookup"><span data-stu-id="37316-142">Delegates</span></span>](../csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="37316-143">Anonyme Funktionen</span><span class="sxs-lookup"><span data-stu-id="37316-143">Anonymous Functions</span></span>](../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="37316-144">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="37316-144">Lambda expressions</span></span>](../csharp/language-reference/operators/lambda-expressions.md)
