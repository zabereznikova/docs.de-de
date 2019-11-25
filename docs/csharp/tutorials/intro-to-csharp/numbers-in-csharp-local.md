---
title: Zahlen in C# – Einführung in das C#-Tutorial
description: Machen Sie sich mit C# vertraut, indem Sie numerische Typen, ihre Eigenschaften und Methoden erkunden.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: a06bc57e5c979b62e19407747cb2c8a2447ca114
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739138"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a>Bearbeiten von Ganzzahlen und Gleitkommazahlen in C\#

Dieses interaktive Tutorial erläutert die numerischen Typen in C#. Sie schreiben einen Teil des Codes, kompilieren diesen und führen ihn aus. Das Tutorial enthält eine Reihe von Lektionen, in denen Zahlen und mathematische Vorgänge in C# untersucht werden. In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.

Für dieses Tutorial benötigen Sie einen Computer, den Sie für die Entwicklung nutzen können. Im .NET-Tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (Hallo Welt in zehn Minuten) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter Windows, Linux oder macOS. Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie im Artikel [Einführung in Entwicklungstools](local-environment.md), der Links zu weiteren Ressourcen enthält.

## <a name="explore-integer-math"></a>Erkunden von arithmetischen Operationen mit ganzen Zahlen

Erstellen Sie ein Verzeichnis mit dem Namen *numbers-quickstart*. Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie den folgenden Befehl aus:

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

Öffnen Sie *Program.cs* in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch Folgendes:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

Führen Sie diesen Code aus, indem Sie `dotnet run` in Ihr Befehlsfenster eingeben.

Sie haben soeben eine der grundlegenden arithmetischen Operationen mit ganzen Zahlen kennengelernt. Der `int`-Typ steht für **integer**, d. h. eine Null oder eine positive oder negative ganze Zahl. Sie verwenden zum Addieren das `+`-Symbol. Zu den anderen häufig verwendeten arithmetischen Operationen für ganze Zahlen zählen Folgende:

- `-` zur Subtraktion
- `*` zur Multiplikation
- `/` zur Division

Erkunden Sie zunächst die anderen Operationen. Fügen Sie diese Zeilen nach der Zeile hinzu, die den Wert von `c` schreibt:

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

Führen Sie diesen Code aus, indem Sie `dotnet run` in Ihr Befehlsfenster eingeben.

Wenn Sie möchten, können Sie auch experimentieren, indem Sie mehrere arithmetische Operationen in der gleichen Zeile ausführen. Testen Sie zum Beispiel `c = a + b - 12 * 17;`. Das Kombinieren von Variablen und konstanten Zahlen ist erlaubt.

> [!TIP]
> Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben. Der **Compiler** findet diese Fehler und meldet diese. Sollte die Ausgabe Fehlermeldungen enthalten, sehen Sie sich den Beispielcode und den Code in Ihrem Fenster an, um festzustellen, was behoben werden muss.
> Durch diese Übung lernen Sie die Struktur eines C#-Codes kennen.

Sie haben den ersten Schritt abgeschlossen. Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode. Dies erleichtert das Arbeiten mit einem neuen Beispiel. Benennen Sie Ihre `Main` -Methode in `WorkingWithIntegers` um, und schreiben Sie eine neue `Main`-Methode, die `WorkingWithIntegers` aufruft. Anschließend sollte der Code wie folgt aussehen:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            
            // addition
            int c = a + b;
            Console.WriteLine(c);
            
            // subtraction
            c = a - b;
            Console.WriteLine(c);
            
            // multiplication
            c = a * b;
            Console.WriteLine(c);
            
            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a>Erkunden der Reihenfolge der Operationen

Kommentieren Sie den Aufruf von `WorkingWithIntegers()` aus. Dadurch wird die Ausgabe weniger überladen, wenn Sie in diesem Abschnitt arbeiten:

```csharp
//WorkingWithIntegers();
```

Mit `//` wird ein **Kommentar** in C# begonnen. Kommentare sind Texte, die Sie in Ihrem Quellcode beibehalten, jedoch nicht als Code ausführen möchten. Der Compiler generiert keinen ausführbaren Code über die Kommentare.

