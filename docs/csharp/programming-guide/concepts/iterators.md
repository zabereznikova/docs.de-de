---
title: Durchlaufen von Sammlungen in C#
description: Hier erfahren Sie, wie Sie einen Iterator verwenden, um Sammlungen wie Listen und Arrays schrittweise zu durchlaufen. Iteratoren werden im Clientcode über eine foreach-Anweisung oder eine LINQ-Abfrage verwendet.
ms.date: 08/14/2018
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
ms.openlocfilehash: 310fff68a242812620357517c212ddd5f053775c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104252"
---
# <a name="iterators-c"></a><span data-ttu-id="10334-104">Iteratoren (C#)</span><span class="sxs-lookup"><span data-stu-id="10334-104">Iterators (C#)</span></span>

<span data-ttu-id="10334-105">Ein *Iterator* kann verwendet werden, um Auflistungen wie Listen und Arrays schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="10334-105">An *iterator* can be used to step through collections such as lists and arrays.</span></span>

<span data-ttu-id="10334-106">Eine Iteratormethode oder eine `get`-Zugriffsmethode führt eine benutzerdefinierte Iteration einer Auflistung durch.</span><span class="sxs-lookup"><span data-stu-id="10334-106">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="10334-107">Eine Iteratormethode verwendet die [yield return](../../language-reference/keywords/yield.md)-Anweisung, um jedes Element einzeln nacheinander zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="10334-107">An iterator method uses the [yield return](../../language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="10334-108">Wenn eine `yield return`-Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="10334-108">When a `yield return` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="10334-109">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="10334-109">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="10334-110">Sie erzeugen einen Iterator aus einem Clientcode, indem Sie eine [foreach](../../language-reference/keywords/foreach-in.md)-Anweisung oder eine LINQ-Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="10334-110">You consume an iterator from client code by using a [foreach](../../language-reference/keywords/foreach-in.md) statement or by using a LINQ query.</span></span>

<span data-ttu-id="10334-111">In folgendem Beispiel führt die erste Iteration der `foreach`-Schleife dazu, dass die Ausführung solange in der Iteratormethode `SomeNumbers` fortschreitet, bis die erste `yield return`-Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="10334-111">In the following example, the first iteration of the `foreach` loop causes execution to proceed in the `SomeNumbers` iterator method until the first `yield return` statement is reached.</span></span> <span data-ttu-id="10334-112">Diese Iteration gibt den Wert 3 zurück, und die aktuelle Postion in der Iteratormethode wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="10334-112">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="10334-113">In der nächsten Iteration der Schleife wird die Ausführung in der Iteratormethode da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einem `yield return`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="10334-113">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="10334-114">Diese Iteration gibt den Wert 5 zurück, und die aktuelle Postion in der Iteratormethode wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="10334-114">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="10334-115">Die Schleife wird beendet, wenn das Ende der Iteratormethode erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="10334-115">The loop completes when the end of the iterator method is reached.</span></span>

```csharp
static void Main()
{
    foreach (int number in SomeNumbers())
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 3 5 8
    Console.ReadKey();
}

public static System.Collections.IEnumerable SomeNumbers()
{
    yield return 3;
    yield return 5;
    yield return 8;
}
```

<span data-ttu-id="10334-116">Der Rückgabetyp einer Iteratormethode oder einer `get`-Zugriffsmethode kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.</span><span class="sxs-lookup"><span data-stu-id="10334-116">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="10334-117">Sie verwenden eine `yield break`-Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="10334-117">You can use a `yield break` statement to end the iteration.</span></span>

> [!NOTE]
> <span data-ttu-id="10334-118">Verwenden Sie in allen Beispielen dieses Themas, außer Einfacher Iterator, die Direktiven [using](../../language-reference/keywords/using-directive.md) für die Namespaces `System.Collections` und `System.Collections.Generic`.</span><span class="sxs-lookup"><span data-stu-id="10334-118">For all examples in this topic except the Simple Iterator example, include [using](../../language-reference/keywords/using-directive.md) directives for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>

## <a name="simple-iterator"></a><span data-ttu-id="10334-119">Einfacher Iterator</span><span class="sxs-lookup"><span data-stu-id="10334-119">Simple Iterator</span></span>

<span data-ttu-id="10334-120">In folgendem Beispiel wird eine `yield return`-Anweisung verwendet, die sich innerhalb einer [for](../../language-reference/keywords/for.md)-Schleife befindet.</span><span class="sxs-lookup"><span data-stu-id="10334-120">The following example has a single `yield return` statement that is inside a [for](../../language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="10334-121">In der `Main`-Methode erstellt jede Iteration des `foreach`-Anweisungstexts einen Aufruf der Iteratorfunktion, die zur nächsten `yield return`-Anweisung übergeht.</span><span class="sxs-lookup"><span data-stu-id="10334-121">In `Main`, each iteration of the `foreach` statement body creates a call to the iterator function, which proceeds to the next `yield return` statement.</span></span>

```csharp
static void Main()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 6 8 10 12 14 16 18
    Console.ReadKey();
}

public static System.Collections.Generic.IEnumerable<int>
    EvenSequence(int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (int number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="creating-a-collection-class"></a><span data-ttu-id="10334-122">Erstellen einer Auflistungsklasse</span><span class="sxs-lookup"><span data-stu-id="10334-122">Creating a Collection Class</span></span>

<span data-ttu-id="10334-123">In folgendem Beispiel implementiert die `DaysOfTheWeek`-Klasse die <xref:System.Collections.IEnumerable>-Schnittstelle, die eine <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode erfordert.</span><span class="sxs-lookup"><span data-stu-id="10334-123">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="10334-124">Der Compiler ruft die Methode `GetEnumerator` implizit auf, die <xref:System.Collections.IEnumerator> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="10334-124">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>

<span data-ttu-id="10334-125">Die Methode `GetEnumerator` gibt jede Zeichenfolge einzeln nacheinander mithilfe der Anweisung `yield return` zurück.</span><span class="sxs-lookup"><span data-stu-id="10334-125">The `GetEnumerator` method returns each string one at a time by using the `yield return` statement.</span></span>

```csharp
static void Main()
{
    DaysOfTheWeek days = new DaysOfTheWeek();

    foreach (string day in days)
    {
        Console.Write(day + " ");
    }
    // Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey();
}

public class DaysOfTheWeek : IEnumerable
{
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

    public IEnumerator GetEnumerator()
    {
        for (int index = 0; index < days.Length; index++)
        {
            // Yield each day of the week.
            yield return days[index];
        }
    }
}
```

<span data-ttu-id="10334-126">Im folgenden Beispiel wird eine `Zoo`-Klasse erstellt, die eine Auflistung von Tieren enthält.</span><span class="sxs-lookup"><span data-stu-id="10334-126">The following example creates a `Zoo` class that contains a collection of animals.</span></span>

<span data-ttu-id="10334-127">Die Anweisung `foreach`, die auf die Instanz der Klasse verweist (`theZoo`), ruft die Methode `GetEnumerator` implizit auf.</span><span class="sxs-lookup"><span data-stu-id="10334-127">The `foreach` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="10334-128">Die Anweisung `foreach`, die auf die Eigenschaften `Birds` und `Mammals` verweist, verwenden die Iteratormethode `AnimalsForType`.</span><span class="sxs-lookup"><span data-stu-id="10334-128">The `foreach` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>

```csharp
static void Main()
{
    Zoo theZoo = new Zoo();

    theZoo.AddMammal("Whale");
    theZoo.AddMammal("Rhinoceros");
    theZoo.AddBird("Penguin");
    theZoo.AddBird("Warbler");

    foreach (string name in theZoo)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros Penguin Warbler

    foreach (string name in theZoo.Birds)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Penguin Warbler

    foreach (string name in theZoo.Mammals)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros

    Console.ReadKey();
}

public class Zoo : IEnumerable
{
    // Private members.
    private List<Animal> animals = new List<Animal>();

    // Public methods.
    public void AddMammal(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });
    }

    public void AddBird(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });
    }

    public IEnumerator GetEnumerator()
    {
        foreach (Animal theAnimal in animals)
        {
            yield return theAnimal.Name;
        }
    }

    // Public members.
    public IEnumerable Mammals
    {
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }
    }

    public IEnumerable Birds
    {
        get { return AnimalsForType(Animal.TypeEnum.Bird); }
    }

    // Private methods.
    private IEnumerable AnimalsForType(Animal.TypeEnum type)
    {
        foreach (Animal theAnimal in animals)
        {
            if (theAnimal.Type == type)
            {
                yield return theAnimal.Name;
            }
        }
    }

    // Private class.
    private class Animal
    {
        public enum TypeEnum { Bird, Mammal }

        public string Name { get; set; }
        public TypeEnum Type { get; set; }
    }
}
```

## <a name="using-iterators-with-a-generic-list"></a><span data-ttu-id="10334-129">Verwenden von Iteratoren mit einer generischen Liste</span><span class="sxs-lookup"><span data-stu-id="10334-129">Using Iterators with a Generic List</span></span>

<span data-ttu-id="10334-130">In folgendem Beispiel implementiert die generische Klasse <xref:System.Collections.Generic.Stack%601> die generische Schnittstelle <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="10334-130">In the following example, the <xref:System.Collections.Generic.Stack%601> generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="10334-131">Die Methode <xref:System.Collections.Generic.Stack%601.Push%2A> weist Werte an Arrays des Typs `T` zu.</span><span class="sxs-lookup"><span data-stu-id="10334-131">The <xref:System.Collections.Generic.Stack%601.Push%2A> method assigns values to an array of type `T`.</span></span> <span data-ttu-id="10334-132">Die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode gibt die Arraywerte mit der `yield return`-Anweisung zurück.</span><span class="sxs-lookup"><span data-stu-id="10334-132">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `yield return` statement.</span></span>

<span data-ttu-id="10334-133">Zusätzlich zur generischen Methode <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> muss auch die nicht generische Methode <xref:System.Collections.IEnumerable.GetEnumerator%2A> implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="10334-133">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="10334-134">Dies liegt daran, dass <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Collections.IEnumerable> erbt.</span><span class="sxs-lookup"><span data-stu-id="10334-134">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="10334-135">Die nicht generische Implementierung verzögert die generische Implementierung.</span><span class="sxs-lookup"><span data-stu-id="10334-135">The non-generic implementation defers to the generic implementation.</span></span>

<span data-ttu-id="10334-136">In diesem Beispiel werden benannte Iteratoren verwendet, um verschiedene Arten der Iteration in der selben Datenauflistung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="10334-136">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="10334-137">Diese benannten Iteratoren sind die Eigenschaften `TopToBottom` und `BottomToTop` und die Methode `TopN`.</span><span class="sxs-lookup"><span data-stu-id="10334-137">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>

<span data-ttu-id="10334-138">Die Eigenschaft `BottomToTop` verwendet einen Iterator in einer `get`-Zugriffsmethode.</span><span class="sxs-lookup"><span data-stu-id="10334-138">The `BottomToTop` property uses an iterator in a `get` accessor.</span></span>

```csharp
static void Main()
{
    Stack<int> theStack = new Stack<int>();

    //  Add items to the stack.
    for (int number = 0; number <= 9; number++)
    {
        theStack.Push(number);
    }

    // Retrieve items from the stack.
    // foreach is allowed because theStack implements IEnumerable<int>.
    foreach (int number in theStack)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    // foreach is allowed, because theStack.TopToBottom returns IEnumerable(Of Integer).
    foreach (int number in theStack.TopToBottom)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    foreach (int number in theStack.BottomToTop)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 0 1 2 3 4 5 6 7 8 9

    foreach (int number in theStack.TopN(7))
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3

    Console.ReadKey();
}

