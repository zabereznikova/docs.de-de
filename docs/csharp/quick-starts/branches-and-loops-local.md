---
title: Schnellstart - Verzweigungen und lops - C#-Handbuch
description: "In diesem Schnellstart zu Verzweigungen und Schleifen schreiben Sie C#-Code aus, um die Sprachsyntax untersuchen, die bedingte Verzweigungen und Schleifen wiederholte Ausführen von Anweisungen unterstützt."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a>Verzweigungen und Schleifen

Dieser Schnellstart erfahren Sie, wie Sie Code schreiben, die Variablen untersucht und ändert den Ausführungspfad, der basierend auf diese Variablen. C#-Code schreiben und die Ergebnisse der kompilieren und Ausführen angezeigt. Der Schnellstart enthält eine Reihe von Lektionen, in denen untersuchen, Verzweigungen und Schleifenkonstrukte in C# geschrieben. In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.

Dieser Schnellstart erwartet, dass Sie einen Computer verfügen, den Sie für die Entwicklung verwenden können. Das Thema .NET [Einstieg in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten der lokalen Entwicklungsumgebung auf Mac, PC oder Linux.

## <a name="make-decisions-using-the-if-statement"></a>Treffen von Entscheidungen mithilfe der `if` Anweisung

Erstellen Sie ein Verzeichnis mit dem Namen **Verzweigungen Schnellstart**. Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console -n BranchesAndLoops -o .` aus. Dieser Befehl erstellt eine neue Konsolenanwendung von .NET Core im aktuellen Verzeichnis. 

Open **"Program.cs"** in Ihrem bevorzugten Editor, und Ersetzen Sie die Zeile `Console.Writeline("Hello World!");` durch den folgenden Code:

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

Versuchen Sie diesen Code durch Eingabe `dotnet run` in der Ihre Konsolenfenster. Sie sollten der Nachricht finden Sie unter "die Antwort ist größer als 10". in der Konsole gedruckt.

Ändern Sie die Deklaration von `b` so, dass die Summe kleiner als 10 ist: 

```csharp
int b = 3;
```

Typ `dotnet run` erneut aus. Da die Antwort kleiner als 10 ist, wird nichts ausgegeben. Die von Ihnen getestete **Bedingung** ist falsch. Es ist kein Code auszuführen, da Sie lediglich eine der möglichen Verzweigungen für eine `if`-Anweisung geschrieben haben: die true-Verzweigung.

> [!TIP]
> Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben. Der Compiler findet und Fehler zu melden. Sehen Sie die Fehlerausgabe und den Code, der den Fehler generiert hat. Der Compler Fehler können in der Regel das Problem zu ermitteln. 

Dieses erste Beispiel veranschaulicht die Leistungsfähigkeit von `if` und booleschen Typen. Ein *booleschen* ist eine Variable, die einen von zwei Werten haben kann: `true` oder `false`. C# definiert eine Sonderform `bool` für boolesche Variablen. Die `if`-Anweisung überprüft den Wert eines `bool`-Typs. Wenn der Wert `true` lautet, wird die nach `if` folgende Anweisung ausgeführt. Andernfalls wird diese übersprungen. 

Dieser Vorgang zum Überprüfen von Bedingungen und Ausführen von Anweisungen basierend auf diesen Bedingungen ist sehr nützlich.


## <a name="make-if-and-else-work-together"></a>Kombinieren von if- und else-Anweisungen

Um einen anderen Code in den true- und false-Verzweigungen auszuführen, erstellen Sie eine `else`-Verzweigung, die ausgeführt wird, wenn die Bedingung falsch ist. Wiederholen Sie diesen Vorgang. Fügen Sie die letzten beiden Zeilen in den folgenden Code, um Ihre `Main` Methode (Sie müssen bereits die ersten vier):

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

Die Anweisung, die nach dem Schlüsselwort `else` folgt, wird nur ausgeführt, wenn die zu testende Bedingung `false` lautet. Kombinieren von `if` und `else` mit einem booleschen Operator Bedingungen bietet die Leistungsfähigkeit, die Sie beide behandeln müssen eine `true` und ein `false` Bedingung.

> [!IMPORTANT]
> Der Einzug unter den `if`- und `else`-Anweisungen dient zur besseren Lesbarkeit.
> In der Programmiersprache C# werden Einzüge oder Leerräume nicht berücksichtigt. Die Anweisung nach dem Schlüsselwort `if` bzw. `else` wird basierend auf der Bedingung ausgeführt. Alle Beispiele in diesem Schnellstart führen Sie üblicherweise um die Zeilen basierend auf dem Steuerungsfluss des Anweisungen einen Einzug festzulegen.

Da Einzüge nicht relevant sind, müssen Sie mit `{` und `}` angeben, dass Sie mehr als eine Anweisung im Rahmen des bedingt ausgeführten Blocks verwenden möchten. C#-Programmierer verwenden solche geschweifte Klammern in der Regel bei allen `if`- und `else`-Anweisungen. Das folgende Beispiel ist identisch mit dem soeben erstellten. Ändern Sie den Code, der oben genannten entsprechend den folgenden Code:

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> Über den Rest dieses Schnellstarts, enthalten alle Codebeispiele die geschweiften Klammern, die folgenden Methoden akzeptiert.

Sie können etwas kompliziertere Bedingungen testen. Fügen Sie den folgenden Code in Ihrem `Main` Methode nach dem Code, Sie haben bisher geschrieben:

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

Das Zeichen `&&` steht für „and“. Es bedeutet, dass beide Bedingungen „true“ lauten müssen, damit die Anweisung in der true-Verzweigung ausgeführt wird.  Diese Beispiele zeigen außerdem, dass Sie in jeder bedingten Verzweigung mehrere Anweisungen verwenden können, sofern Sie sie mit `{` und `}` umschließen.

Sie können auch `||` zur Darstellung "oder". Fügen Sie den folgenden Code nach dem Sie bisher geschrieben haben:

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

Der erste Schritt ist abgeschlossen. Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode. Dies erleichtert das Arbeiten mit einem neuen Beispiel. Benennen Sie Ihre `Main` -Methode in `ExploreIf` um, und schreiben Sie eine neue `Main`-Methode, die `ExploreIf` aufruft. Anschließend sollte der Code wie folgt aussehen:

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

Kommentieren Sie den Aufruf von `ExploreIf()`. Die Ausgabe werden vorgenommen, die weniger überladen, wenn Sie in diesem Abschnitt arbeiten:

```csharp
//ExploreIf();
```

Die `//` startet eine **Kommentar** in C# geschrieben. Kommentare sind Text, die Sie in Ihrem Quellcode beibehalten, aber nicht als Code ausführen möchten. Der Compiler löst keine ausführbaren Code von den Kommentaren.

## <a name="use-loops-to-repeat-operations"></a>Wiederholen von Vorgängen durch Schleifen

In diesem Abschnitt verwenden Sie **Schleifen** Anweisungen wiederholen. Wiederholen Sie diesen Code in Ihrem `Main` Methode:

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

Die `while` -Anweisung überprüft eine Bedingung und führt die Anweisung oder der Anweisungsblock nach der `while`. Er überprüft wiederholt die Bedingung und diese Anweisungen ausführen, bis die Bedingung "false" ist.

In diesem Beispiel kommt ein weiterer neuer Operator vor. Das `++`-Zeichen nach der `counter`-Variable ist der **increment**-Operator. Der Wert von 1 hinzugefügt `counter` und speichert diesen Wert in der `counter` Variable.

> [!IMPORTANT]
> Stellen Sie sicher, dass die `while` Schleife Bedingung Änderungen auf "false", wenn Sie den Code ausführen. Erstellen Sie anderenfalls eine **Endlosschleife**, durch die das Programm niemals beendet wird. Wird nicht in diesem Beispiel wird veranschaulicht, Schreibberechtigung erzwingen das Programm zu beenden, verwenden **STRG + C** oder auf andere Weise.

Die `while`-Schleife testet die Bedingung, bevor der Code nach `while` ausgeführt wird. Die `do` ... `while`-Schleife führt den Code zuerst aus und überprüft anschließend die Bedingung. Die stimmen während der Schleife in den folgenden Code gezeigt wird:

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

Dies `do` Schleife und die frühere `while` Schleife erzeugen dieselbe Ausgabe.

## <a name="work-with-the-for-loop"></a>Arbeiten mit der for-Schleife

Die **für** Schleife wird üblicherweise in c# verwendet. Versuchen Sie diesen Code in der Main()-Methode aus:

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

Dieser funktioniert auf dieselbe Weise wie die `while`-Schleife und die `do`-Schleife, die Sie bereits verwendet haben. Die `for`-Anweisung besteht aus drei Teilen, die steuern, wie sie ausgeführt wird. 

Der erste Teil ist der **for-Initialisierer**: `for index = 0;` deklariert, dass `index` die Schleifenvariable ist, und legt den Anfangswert auf `0` fest.

Der mittlere Teil ist die **for-Bedingung**: `index < 10` deklariert, dass diese `for`-Schleife ausgeführt wird, solange der Wert des Zählers kleiner als 10 ist.

Der letzte Teil ist der **for-Iterator**: `index++` gibt an, wie die Schleifenvariable geändert wird, nachdem der Block nach der `for`-Anweisung ausgeführt wurde. Hier gibt dieser an, dass `index` bei jeder Blockausführung um 1 erhöht werden soll.

Experimentieren Sie selbst damit. Testen Sie Folgendes:

- Ändern Sie den Initialisierer, um mit einem anderen Wert zu beginnen.
- Ändern Sie die Bedingung, um an einem anderen Wert anzuhalten.

Wenn Sie fertig sind, fahren Sie damit fort, mithilfe der erworbenen Kenntnisse selbst Codes zu schreiben.

## <a name="combine-branches-and-loops"></a>Zusammenführen von Verzweigungen Schleifen

Nachdem Sie nun die `if`-Anweisung und die Schleifenkonstrukte in der Programmiersprache C# kennengelernt haben, versuchen Sie, einen C#-Code zu schreiben, der die Summe aller ganzen Zahlen von 1 bis 20 ermittelt, die durch 3 teilbar sind.  Im Folgenden einige Tipps:

- Der `%`-Operator ermittelt den Restwert einer Divisionsoperation.
- Die `if` -Anweisung können Sie die Bedingung aus, um festzustellen, ob eine Zahl Teilen der Summe sein darf.
- Die `for`-Schleife ermöglicht es, eine Reihe von Schritten für alle Zahlen von 1 bis 20 zu wiederholen.

Probieren Sie es selbst aus. Prüfen Sie dann, wie Sie abgeschnitten haben. Sehen Sie eine Antwort von [den fertigen Code auf GitHub anzeigen](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).

Sie haben die "Verzweigungen und Schleifen" Schnellstart abgeschlossen.

Sie können weiterhin mit der [Arrays und Sammlungen](arrays-and-collections.md) schnellen Einstieg in die Entwicklungsumgebung vorbereiten.

Weitere Informationen zu diesen Begriffen finden Sie unter folgenden Themen:

[if- und else-Anweisung](../language-reference/keywords/if-else.md)   
[while-Anweisung](../language-reference/keywords/while.md)   
[do-Anweisung](../language-reference/keywords/do.md)   
[for-Anweisung](../language-reference/keywords/for.md)   
