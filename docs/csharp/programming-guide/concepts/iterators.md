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
# <a name="iterators-c"></a>Iteratoren (C#)

Ein *Iterator* kann verwendet werden, um Auflistungen wie Listen und Arrays schrittweise durchzugehen.

Eine Iteratormethode oder eine `get`-Zugriffsmethode führt eine benutzerdefinierte Iteration einer Auflistung durch. Eine Iteratormethode verwendet die [yield return](../../language-reference/keywords/yield.md)-Anweisung, um jedes Element einzeln nacheinander zurückzugeben. Wenn eine `yield return`-Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Sie erzeugen einen Iterator aus einem Clientcode, indem Sie eine [foreach](../../language-reference/keywords/foreach-in.md)-Anweisung oder eine LINQ-Abfrage verwenden.

In folgendem Beispiel führt die erste Iteration der `foreach`-Schleife dazu, dass die Ausführung solange in der Iteratormethode `SomeNumbers` fortschreitet, bis die erste `yield return`-Anweisung erreicht wird. Diese Iteration gibt den Wert 3 zurück, und die aktuelle Postion in der Iteratormethode wird beibehalten. In der nächsten Iteration der Schleife wird die Ausführung in der Iteratormethode da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einem `yield return`-Ausdruck. Diese Iteration gibt den Wert 5 zurück, und die aktuelle Postion in der Iteratormethode wird beibehalten. Die Schleife wird beendet, wenn das Ende der Iteratormethode erreicht wird.

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

Der Rückgabetyp einer Iteratormethode oder einer `get`-Zugriffsmethode kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.

Sie verwenden eine `yield break`-Anweisung, um die Iteration zu beenden.

> [!NOTE]
> Verwenden Sie in allen Beispielen dieses Themas, außer Einfacher Iterator, die Direktiven [using](../../language-reference/keywords/using-directive.md) für die Namespaces `System.Collections` und `System.Collections.Generic`.

## <a name="simple-iterator"></a>Einfacher Iterator

In folgendem Beispiel wird eine `yield return`-Anweisung verwendet, die sich innerhalb einer [for](../../language-reference/keywords/for.md)-Schleife befindet. In der `Main`-Methode erstellt jede Iteration des `foreach`-Anweisungstexts einen Aufruf der Iteratorfunktion, die zur nächsten `yield return`-Anweisung übergeht.

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

## <a name="creating-a-collection-class"></a>Erstellen einer Auflistungsklasse

In folgendem Beispiel implementiert die `DaysOfTheWeek`-Klasse die <xref:System.Collections.IEnumerable>-Schnittstelle, die eine <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode erfordert. Der Compiler ruft die Methode `GetEnumerator` implizit auf, die <xref:System.Collections.IEnumerator> zurückgibt.

Die Methode `GetEnumerator` gibt jede Zeichenfolge einzeln nacheinander mithilfe der Anweisung `yield return` zurück.

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

Im folgenden Beispiel wird eine `Zoo`-Klasse erstellt, die eine Auflistung von Tieren enthält.

Die Anweisung `foreach`, die auf die Instanz der Klasse verweist (`theZoo`), ruft die Methode `GetEnumerator` implizit auf. Die Anweisung `foreach`, die auf die Eigenschaften `Birds` und `Mammals` verweist, verwenden die Iteratormethode `AnimalsForType`.

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

## <a name="using-iterators-with-a-generic-list"></a>Verwenden von Iteratoren mit einer generischen Liste

In folgendem Beispiel implementiert die generische Klasse <xref:System.Collections.Generic.Stack%601> die generische Schnittstelle <xref:System.Collections.Generic.IEnumerable%601>. Die Methode <xref:System.Collections.Generic.Stack%601.Push%2A> weist Werte an Arrays des Typs `T` zu. Die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode gibt die Arraywerte mit der `yield return`-Anweisung zurück.

Zusätzlich zur generischen Methode <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> muss auch die nicht generische Methode <xref:System.Collections.IEnumerable.GetEnumerator%2A> implementiert werden. Dies liegt daran, dass <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Collections.IEnumerable> erbt. Die nicht generische Implementierung verzögert die generische Implementierung.

