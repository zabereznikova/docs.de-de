---
title: Schnellstart - Zahlen in c# - C#-Handbuch
description: Erlernen von c# durch das Durchsuchen von numerischen Typen, deren Eigenschaften und Methoden.
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a>Zahlen in C#-Schnellstart #

Dieser Schnellstart erfahren Sie, über die Number-Typen in c# interaktiv. Schreiben Sie kleine Mengen von Code, und Sie kompilieren und Ausführen dieses Codes. Der Schnellstart enthält eine Reihe von Lektionen, in denen Zahlen und mathematische Operationen in c# zu untersuchen. In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.

Dieser Schnellstart erwartet, dass Sie einen Computer verfügen, den Sie für die Entwicklung verwenden können. Das Thema .NET [Einstieg in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten der lokalen Entwicklungsumgebung auf Mac, PC oder Linux.

## <a name="explore-integer-math"></a>Erkunden von arithmetischen Operationen mit ganzen Zahlen

Erstellen Sie ein Verzeichnis mit dem Namen **Zahlen Schnellstart**. Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console -n NumbersInCSharp -o .` aus.

Open **"Program.cs"** in Ihrem bevorzugten Editor, und Ersetzen Sie die Zeile `Console.Writeline("Hello World!");` durch Folgendes:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

Führen Sie diesen Code durch Eingabe `dotnet run` in das Befehlsfenster. 

Sie haben soeben eine der grundlegenden arithmetischen Operationen mit ganzen Zahlen kennengelernt. Der `int`-Typ steht für **integer**, d.h. eine positive oder negative ganze Zahl. Sie verwenden zum Addieren das `+`-Symbol. Zu den anderen häufig verwendeten arithmetischen Operationen für ganze Zahlen zählen Folgende:

- `-` zur Subtraktion
- `*` zur Multiplikation
- `/` zur Division

Erkunden Sie zunächst die anderen Operationen. Fügen Sie nach der Zeile, die den Wert der schreibt diese Zeilen `c`:

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

Führen Sie diesen Code durch Eingabe `dotnet run` in das Befehlsfenster. 
    
Wenn Sie möchten, können Sie auch experimentieren, indem Sie mehrere arithmetische Operationen in der gleichen Zeile ausführen. Wiederholen Sie den `c = a + b - 12 * 17;` beispielsweise. Das Mischen von Variablen und Konstanten Zahlen ist zulässig.

> [!TIP]
> Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben. Der **Compiler** findet diese Fehler und meldet diese. Wenn die Ausgabe Fehlermeldungen enthält, sehen Sie sich den Beispielcode und den Code in das Fenster zu sehen, zu beheben.
> Durch diese Übung lernen Sie die Struktur eines C#-Codes kennen.     

Der erste Schritt ist abgeschlossen. Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode. Dies erleichtert das Arbeiten mit einem neuen Beispiel. Benennen Sie Ihre `Main` -Methode in `WorkingWithIntegers` um, und schreiben Sie eine neue `Main`-Methode, die `WorkingWithIntegers` aufruft. Anschließend sollte der Code wie folgt aussehen:

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
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
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

Kommentieren Sie den Aufruf von `WorkingWithIntegers()`. Die Ausgabe werden vorgenommen, die weniger überladen, wenn Sie in diesem Abschnitt arbeiten:

```csharp
//WorkingWithIntegers();
```

Die `//` startet eine **Kommentar** in C# geschrieben. Kommentare sind Text, die Sie in Ihrem Quellcode beibehalten, aber nicht als Code ausführen möchten. Der Compiler löst keine ausführbaren Code von den Kommentaren.

Die Programmiersprache C# definiert anhand von Regeln, die Sie aus der Mathematik kennen, die Rangfolge verschiedener arithmetischer Operationen.
Multiplikation und Division haben gegenüber der Addition und Subtraktion Vorrang.
Prüfen Sie, indem Sie den folgenden Code Hinzufügen Ihrer `Main` -Methode und Execuing `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

Die Ausgabe zeigt, dass vor der Addition die Multiplikation ausgeführt wurde.

Eine andere Reihenfolge des Vorgangs können Sie erzwingen, durch Hinzufügen von Klammern um den Vorgang, oder Vorgänge, die gewünschten zuerst ausgeführt. Fügen Sie die folgenden Zeilen hinzu, und führen Sie erneut aus:

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

Machen Sie sich damit vertraut, indem Sie viele verschiedene Operationen kombinieren. Fügen Sie etwa die folgenden Zeilen am unteren Rand der `Main` Methode. Wiederholen Sie den `dotnet run` erneut aus.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

Vielleicht haben Sie bereits ein interessantes Verhalten bei den ganzen Zahlen bemerkt. Ganzzahldivision immer erzeugt ein Ganzzahlergebnis, selbst wenn Sie das Ergebnis ein Teils Dezimalstellen oder Bruchzahlen enthalten erwarten würden.

Wenn Sie dieses Verhalten gesehen haben, wiederholen Sie den folgenden Code am Ende Ihrer `Main` Methode:

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

Typ `dotnet run` erneut aus, um die Ergebnisse anzuzeigen.

Bevor Sie fortfahren, werfen wir den Code, den Sie in diesem Abschnitt selbst geschrieben haben, und fügen Sie ihn in eine neue Methode. Diese neue Methode aufzurufen `OrderPrecedence`.
Sie sollte etwa wie folgt zum Schluss:

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
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
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

            d = (a  + b) * c;
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
Erhalten Sie die **Rest** mithilfe der **modulo** -Operator, der `%` Zeichen. Wiederholen Sie den folgenden Code in Ihrem `Main` Methode:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

Der integer-C#-Typ unterscheidet sich noch in einem weiteren Punkt von einer mathematischen ganzen Zahl: Der `int`-Typ ist mit minimalen und maximalen Grenzwerten versehen. Fügen Sie diesen Code auf Ihre `Main` Methode, um diese Grenzen finden Sie unter:
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

Wenn bei einer Berechnung ein Wert herauskommt, der diese Grenzwerte überschreitet, liegt eine **Unterlauf-** oder **Überlaufbedingung** vor. Die Antwort gibt dann den Bereich der Grenzwerte an. Fügen Sie diese zwei Zeilen auf Ihre `Main` Methode, um ein Beispiel finden Sie unter:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
Beachten Sie, dass die Antwort sehr nah an der minimalen (negativen) ganzen Zahl liegt. Sie entspricht `min + 2`. Die Additionsoperation hat die zulässigen Werte für ganze Zahlen **überlaufen**.
Die Antwort enthält eine sehr große negative Zahl, da ein Überlauf den größtmöglichen ganzzahligen Wert bis zum kleinstmöglichen Wert umschließt.

Wenn der `int`-Typ nicht Ihren Anforderungen entspricht, so gibt es verschiedene numerische Typen mit anderen Grenzwerten und Genauigkeitsgraden, die Sie verwenden können. Werfen wir im Folgenden einmal einen Blick auf diese.

Fahren wir noch einmal: des Codes, den Sie in diesem Abschnitt in eine separate Methode geschrieben haben. Nennen Sie es `TestLimits`. 

## <a name="work-with-the-double-type"></a>Arbeiten mit dem Double-Typ

Der numerische Typ `double` stellt eine Gleitkommazahl mit doppelter Genauigkeit dar. Falls Ihnen diese Benennungen nichts sagen, beachten Sie die folgenden Erläuterungen: Ein **Gleitkomma** Anzahl eignet sich zur Darstellung von nicht ganzzahligen Ziffern, die möglicherweise sehr große oder kleine Wert ohne Vorzeichen. **Doppelte Genauigkeit** bedeutet, dass diese Zahlen mit einer höheren Genauigkeit gespeichert werden als mit **einfacher Genauigkeit**. Bei modernen Computern werden häufiger Zahlen mit doppelter Genauigkeit verwendet statt mit einfacher Genauigkeit.
Sehen wir uns dies einmal genauer an. Fügen Sie den folgenden Code hinzu, und anzuzeigen Sie das Ergebnis:

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

Beachten Sie, dass die Antwort die Dezimalzahl des Quotienten enthält. Testen Sie einen etwas komplizierteren Ausdruck mit Werten vom Typ „double“:

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

Der Bereich eines Werts vom Typ „double“ ist weitaus größer als bei ganzzahligen Werten. Wiederholen Sie den folgenden Code unter Sie bisher geschrieben haben:

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

Diese Werte werden in der wissenschaftlichen Schreibweise ausgegeben. Die Anzahl auf der linken Seite des der `E` ist die Mantisse. Die Zahl rechts ist der Exponent als Potenz von 10. 

Wie bei Dezimalzahlen in der Mathematik können double-Werte in C# Rundungsfehler aufweisen. Testen Sie den folgenden Code:

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

Denken Sie daran, dass `0.3` nicht exakt `1/3` entspricht.

***Übung***

Testen Sie für den `double`-Typ andere Berechnungen mit großen und kleinen Zahlen sowie mit Multiplikation und Division.  Testen Sie kompliziertere Berechnungen.

Nachdem Sie einige Zeit mit der Aufforderung gearbeitet haben, nehmen Sie den Code, den Sie selbst geschrieben haben, und fügen Sie ihn in eine neue Methode. Nennen Sie diese neue Methode `WorkWithDoubles`.

## <a name="work-with-fixed-point-types"></a>Arbeiten mit Festkommatypen

Sie haben die grundlegenden numerischen Typen in C# – „integer“ und „double“ – kennengelernt.  Es gibt einen weiteren Typ, den Sie kennen sollten: den `decimal`-Typ. Die `decimal` Typ hat einen kleineren Bereich aber größere Genauigkeit als `double`. Die Benennung **Festkomma** bedeutet, dass die Position des Dezimalkommas (hier Dezimalpunkts bzw. Binärpunkts) unveränderlich ist. Sehen wir uns das einmal genauer an:

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

Nachdem Sie nun die verschiedenen numerischen Typen kennengelernt haben, schreiben Sie einen Code, der den Flächeninhalt eines Kreises mit einem Radius von 2,5 Zoll berechnet. Denken Sie daran, dass der Flächeninhalt eines Kreises durch das Quadrat des Radius multipliziert mit Pi gebildet wird. Einen Hinweis: c# enthält eine Konstante PI, <xref:System.Math.PI?displayProperty=nameWithType> , die Sie für diesen Wert verwenden können. 

Sehen Sie sich Ihre Antwort von [Betrachtung der fertig gestellten Beispiel-Codes auf GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)

Wenn Sie möchten, versuchen Sie es von einigen anderen Formeln. 

Sie haben die "Zahlen in c#" Schnellstart abgeschlossen. Sie können weiterhin mit der [Verzweigungen und Schleifen](branches-and-loops-local.md) schnellen Einstieg in die Entwicklungsumgebung vorbereiten.

Weitere Informationen zu Zahlen in C# finden Sie auch unter folgenden Themen:

[Tabelle ganzzahliger Typen](../language-reference/keywords/integral-types-table.md)   
[Tabelle für Gleitkommatypen](../language-reference/keywords/floating-point-types-table.md)   
[Tabelle integrierter Typen](../language-reference/keywords/built-in-types-table.md)   
[Tabelle für implizite numerische Konvertierungen](../language-reference/keywords/implicit-numeric-conversions-table.md)   
[Tabelle für explizite numerische Konvertierungen](../language-reference/keywords/explicit-numeric-conversions-table.md)

