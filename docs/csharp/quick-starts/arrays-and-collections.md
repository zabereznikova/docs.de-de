---
title: 'Schnellstart - Sammlungen: C#-Handbuch'
description: Erlernen von c# durch Untersuchen der listenauflistung in diesem Schnellstart.
keywords: C#-, erste Schritte, Tutorial, Auflistungen, Liste
author: billwagner
ms.author: wiwagn
ms.date: 10/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 51b190fba32186cb4c52ccd773274d9ae22c8efb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="c-quick-start-collections"></a>C#-Schnellstart: Sammlungen #

Dieses Lernprogramm bietet eine Einführung in die C#-Sprache und die Grundlagen der <xref:System.Collections.Generic.List%601> Klasse.

## <a name="a-simple-list-example"></a>Ein Beispiel für eine einfache Liste.

> [!NOTE]
> Wenn Sie aus dem Code starten schrieb [dot.net](https://dot.net/), Sie haben bereits den Code in diesem Abschnitt geschrieben. Springen zu [ändern Listeninhalte](#modify-list-contents).

In dieser Lektion wird davon ausgegangen, die online-Schnellstarts ist abgeschlossen, und installiert haben die [.NET Core SDK](http://dot.net/core) und [Visual Studio Code](https://code.visualstudio.com/). 

Erstellen Sie ein Verzeichnis mit dem Namen **Liste Schnellstart**. Stellen, dass das aktuelle Verzeichnis, und führen `dotnet new console`.

Open **"Program.cs"** in Ihrem bevorzugten Editor, und Ersetzen Sie den vorhandenen Code durch Folgendes:

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

Ersetzen Sie `<name>` durch den Namen Ihres. Speichern Sie **"Program.cs"**. Typ `dotnet run` in Ihrem Konsolenfenster ausprobieren.

Sie haben gerade erstellte eine Liste von Zeichenfolgen, drei Namen dieser Liste hinzugefügt, und die Namen in Großbuchstaben ausgegeben. Sie verwenden Konzepte, die Sie haben gelernt in zuvor Schnellstarts so durchlaufen Sie die Liste.

Der Code zum Anzeigen der Namen nutzt **interpoliert Zeichenfolgen**.  Wenn Sie voranstellen eine `string` mit der `$` Zeichen ist, können Sie C#-Code in der Deklaration Zeichenfolge einbetten. Die tatsächliche Zeichenfolge ersetzt dieses C#-Code mit dem Wert, den er generiert wird. In diesem Beispiel ersetzt die `{name.ToUpper()}` jeder Name konvertiert, Großbuchstaben, da Sie wird aufgerufen, die <xref:System.String.ToUpper%2A> Methode.

Wir untersuchen zu halten.
    
## <a name="modify-list-contents"></a>Ändern der Ordnerinhalt auflisten

Die Auflistung, die Sie erstellt mithilfe der <xref:System.Collections.Generic.List%601> Typ. Dieser Typ speichert Elementsequenzen. Sie geben den Typ der Elemente zwischen den spitzen Klammern.
    
Ein wichtiger Aspekt dieses <xref:System.Collections.Generic.List%601> Typ ist, dass es vergrößert oder verkleinert werden, können Sie zum Hinzufügen oder Entfernen von Elementen zu aktivieren. Fügen Sie diesen Code vor dem abschließenden `}` in die `Main` Methode:

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Sie haben zwei weitere Namen bis zum Ende der Liste hinzugefügt. Sie haben eine auch ebenfalls entfernt. Speichern der Datei, und geben `dotnet run` ausprobieren.
    
Die <xref:System.Collections.Generic.List%601> ermöglicht es Ihnen, einzelne Elemente von verweisen **Index** ebenfalls. Platzieren Sie den Index zwischen `[` und `]` Token, die nach dem Listennamen. C# für den ersten Index wird 0 verwendet. Fügen Sie diesen Code direkt unterhalb der Code, den Sie gerade hinzugefügt haben, und versuchen Sie es:

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

Sie können nicht auf einen Index hinter dem Ende der Liste zugreifen. Denken Sie daran, dass Indizes auf 0 (null) starten, damit der größte gültige Index eine ist kleiner als die Anzahl der Elemente in der Liste. Sie können überprüfen, wie lange die Liste verwendet die <xref:System.Collections.Generic.List%601.Count%2A> Eigenschaft. Fügen Sie den folgenden Code am Ende der Main-Methode hinzu:

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

Speichern der Datei, und geben `dotnet run` erneut aus, um die Ergebnisse anzuzeigen.    

## <a name="search-and-sort-lists"></a>Suchen und sortieren Listen
Unsere Beispiele relativ kleine Listen werden verwendet, aber Ihre Anwendungen möglicherweise häufig Listen mit viele weitere Elemente, manchmal in Tausenden Nummerierung erstellen. In diesen größere Sammlungen nach Elementen suchen möchten, müssen Sie die Liste der für verschiedene Elemente durchsuchen. Die <xref:System.Collections.Generic.List%601.IndexOf%2A> Methode sucht nach einem Element und gibt den Index des Elements zurück. Fügen Sie diesen Code am Ende Ihrer `Main` Methode:

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
    
}
```

Die Elemente in der Liste können auch sortiert werden. Die <xref:System.Collections.Generic.List%601.Sort%2A> Methode werden alle Elemente in der Liste in der normalen Reihenfolge (in alphabetischer Reihenfolge im Fall von Zeichenfolgen). Fügen Sie diesen Code am Ende unserer `Main` Methode:

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Speichern Sie die Datei und den Typ `dotnet run` versucht, diese neueste Version.

Bevor Sie im nächsten Abschnitt beginnen, fahren wir den aktuellen Code in eine separate Methode ein. Die erleichtert das Arbeiten mit einem neuen Beispiel. Benennen Sie Ihre `Main` aufzurufende Methode `WorkingWithStrings` und Schreiben Sie ein neues `Main` Methode, die aufgerufen `WorkingWithStrings`. Wenn Sie fertig sind, sollte der Code wie folgt aussehen:

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a>Listen mit anderen Typen

Haben Sie verwendet wurden die `string` Typ in Listen bisher. Wir stellen eine <xref:System.Collections.Generic.List%601> mithilfe eines anderen Typs. Erstellen Sie eine Menge von Zahlen. 

Fügen Sie Folgendes am Ende Ihrer neuen `Main` Methode:

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

Die eine Liste mit ganzen Zahlen erstellt, und legt die ersten beiden Ganzzahlen auf den Wert 1 fest. Dies sind die ersten beiden Werte, der eine *Fibonacci-Sequenz*, eine Sequenz von Zahlen. Jede nächste Fibonacci-Zahl wird ermittelt, indem die Summe der beiden vorherigen Zahlen. Fügen Sie diesen Code hinzu:

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Speichern Sie die Datei und den Typ `dotnet run` um die Ergebnisse anzuzeigen. 

> [!TIP]
> Um auf die nur in diesem Abschnitt zu konzentrieren, können Sie Auskommentieren der aufrufende Code `WorkingWithStrings();`. Einfach zwei `/` Zeichen vor dem Aufruf wie folgt: `// WorkingWithStrings();`. 

## <a name="challenge"></a>Herausforderung
Überprüfen, ob Sie zusammen platzieren können einige der in den Lektionen aus dieser und früheren Lektionen. Erweitern Sie auf, was Sie bisher mit Fibonacci-Zahlen erstellt haben. Versuchen Sie es, und Schreiben Sie den Code, um die ersten 20 Zahlen in der Sequenz zu generieren.

## <a name="complete-challenge"></a>Vollständige Herausforderung

Sehen Sie eine beispiellösung von [Betrachtung der fertig gestellten Beispiel-Codes auf GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs)

Bei jeder Iteration der Schleife weitergeleitet Sie die letzten beiden Ganzzahlen in der Liste, und diesen Wert zur Liste hinzufügen, summiert werden. Die Schleife wird wiederholt, bis Sie die Liste 20 Elemente hinzugefügt haben.

Herzlichen Glückwunsch, Sie haben das Lernprogramm Liste abgeschlossen.

Weitere Informationen finden Sie Informationen zum Arbeiten mit der `List` Geben Sie in der [Handbuch für die .NET](../../standard/index.md) Thema auf [Sammlungen](../../standard/collections/index.md). Sie erfahren auch über viele andere Sammlungstypen.