public class Stack<T> : IEnumerable<T>
{
    private T[] values = new T[100];
    private int top = 0;

    public void Push(T t)
    {
        values[top] = t;
        top++;
    }
    public T Pop()
    {
        top--;
        return values[top];
    }

    // This method implements the GetEnumerator method. It allows
    // an instance of the class to be used in a foreach statement.
    public IEnumerator<T> GetEnumerator()
    {
        for (int index = top - 1; index >= 0; index--)
        {
            yield return values[index];
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }

    public IEnumerable<T> TopToBottom
    {
        get { return this; }
    }

    public IEnumerable<T> BottomToTop
    {
        get
        {
            for (int index = 0; index <= top - 1; index++)
            {
                yield return values[index];
            }
        }
    }

    public IEnumerable<T> TopN(int itemsFromTop)
    {
        // Return less than itemsFromTop if necessary.
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;

        for (int index = top - 1; index >= startIndex; index--)
        {
            yield return values[index];
        }
    }

}
```

## <a name="syntax-information"></a><span data-ttu-id="10334-139">Syntaxinformationen</span><span class="sxs-lookup"><span data-stu-id="10334-139">Syntax Information</span></span>

<span data-ttu-id="10334-140">Ein Iterator kann als Methode oder als `get`-Zugriffsmethode vorkommen.</span><span class="sxs-lookup"><span data-stu-id="10334-140">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="10334-141">Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Finalizer vorkommen.</span><span class="sxs-lookup"><span data-stu-id="10334-141">An iterator cannot occur in an event, instance constructor, static constructor, or static finalizer.</span></span>

<span data-ttu-id="10334-142">Es muss eine implizite Konvertierung vom Typ des Ausdrucks in der `yield return`-Anweisung in das Typargument für das vom Iterator zurückgegebene `IEnumerable<T>` vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="10334-142">An implicit conversion must exist from the expression type in the `yield return` statement to the type argument for the `IEnumerable<T>` returned by the iterator.</span></span>

<span data-ttu-id="10334-143">In C# kann eine Iteratormethode nicht die Parameter `in`, `ref` oder `out` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="10334-143">In C#, an iterator method cannot have any `in`, `ref`, or `out` parameters.</span></span>

<span data-ttu-id="10334-144">In C# ist `yield` kein reserviertes Wort, und es hat nur besondere Bedeutung, wenn es vor den Schlüsselwörtern `return` und `break` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10334-144">In C#, `yield` is not a reserved word and has special meaning only when it is used before a `return` or `break` keyword.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="10334-145">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="10334-145">Technical Implementation</span></span>

<span data-ttu-id="10334-146">Auch wenn Sie einen Iterator als Methode schreiben, führt der Compiler für diesen eine Translation in eine geschachtelte Klasse durch, die tatsächlich ein Zustandsautomat ist.</span><span class="sxs-lookup"><span data-stu-id="10334-146">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="10334-147">Diese Klasse überwacht die Position des Iterators solange, wie die `foreach`-Schleife im Clientcode weiter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="10334-147">This class keeps track of the position of the iterator as long the `foreach` loop in the client code continues.</span></span>

<span data-ttu-id="10334-148">Wenn Sie sehen möchten, was der Compiler macht, können Sie das Tool Ildasm.exe verwenden, um den Intermediate Language-Code von Microsoft anzuzeigen, der für eine Iteratormethode generiert wird.</span><span class="sxs-lookup"><span data-stu-id="10334-148">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that's generated for an iterator method.</span></span>

<span data-ttu-id="10334-149">Wenn Sie einen Iterator für eine [Klasse](../../language-reference/keywords/class.md) oder [Struktur](../../language-reference/builtin-types/struct.md) erstellen, müssen Sie die gesamte <xref:System.Collections.IEnumerator>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="10334-149">When you create an iterator for a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md), you don't have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="10334-150">Wenn der Compiler einer Iterator erkennt, generiert er automatisch die Methoden `Current`, `MoveNext` und `Dispose` der <xref:System.Collections.IEnumerator>- und <xref:System.Collections.Generic.IEnumerator%601>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="10334-150">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>

<span data-ttu-id="10334-151">In jeder aufeinanderfolgenden Iteration der `foreach`-Schleife (oder im direkten Aufruf von `IEnumerator.MoveNext`) setzt der nächste Iteratorcodetext den Prozess nach der letzten `yield return`-Anweisung fort.</span><span class="sxs-lookup"><span data-stu-id="10334-151">On each successive iteration of the `foreach` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `yield return` statement.</span></span> <span data-ttu-id="10334-152">Er springt dann zur nächsten `yield return`-Anweisung weiter, bis das Ende des Iteratortexts erreicht ist, oder bis er auf eine `yield break`-Anweisung trifft.</span><span class="sxs-lookup"><span data-stu-id="10334-152">It then continues to the next `yield return` statement until the end of the iterator body is reached, or until a `yield break` statement is encountered.</span></span>

<span data-ttu-id="10334-153">Iteratoren unterstützen die <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>-Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="10334-153">Iterators don't support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="10334-154">Wenn der Prozess erneut von Anfang an durchlaufen werden soll, müssen Sie einen neuen Iterator erstellen.</span><span class="sxs-lookup"><span data-stu-id="10334-154">To reiterate from the start, you must obtain a new iterator.</span></span> <span data-ttu-id="10334-155">Durch das Aufrufen von <xref:System.Collections.IEnumerator.Reset%2A> für den von einer Iteratormethode zurückgegebenen Iterator wird <xref:System.NotSupportedException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="10334-155">Calling <xref:System.Collections.IEnumerator.Reset%2A> on the iterator returned by an iterator method throws a <xref:System.NotSupportedException>.</span></span>

<span data-ttu-id="10334-156">Weitere Informationen finden Sie unter [C#-Programmiersprachenspezifikation](~/_csharplang/spec/classes.md#iterators).</span><span class="sxs-lookup"><span data-stu-id="10334-156">For additional information, see the [C# Language Specification](~/_csharplang/spec/classes.md#iterators).</span></span>

## <a name="use-of-iterators"></a><span data-ttu-id="10334-157">Verwendung von Iteratoren</span><span class="sxs-lookup"><span data-stu-id="10334-157">Use of Iterators</span></span>

<span data-ttu-id="10334-158">Mit Iteratoren können Sie die Einfachheit einer `foreach`-Schleife beibehalten, wenn Sie komplexen Code verwenden müssen, um eine Listensequenz aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="10334-158">Iterators enable you to maintain the simplicity of a `foreach` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="10334-159">Das kann für Folgende Aktionen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="10334-159">This can be useful when you want to do the following:</span></span>

- <span data-ttu-id="10334-160">Das Modifizieren der Listensequenz nach der ersten Iteration einer `foreach`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="10334-160">Modify the list sequence after the first `foreach` loop iteration.</span></span>

- <span data-ttu-id="10334-161">Das Vermeiden des kompletten Ladens einer großen Liste vor der ersten Iteration einer `foreach`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="10334-161">Avoid fully loading a large list before the first iteration of a `foreach` loop.</span></span> <span data-ttu-id="10334-162">Ein Beispiel dafür ist das ausgelagerte Abrufen, um einen Batch von Tabellenzeilen zu laden.</span><span class="sxs-lookup"><span data-stu-id="10334-162">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="10334-163">Ein anderes Beispiel ist die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>-Methode, die Iteratoren in .NET implementiert.</span><span class="sxs-lookup"><span data-stu-id="10334-163">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators in .NET.</span></span>

- <span data-ttu-id="10334-164">Das Einschließen des Erstellens der Liste im Iterator.</span><span class="sxs-lookup"><span data-stu-id="10334-164">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="10334-165">In der Iteratormethode können Sie die Liste erstellen und anschließend jedes Ergebnis in eine Schleife liefern.</span><span class="sxs-lookup"><span data-stu-id="10334-165">In the iterator method, you can build the list and then yield each result in a loop.</span></span>

## <a name="see-also"></a><span data-ttu-id="10334-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10334-166">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="10334-167">foreach, in</span><span class="sxs-lookup"><span data-stu-id="10334-167">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="10334-168">yield</span><span class="sxs-lookup"><span data-stu-id="10334-168">yield</span></span>](../../language-reference/keywords/yield.md)
- [<span data-ttu-id="10334-169">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="10334-169">Using foreach with Arrays</span></span>](../arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="10334-170">Generics</span><span class="sxs-lookup"><span data-stu-id="10334-170">Generics</span></span>](../generics/index.md)
