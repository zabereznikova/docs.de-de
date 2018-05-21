---
title: Delegaten und Lambdas
description: Erfahren Sie, wie Delegate einen Typ definieren, der eine bestimmte Methodensignatur angibt, die direkt aufgerufen oder erst an eine andere Methode übergeben und dann aufgerufen werden kann.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: f8184b87fc62f378fe72138733f87de924da60f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="2edaf-103">Delegaten und Lambdas</span><span class="sxs-lookup"><span data-stu-id="2edaf-103">Delegates and lambdas</span></span>

<span data-ttu-id="2edaf-104">Delegaten definieren einen Typ, der eine bestimmte Methodensignatur angibt.</span><span class="sxs-lookup"><span data-stu-id="2edaf-104">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="2edaf-105">Eine Methode (statische Methode oder Instanzmethode), die dieser Signatur entspricht, kann einer Variablen dieses Typs zugewiesen werden. Anschließend kann sie (mit den entsprechenden Argumenten) direkt aufgerufen oder selbst als Argument an eine andere Methode übergeben und dann aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2edaf-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="2edaf-106">Das folgende Beispiel veranschaulicht die Verwendung von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="2edaf-106">The following example demonstrates delegate use.</span></span>

```csharp
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

*   <span data-ttu-id="2edaf-107">In Zeile 4 erstellen wir einen Delegattyp mit einer bestimmten Signatur – in diesem Fall eine Methode, die einen Zeichenfolgenparameter akzeptiert und dann einen Zeichenfolgenparameter zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2edaf-107">On line 4 we create a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
*   <span data-ttu-id="2edaf-108">In Zeile 6 definieren wir die Implementierung des Delegaten, indem wir eine Methode bereitstellen, die exakt die gleiche Signatur aufweist.</span><span class="sxs-lookup"><span data-stu-id="2edaf-108">On line 6, we define the implementation of the delegate by providing a method that has the exact same signature.</span></span>
*   <span data-ttu-id="2edaf-109">In Zeile 13 wird die Methode einem Typ zugewiesen, der dem `Reverse`-Delegaten entspricht.</span><span class="sxs-lookup"><span data-stu-id="2edaf-109">On line 13, the method is assigned to a type that conforms to the `Reverse` delegate.</span></span>
*   <span data-ttu-id="2edaf-110">In Zeile 15 rufen wir schließlich den Delegaten auf, indem wir eine Zeichenfolge übergeben, die umgekehrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2edaf-110">Finally, on line 15 we invoke the delegate passing a string to be reversed.</span></span>

<span data-ttu-id="2edaf-111">Um den Entwicklungsprozess zu optimieren, enthält .NET eine Reihe von Delegattypen, die Programmierer verwenden können, damit sie keine neuen Typen erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="2edaf-112">Dies sind `Func<>`, `Action<>` und `Predicate<>`. Sie können an verschiedenen Stellen in den .NET-APIs verwendet werden, ohne dass neue Delegattypen definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-112">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="2edaf-113">Natürlich gibt es Unterschiede zwischen den drei Typen, wie Sie in ihren Signaturen erkennen können. Hierbei handelt es sich meist um Unterschiede in der Art und Weise der Verwendung dieser Typen:</span><span class="sxs-lookup"><span data-stu-id="2edaf-113">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

*   <span data-ttu-id="2edaf-114">`Action<>` wird verwendet, wenn eine Aktion mithilfe der Argumente des Delegaten ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="2edaf-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span>
*   <span data-ttu-id="2edaf-115">`Func<>` wird üblicherweise verwendet, wenn eine Transformation ausgeführt werden muss, Sie also die Argumente des Delegaten in ein anderes Ergebnis transformieren müssen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-115">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="2edaf-116">Projektionen sind ein gutes Beispiel hierfür.</span><span class="sxs-lookup"><span data-stu-id="2edaf-116">Projections are a prime example of this.</span></span>
*   <span data-ttu-id="2edaf-117">`Predicate<>` wird verwendet, wenn Sie ermitteln müssen, ob das Argument die Bedingung des Delegaten erfüllt.</span><span class="sxs-lookup"><span data-stu-id="2edaf-117">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="2edaf-118">Der Typ kann auch als `Func<T, bool>` geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="2edaf-118">It can also be written as a `Func<T, bool>`.</span></span>

<span data-ttu-id="2edaf-119">Wir schreiben jetzt das obige Beispiel neu, indem wir den `Func<>`-Delegaten anstelle eines benutzerdefinierten Typs verwenden.</span><span class="sxs-lookup"><span data-stu-id="2edaf-119">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="2edaf-120">Das Programm wird weiterhin genau gleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2edaf-120">The program will continue running exactly the same.</span></span>

```csharp
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