Die Programmiersprache C# definiert anhand von Regeln, die Sie aus der Mathematik kennen, die Rangfolge verschiedener arithmetischer Operationen.
Multiplikation und Division haben gegenüber der Addition und Subtraktion Vorrang.
Überprüfen Sie das, indem Sie den folgenden Code Ihrer `Main`-Methode hinzufügen und `dotnet run` ausführen:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

Die Ausgabe zeigt, dass vor der Addition die Multiplikation ausgeführt wurde.

Sie können eine andere Operationsreihenfolge erzwingen, indem Sie die Operation bzw. die Operationen, die zuerst ausgeführt werden soll bzw. sollen, mit Klammern umschließen. Fügen Sie die folgenden Zeilen hinzu, und führen Sie sie aus:

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

Machen Sie sich damit vertraut, indem Sie viele verschiedene Operationen kombinieren. Fügen Sie eine Zeile hinzu, die ungefähr den folgenden Zeilen am Ende Ihrer `Main`-Methode entspricht. Testen Sie erneut `dotnet run`.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

Vielleicht haben Sie bereits ein interessantes Verhalten bei den ganzen Zahlen bemerkt. Bei der Division ganzer Zahlen kommt immer ein ganzzahliges Ergebnis heraus, selbst wenn Sie als Ergebnis einen Dezimal- oder Bruchteil erwarten würden.

Wenn Sie dieses Verhalten noch nicht beobachtet haben, testen Sie den folgenden Code am Ende Ihrer `Main`-Methode:

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

Geben Sie erneut `dotnet run` ein, um die Ergebnisse anzuzeigen.

Bevor Sie fortfahren, kopieren Sie den gesamten Code, den Sie in diesem Abschnitt geschrieben haben, und fügen ihn in eine neue Methode ein. Rufen Sie die neue Methode `OrderPrecedence` auf.
Das Ergebnis sollte ungefähr wie im folgenden Code aussehen:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            
            // addition
            int c = a + b;
            Console.WriteLine(c);
            
            // subtraction
            c = a - b;
            Console.WriteLine(c);
            
            // multiplication
            c = a * b;
            Console.WriteLine(c);
            
            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a>Erkunden der Genauigkeit und Grenzwerte ganzer Zahlen

Im vorherigen Beispiel haben Sie gesehen, dass das Ergebnis bei der Division ganzer Zahlen abgeschnitten wird.
Sie erhalten den Restwert **remainder** mithilfe des **Modulo**-Operators, dem `%`-Zeichen. Testen Sie den folgenden Code in Ihrer `Main`-Methode:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

Der integer-C#-Typ unterscheidet sich noch in einem weiteren Punkt von einer mathematischen ganzen Zahl: Der `int`-Typ ist mit minimalen und maximalen Grenzwerten versehen. Fügen Sie diesen Code zu Ihrer `Main`-Methode hinzu, um die jeweiligen Grenzwerte zu sehen:

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

Wenn bei einer Berechnung ein Wert herauskommt, der diese Grenzwerte überschreitet, liegt eine **Unterlauf-** oder **Überlaufbedingung** vor. Die Antwort gibt dann den Bereich der Grenzwerte an. Fügen Sie die folgenden zwei Zeilen zu Ihrer `Main`-Methode hinzu, um ein Beispiel zu sehen:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

Beachten Sie, dass die Antwort sehr nah an der minimalen (negativen) ganzen Zahl liegt. Sie entspricht `min + 2`.
Die Additionsoperation hat die zulässigen Werte für ganze Zahlen **überlaufen**.
Die Antwort enthält eine sehr große negative Zahl, da ein Überlauf den größtmöglichen ganzzahligen Wert bis zum kleinstmöglichen Wert umschließt.

Wenn der `int`-Typ nicht Ihren Anforderungen entspricht, so gibt es verschiedene numerische Typen mit anderen Grenzwerten und Genauigkeitsgraden, die Sie verwenden können. Werfen wir im Folgenden einmal einen Blick auf diese.

Fügen Sie den Code, den Sie in diesem Abschnitt geschrieben haben, wieder in eine separate Methode ein. Nennen Sie es `TestLimits`.

## <a name="work-with-the-double-type"></a>Arbeiten mit dem Double-Typ