In diesem Beispiel werden benannte Iteratoren verwendet, um verschiedene Arten der Iteration in der selben Datenauflistung zu unterstützen. Diese benannten Iteratoren sind die Eigenschaften `TopToBottom` und `BottomToTop` und die Methode `TopN`.

Die Eigenschaft `BottomToTop` verwendet einen Iterator in einer `get`-Zugriffsmethode.

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

## <a name="syntax-information"></a>Syntaxinformationen

Ein Iterator kann als Methode oder als `get`-Zugriffsmethode vorkommen. Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Finalizer vorkommen.

Es muss eine implizite Konvertierung vom Typ des Ausdrucks in der `yield return`-Anweisung in das Typargument für das vom Iterator zurückgegebene `IEnumerable<T>` vorhanden sein.

In C# kann eine Iteratormethode nicht die Parameter `in`, `ref` oder `out` aufweisen.

In C# ist `yield` kein reserviertes Wort, und es hat nur besondere Bedeutung, wenn es vor den Schlüsselwörtern `return` und `break` verwendet wird.

## <a name="technical-implementation"></a>Technische Implementierung

Auch wenn Sie einen Iterator als Methode schreiben, führt der Compiler für diesen eine Translation in eine geschachtelte Klasse durch, die tatsächlich ein Zustandsautomat ist. Diese Klasse überwacht die Position des Iterators solange, wie die `foreach`-Schleife im Clientcode weiter ausgeführt wird.

Wenn Sie sehen möchten, was der Compiler macht, können Sie das Tool Ildasm.exe verwenden, um den Intermediate Language-Code von Microsoft anzuzeigen, der für eine Iteratormethode generiert wird.

Wenn Sie einen Iterator für eine [Klasse](../../language-reference/keywords/class.md) oder [Struktur](../../language-reference/builtin-types/struct.md) erstellen, müssen Sie die gesamte <xref:System.Collections.IEnumerator>-Schnittstelle implementieren. Wenn der Compiler einer Iterator erkennt, generiert er automatisch die Methoden `Current`, `MoveNext` und `Dispose` der <xref:System.Collections.IEnumerator>- und <xref:System.Collections.Generic.IEnumerator%601>-Schnittstelle.

In jeder aufeinanderfolgenden Iteration der `foreach`-Schleife (oder im direkten Aufruf von `IEnumerator.MoveNext`) setzt der nächste Iteratorcodetext den Prozess nach der letzten `yield return`-Anweisung fort. Er springt dann zur nächsten `yield return`-Anweisung weiter, bis das Ende des Iteratortexts erreicht ist, oder bis er auf eine `yield break`-Anweisung trifft.

Iteratoren unterstützen die <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>-Methode nicht. Wenn der Prozess erneut von Anfang an durchlaufen werden soll, müssen Sie einen neuen Iterator erstellen. Durch das Aufrufen von <xref:System.Collections.IEnumerator.Reset%2A> für den von einer Iteratormethode zurückgegebenen Iterator wird <xref:System.NotSupportedException> ausgelöst.

Weitere Informationen finden Sie unter [C#-Programmiersprachenspezifikation](~/_csharplang/spec/classes.md#iterators).

## <a name="use-of-iterators"></a>Verwendung von Iteratoren

Mit Iteratoren können Sie die Einfachheit einer `foreach`-Schleife beibehalten, wenn Sie komplexen Code verwenden müssen, um eine Listensequenz aufzufüllen. Das kann für Folgende Aktionen nützlich sein:

- Das Modifizieren der Listensequenz nach der ersten Iteration einer `foreach`-Schleife.

- Das Vermeiden des kompletten Ladens einer großen Liste vor der ersten Iteration einer `foreach`-Schleife. Ein Beispiel dafür ist das ausgelagerte Abrufen, um einen Batch von Tabellenzeilen zu laden. Ein anderes Beispiel ist die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>-Methode, die Iteratoren in .NET implementiert.

- Das Einschließen des Erstellens der Liste im Iterator. In der Iteratormethode können Sie die Liste erstellen und anschließend jedes Ergebnis in eine Schleife liefern.

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [foreach, in](../../language-reference/keywords/foreach-in.md)
- [yield](../../language-reference/keywords/yield.md)
- [Verwenden von foreach mit Arrays](../arrays/using-foreach-with-arrays.md)
- [Generics](../generics/index.md)
