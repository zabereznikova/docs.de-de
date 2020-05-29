---
title: Arbeiten mit Sammlungen – Tutorial zur Einführung in C#
description: Machen Sie sich mit C# vertraut, indem Sie die Listenauflistung in diesem Tutorial erkunden.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: c99f5582702120db238de1206de42d964837cdbd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396892"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a>Informationen zum Verwalten von Datensammlungen mithilfe des generischen Listentyps

Dieses Tutorial bietet eine Einführung in die Sprache C# und die Grundlagen der <xref:System.Collections.Generic.List%601>-Klasse.

Für dieses Tutorial benötigen Sie einen Computer, den Sie für die Entwicklung nutzen können. Im .NET-Tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (Hallo Welt in zehn Minuten) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter Windows, Linux oder macOS. Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie im Artikel [Einführung in Entwicklungstools](local-environment.md), der Links zu weiteren Ressourcen enthält.

## <a name="a-basic-list-example"></a>Beispiel für eine einfache Liste

Erstellen Sie ein Verzeichnis mit dem Namen *list-tutorial*. Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console` aus.

Öffnen Sie *Program.cs* in Ihrem bevorzugten Editor, und ersetzen Sie den vorhandenen Code durch Folgendes:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
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

Ersetzen Sie `<name>` durch Ihren eigenen Namen. Speichern Sie *Program.cs*. Geben Sie `dotnet run` in Ihrem Konsolenfenster ein, um es zu testen.

Sie haben eine Liste mit Zeichenfolgen erstellt, dieser Liste drei Namen hinzugefügt und die Namen in Großbuchstaben ausgegeben. Sie verwenden Konzepte, die Sie in früheren Tutorials kennengelernt haben, um die Liste zu durchlaufen.

Im Code zum Anzeigen von Namen wird das Feature [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md) genutzt.  Wenn Sie einem `string` ein `$`-Zeichen voranstellen, können Sie C#-Code in die Zeichenfolgendeklaration einbetten. Der Wert, den dieser C#-Code generiert, ist eine Zeichenfolge, durch die der C#-Code ersetzt wird. In diesem Beispiel wird `{name.ToUpper()}` mit dem jeweiligen in Großbuchstaben konvertierten Namen ersetzt, da Sie die <xref:System.String.ToUpper%2A>-Methode aufgerufen haben.

Setzen wir nun unsere Forschungen fort.

## <a name="modify-list-contents"></a>Ändern von Listeninhalten

Die Sammlung, die Sie erstellt haben, nutzt den <xref:System.Collections.Generic.List%601>-Typ. Dieser Typ speichert Elementsequenzen. Sie geben den Typ der Elemente zwischen den spitzen Klammern an.

Ein wichtiger Aspekt dieses <xref:System.Collections.Generic.List%601>-Typs ist, dass er wachsen oder schrumpfen kann, sodass Sie Elemente hinzufügen oder entfernen können. Fügen Sie diesen Code vor der abschließenden `}` in die `Main`-Methode ein:

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

Sie haben am Ende der Liste zwei weitere Namen hinzugefügt. Sie haben auch einen entfernt. Speichern Sie die Datei, und geben Sie `dotnet run` zum Testen ein.

<xref:System.Collections.Generic.List%601> ermöglicht Ihnen auch, mithilfe des **Indexes** auf einzelne Elemente zu verweisen. Platzieren Sie den Index hinter dem Listennamen zwischen den Zeichen `[` und `]`. C# verwendet 0 für den ersten Index. Fügen Sie diesen Code direkt unterhalb des Codes hinzu, den Sie gerade hinzugefügt haben, und probieren Sie es aus:

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

Sie können nicht auf einen Index zugreifen, der hinter dem Ende der Liste liegt. Denken Sie daran, dass die Indizes mit 0 (null) beginnen, sodass der größte gültige Index um eins kleiner ist als die Anzahl der Elemente in der Liste. Sie können mit der <xref:System.Collections.Generic.List%601.Count%2A>-Eigenschaft überprüfen, wie lang die Liste ist. Fügen Sie den folgenden Code am Ende der Main-Methode hinzu:

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

Speichern Sie die Datei, und geben Sie `dotnet run` erneut ein, um die Ergebnisse anzuzeigen.

## <a name="search-and-sort-lists"></a>Suchen in und Sortieren von Listen

In unseren Beispielen werden relativ kleine Listen verwendet, aber Ihre Anwendungen erstellen möglicherweise häufig Listen mit viel mehr Elementen, die manchmal in die Tausende gehen. Um in diesen größeren Sammlungen Elemente zu finden, müssen Sie die Liste nach verschiedenen Elementen durchsuchen. Die <xref:System.Collections.Generic.List%601.IndexOf%2A>-Methode sucht nach einem Element und gibt den Index des Elements zurück. Wenn das Element nicht in der Liste enthalten ist, gibt `IndexOf` `-1` zurück. Fügen Sie diesen Code am Ende der `Main`-Methode hinzu:

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

Die Elemente in der Liste können auch sortiert werden. Die <xref:System.Collections.Generic.List%601.Sort%2A>-Methode sortiert alle Elemente in der Liste in der normalen Reihenfolge (Zeichenfolgen alphabetisch). Fügen Sie diesen Code am Ende der `Main`-Methode hinzu:

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Speichern Sie die Datei, und geben Sie `dotnet run` ein, um diese neueste Version zu testen.

Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode. Dies erleichtert das Arbeiten mit einem neuen Beispiel. Benennen Sie Ihre `Main` -Methode in `WorkingWithStrings` um, und schreiben Sie eine neue `Main`-Methode, die `WorkingWithStrings` aufruft. Anschließend sollte der Code wie folgt aussehen:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
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
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

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

Sie haben bisher den `string`-Typ in Listen verwendet. Nun erstellen wir eine <xref:System.Collections.Generic.List%601> mithilfe eines anderen Typs. Zunächst erstellen wir einen Satz von Zahlen.

Fügen Sie Folgendes am Ende Ihrer neuen `Main`-Methode hinzu:

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

Damit wird eine Liste von Ganzzahlen erstellt und für die ersten beiden Ganzzahlen der Wert 1 festgelegt. Dies sind die ersten beiden Werte einer *Fibonacci-Sequenz* – einer Sequenz von Zahlen. Jede nächste Fibonacci-Zahl wird ermittelt, indem die Summe der beiden vorherigen Zahlen gebildet wird. Fügen Sie den folgenden Code hinzu:

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Speichern Sie die Datei, und geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.

> [!TIP]
> Um sich genau auf diesen Abschnitt zu konzentrieren, können Sie den Code auskommentieren, der `WorkingWithStrings();` aufruft. Setzen Sie einfach zwei `/`-Zeichen wie folgt vor den Aufruf: `// WorkingWithStrings();`.