Der numerische Typ `double` stellt eine Gleitkommazahl mit doppelter Genauigkeit dar. Falls Ihnen diese Benennungen nichts sagen, beachten Sie die folgenden Erläuterungen: Eine **Gleitkommazahl** wird verwendet, um sehr große oder sehr kleine Zahlen, die keine ganzen Zahlen sind, darzustellen. **Doppelte Genauigkeit** bedeutet, dass diese Zahlen mit einer höheren Genauigkeit gespeichert werden als mit **einfacher Genauigkeit**. Bei modernen Computern werden häufiger Zahlen mit doppelter Genauigkeit verwendet statt mit einfacher Genauigkeit.
Sehen wir uns dies einmal genauer an. Fügen Sie den folgenden Code hinzu, und zeigen Sie das Ergebnis an:

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

Beachten Sie, dass die Antwort die Dezimalzahl des Quotienten enthält. Testen Sie einen etwas komplizierteren Ausdruck mit Werten vom Typ „double“:

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

Der Bereich eines Werts vom Typ „double“ ist weitaus größer als bei ganzzahligen Werten. Fügen Sie den folgenden Code unter dem Code hinzu, den Sie bereits geschrieben haben:

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

Diese Werte werden in der wissenschaftlichen Schreibweise ausgegeben. Die Zahl links von `E` ist die Mantisse. Die Zahl rechts ist der Exponent als Potenz von 10.

Wie bei Dezimalzahlen in der Mathematik können double-Werte in C# Rundungsfehler aufweisen. Testen Sie den folgenden Code:

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

Denken Sie daran, dass `0.3` nicht exakt `1/3` entspricht.

***Übung***

Testen Sie für den `double`-Typ andere Berechnungen mit großen und kleinen Zahlen sowie mit Multiplikation und Division. Testen Sie kompliziertere Berechnungen.

Nachdem Sie sich nun einige Zeit lang mit der Übung auseinander gesetzt haben, kopieren Sie den von Ihnen geschriebenen Code, und fügen Sie ihn in eine neue Methode ein. Vergeben Sie einen Namen für die neue Methode `WorkWithDoubles`.

## <a name="work-with-fixed-point-types"></a>Arbeiten mit Festkommatypen

Sie haben die grundlegenden numerischen Typen in C# – „integer“ und „double“ – kennengelernt.  Es gibt einen weiteren Typ, den Sie kennen sollten: den `decimal`-Typ. Der `decimal`-Typ weist einen kleineren Bereich als `double` auf, aber eine höhere Genauigkeit. Die Benennung **Festkomma** bedeutet, dass die Position des Dezimalkommas (hier Dezimalpunkts bzw. Binärpunkts) unveränderlich ist. Sehen wir uns das einmal genauer an:

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

Beachten Sie, dass der Bereich kleiner ist als beim `double`-Typ. Sie können sehen, dass die Genauigkeit beim Typ „decimal“ höher ist, wenn Sie den folgenden Code testen:

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

Mit dem Suffix `M` neben einer Zahl geben Sie an, dass eine Konstante den `decimal`-Typ verwenden soll.

Beachten Sie, dass der aus dieser arithmetischen Operation resultierende Wert vom Typ „decimal“ rechts neben dem Dezimalpunkt mehr Ziffern enthält.

***Übung***

Nachdem Sie nun die verschiedenen numerischen Typen kennengelernt haben, schreiben Sie Code, der den Flächeninhalt eines Kreises mit einem Radius von 2,5 cm berechnet. Denken Sie daran, dass der Flächeninhalt eines Kreises durch das Quadrat des Radius multipliziert mit Pi gebildet wird. Hinweis: .NET bietet eine Konstante für Pi (<xref:System.Math.PI?displayProperty=nameWithType>), die Sie für die Berechnung dieses Werts verwenden können.

Sie sollten eine Antwort zwischen 19 und 20 erhalten.
Sie können Ihre Antwort anhand des [fertig gestellten Beispielcodes auf GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106) prüfen.

Wenn Sie möchten, testen Sie andere Formeln.

Sie haben den Schnellstart „Zahlen in C#“ abgeschlossen. Sie können mit dem Schnellstart [Branches und Schleifen](branches-and-loops-local.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.

Weitere Informationen zu Zahlen in C# finden Sie auch unter folgenden Themen:

- [Integrale numerische Typen](../../language-reference/builtin-types/integral-numeric-types.md)
- [Numerische Gleitkommatypen](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [Integrierte numerischer Konvertierungen](../../language-reference/builtin-types/numeric-conversions.md)