<span data-ttu-id="2edaf-121">In diesem einfachen Beispiel erscheint es überflüssig, eine Methode außerhalb der Main()-Methode zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2edaf-121">For this simple example, having a method defined outside of the Main() method seems a bit superfluous.</span></span> <span data-ttu-id="2edaf-122">Aus diesem Grund wurde in .NET Framework 2.0 das Konzept der **anonymen Delegaten** eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2edaf-122">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="2edaf-123">Damit können Sie „Inlinedelegaten“ erstellen, ohne einen weiteren Typ oder eine zusätzliche Methode angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-123">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="2edaf-124">Sie fügen einfach die Definition des Delegaten inline dort ein, wo Sie sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-124">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="2edaf-125">Als Beispiel verwenden wir unseren anonymen Delegaten, um eine Liste mit gerade Zahlen herauszufiltern und diese Zahlen in der Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="2edaf-125">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

```csharp
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
      delegate(int no)
      {
          return (no%2 == 0);
      }
    );

    foreach (var item in result)
    {
        Console.WriteLine(item);
    }
  }
}
```

<span data-ttu-id="2edaf-126">Beachten Sie die markierten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-126">Notice the highlighted lines.</span></span> <span data-ttu-id="2edaf-127">Wie Sie sehen, besteht der Haupttext des Delegaten einfach nur aus einer Reihe von Ausdrücken, wie bei jedem anderen Delegaten auch.</span><span class="sxs-lookup"><span data-stu-id="2edaf-127">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="2edaf-128">Anstatt aber eine separate Definition zu erstellen, haben wir ihn _ad hoc_ in den Aufruf der `FindAll()`-Methode des `List<T>`-Typs eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2edaf-128">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the `FindAll()` method of the `List<T>` type.</span></span>

<span data-ttu-id="2edaf-129">Selbst bei dieser Vorgehensweise bleibt immer noch zu viel Code übrig, den wir nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="2edaf-129">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="2edaf-130">Hier kommen **Lambdaausdrücke** ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="2edaf-130">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="2edaf-131">Lambdaausdrücke (sogenannte Lambdas) wurden zum ersten Mal in C# 3.0 eingeführt und stellen einen der wichtigsten Bausteine von LINQ dar (Language Integrated Query).</span><span class="sxs-lookup"><span data-stu-id="2edaf-131">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="2edaf-132">Sie sind einfach eine praktischere Syntax für die Verwendung von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="2edaf-132">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="2edaf-133">Sie deklarieren eine Signatur und einen Methodentext, besitzen aber keine eigene formale Identität, sofern sie nicht einem Delegaten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2edaf-133">They declare a signature and a method body, but don’t have an formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="2edaf-134">Im Gegensatz zu Delegaten können sie direkt als linke Seite der Ereignisregistrierung oder in verschiedenen LINQ-Klauseln und -Methoden zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2edaf-134">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various Linq clauses and methods.</span></span>

<span data-ttu-id="2edaf-135">Da ein Lambdaausdruck einfach nur eine weitere Möglichkeit ist, einen Delegaten anzugeben, können wir das obige Beispiel neu schreiben und einen Lambdaausdruck anstelle eines anonymen Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2edaf-135">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
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

<span data-ttu-id="2edaf-136">In den markierten Zeilen sehen Sie, wie ein Lambdaausdruck aussieht.</span><span class="sxs-lookup"><span data-stu-id="2edaf-136">If you take a look at the highlighted lines, you can see how a lambda expression looks like.</span></span> <span data-ttu-id="2edaf-137">Das ist einfach eine **sehr** praktische Syntax für die Verwendung von Delegaten. Hinter den Kulissen passiert das Gleiche wie bei anonymen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="2edaf-137">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="2edaf-138">Noch einmal: Lambdas sind einfach Delegaten. Das bedeutet, dass sie problemlos als Ereignishandler verwendet werden können, wie im folgenden Codeausschnitt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2edaf-138">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

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

## <a name="further-reading-and-resources"></a><span data-ttu-id="2edaf-139">Weitere Informationen und Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2edaf-139">Further reading and resources</span></span>

*   [<span data-ttu-id="2edaf-140">Delegaten</span><span class="sxs-lookup"><span data-stu-id="2edaf-140">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
*   [<span data-ttu-id="2edaf-141">Anonyme Funktionen</span><span class="sxs-lookup"><span data-stu-id="2edaf-141">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
*   [<span data-ttu-id="2edaf-142">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2edaf-142">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