## <a name="challenge"></a>Herausforderung

Versuchen Sie, einige dieser Konzepte aus dieser Lektion und früheren Lektionen in einen Zusammenhang zu bringen. Erweitern Sie das, was Sie bisher bezüglich Fibonacci-Zahlen erstellt haben. Schreiben Sie den Code zum Generieren der ersten 20 Zahlen der Sequenz. (Hinweis: Die 20. Fibonacci-Zahl lautet 6765.)

## <a name="complete-challenge"></a>Übung abgeschlossen

Eine Beispiellösung finden Sie in Form eines [fertiggestellten Beispielcodes auf GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).

Mit jeder Iteration der Schleife werden die letzten beiden Ganzzahlen in der Liste summiert, und dieser Wert wird der Liste hinzugefügt. Die Schleife wird wiederholt, bis der Liste 20 Elemente hinzugefügt worden sind.

Herzlichen Glückwunsch, Sie haben das Listentutorial abgeschlossen. Sie können mit dem Tutorial [Einführung in Klassen](introduction-to-classes.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.

Weitere Informationen zum Arbeiten mit dem `List`-Typ finden Sie im Artikel [Leitfaden für .NET](../../../standard/index.yml) unter [Sammlungen](../../../standard/collections/index.md). Sie werden auch viele andere Sammlungstypen kennenlernen.
