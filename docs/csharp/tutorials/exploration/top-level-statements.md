---
title: Anweisungen der obersten Ebene – C#-Tutorial
description: In diesem Tutorial wird gezeigt, wie Sie Anweisungen der obersten Ebene verwenden, um Konzepte zu testen und mithilfe Ihrer eigenen Ideen in der Praxis umzusetzen.
ms.date: 10/28/2020
ms.openlocfilehash: 5e5dc6cec382baa69ac8cb4625684315bb2cd5e0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282257"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a>Tutorial: Schreiben von Code durch das Umsetzen eigener Ideen mithilfe von Anweisungen der obersten Ebene

In diesem Tutorial lernen Sie Folgendes:

> [!div class="checklist"]
>
> - Kennenlernen der Regeln für die Verwendung von Anweisungen der obersten Ebene
> - Verwenden von Anweisungen der obersten Ebene zum Untersuchen von Algorithmen
> - Umwandeln von Erkenntnissen in wiederverwendbare Komponenten

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET 5 einrichten, einschließlich des C# 9-Compilers. Der C# 9-Compiler steht ab [Visual Studio 2019 Version 16.9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) oder [.NET 5.0 SDK](https://dot.net/get-dotnet5) zur Verfügung.

In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.

## <a name="start-exploring"></a>Ausprobieren

Mithilfe von Anweisungen der obersten Ebene können Sie den zusätzlichen erforderlichen Schritt vermeiden, indem Sie den Einstiegspunkt Ihres Programms in einer statischen Methode in einer Klasse platzieren. Der typische Startpunkt für eine neue Konsolenanwendung sieht wie der folgende Code aus:

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Der vorangehende Code ist das Ergebnis der Ausführung des `dotnet new console`-Befehls und der Erstellung einer neuen Konsolenanwendung. Diese elf Zeilen enthalten nur eine Zeile ausführbaren Codes. Sie können dieses Programm mit dem neuen Feature für Anweisungen der obersten Ebene vereinfachen. Dadurch können Sie in diesem Programm bis auf zwei Zeilen alle anderen Zeilen entfernen.

```csharp
using System;

Console.WriteLine("Hello World!");
```

Durch diese Aktion wird das Umsetzen neuer Ideen vereinfacht. Sie können Anweisungen der obersten Ebene für Skripterstellungsszenarios oder zum Durchsuchen verwenden. Sobald Sie die Grundlagen beherrschen, können Sie mit dem Umgestalten des Codes beginnen und Methoden, Klassen oder andere Assemblys für von Ihnen entwickelte wiederverwendbare Komponenten erstellen. Anweisungen der obersten Ebene ermöglichen das schnelle Testen von Code und bieten eine gute Grundlage für Einsteigertutorials. Außerdem bieten sie eine praktische Möglichkeit für den Übergang von Experimenten mit Code hin zu vollständigen Programmen.

Anweisungen der obersten Ebene werden in der Reihenfolge ausgeführt, in der sie in der Datei aufgeführt sind. Sie können nur in einer Quelldatei in der Anwendung verwendet werden. Der Compiler generiert einen Fehler, wenn Sie die Anweisungen in mehr als einer Datei verwenden.

## <a name="build-a-magic-net-answer-machine"></a>Entwickeln eines „magischen“ .NET-Programms zum Ausgeben von Antworten

In diesem Tutorial erstellen Sie eine Konsolenanwendung, die eine Frage, die mit „Ja“ oder „Nein“ beantwortet wird, zufällig beantwortet. Sie erstellen die Funktionalität Schritt für Schritt. Sie können sich auf Ihre Aufgabe konzentrieren, anstatt sich mit dem Prozess zum Entwickeln der Struktur eines typischen Programms beschäftigen zu müssen. Sobald Sie mit der Funktionalität zufrieden sind, können Sie die Anwendung nach Bedarf umgestalten.

Es ist ein guter Startpunkt, die Frage wieder in die Konsole zu schreiben. Sie können beginnen, indem Sie den folgenden Code schreiben:

```csharp
using System;

Console.WriteLine(args);
```

Sie deklarieren keine `args`-Variable. Im Zusammenhang mit der einzelnen Quelldatei, die die Anweisungen der obersten Ebene enthält, erkennt der Compiler, dass `args` für die Befehlszeilenargumente steht. Dies sind wie in allen C#-Programmen Argumente vom Typ `string[]`.

Sie können den Code testen, indem Sie den folgenden `dotnet run`-Befehl ausführen:

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

Die Argumente nach `--` in der Befehlszeile werden an das Programm weitergegeben. Sie können den Typ der `args`-Variable sehen, da diese Information in der Konsole angezeigt wird:

```console
System.String[]
```

Sie müssen die Argumente einzeln benennen und durch ein Leerzeichen trennen, um die Frage in die Konsole zu schreiben. Ersetzen Sie den `WriteLine`-Aufruf durch den folgenden Code:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

Wenn Sie das Programm ausführen, wird die Frage nun ordnungsgemäß als Zeichenfolge von Argumenten angezeigt.

## <a name="respond-with-a-random-answer"></a>Antworten mit einer zufälligen Antwort

Nachdem Sie die Frage wiederholt haben, können Sie den Code hinzufügen, um die zufällige Antwort zu generieren. Fügen Sie zunächst ein Array möglicher Antworten hinzu:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

Dieses Array umfasst zwölf positive, sechs zurückhaltende und sechs negative Antworten. Fügen Sie als Nächstes den folgenden Code hinzu, um eine zufällige Antwort aus dem Array zu generieren und anzuzeigen:

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

Sie können die Anwendung noch mal ausführen, um die Ergebnisse anzuzeigen. Es sollte nun etwa die folgende Ausgabe angezeigt werden:

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

Mit diesem Code werden die Fragen beantwortet, allerdings fügen Sie noch ein weiteres Feature hinzu. Ihre Frage-App soll das Nachdenken vor dem Ausgeben der Antwort simulieren. Dies erreichen Sie, indem Sie eine ASCII-Animation (American Standard Code for Information Interchange) hinzufügen und den restlichen Vorgang während der Bearbeitung anhalten.  Fügen Sie den folgenden Code nach der Zeile hinzu, die die Frage wiederholt:

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

Außerdem müssen Sie am Anfang der Quelldatei eine `using`-Anweisung hinzufügen:

```csharp
using System.Threading.Tasks;
```

Die `using`-Anweisungen müssen sich vor allen anderen Anweisungen in der Datei befinden. Andernfalls tritt ein Compilerfehler auf. Sie können das Programm noch mal ausführen und die Animation anzeigen. Dies ermöglicht eine bessere Nutzung des Programms. Experimentieren Sie hinsichtlich der Länge der Verzögerung, bis Sie mit dem Ergebnis zufrieden sind.

Der vorangehende Code erstellt eine Reihe von Zeilen, die durch ein Leerzeichen voneinander getrennt sind. Durch das Hinzufügen des Schlüsselworts `await` wird der Compiler angewiesen, den Programmeinstiegspunkt als Methode zu generieren, die den `async`-Modifizierer aufweist und die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse zurückgibt. Dieses Programm gibt keinen Wert zurück, sodass der Programmeinstiegspunkt `Task` zurückgibt. Wenn das Programm einen ganzzahligen Wert zurückgibt, fügen Sie eine return-Anweisung am Ende der Anweisungen der obersten Ebene hinzu. Diese return-Anweisung gibt den ganzzahligen Wert an, der zurückgegeben wird. Wenn die Anweisungen der obersten Ebene einen `await`-Ausdruck enthalten, wird der Rückgabetyp zu einer <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Klasse.

## <a name="refactoring-for-the-future"></a>Umgestaltung für die Zukunft

Ihr Programm sollte wie der folgende Code aussehen:

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don’t count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

Der vorangehende Code ist nützlich. Er funktioniert. Er kann jedoch nicht erneut verwendet werden. Nachdem die Anwendung jetzt funktioniert, ist es an der Zeit, wiederverwendbare Teile zu extrahieren.

Eine Option hierfür ist der Code, der die Animation beim Warten während des Vorgangs anzeigt. Aus diesem Codeausschnitt kann eine Methode werden:

Erstellen Sie hierfür zunächst eine lokale Funktion in der Datei. Ersetzen Sie die aktuelle Animation durch den folgenden Code:

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

Der vorangehende Code erstellt eine lokale Funktion in der Main-Methode. Diese ist immer noch nicht wiederverwendbar. Extrahieren Sie den Code daher in eine Klasse. Erstellen Sie eine neue Datei namens *utilities.cs* , und fügen Sie den folgenden Code hinzu:

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

Anweisungen der obersten Ebene können nur in einer Datei enthalten sein, und diese Datei darf keine Namespaces oder Typen enthalten.

Zum Schluss können Sie den Animationscode bereinigen, um Duplizierungen zu entfernen:

:::code language="csharp" source="snippets/top-level-statements/Utilities.cs" ID="Animation":::

Nun verfügen Sie über eine komplette Anwendung, und Sie haben die wiederverwendbaren Teile für die spätere Verwendung umgestaltet.

## <a name="summary"></a>Zusammenfassung

Anweisungen der obersten Ebene vereinfachen das Erstellen einfacher Programme, mit denen neue Algorithmen untersucht werden können. Sie können mit Algorithmen experimentieren, indem Sie verschiedene Codeausschnitte ausprobieren. Nachdem Sie gelernt haben, was funktioniert, können Sie den Code so umgestalten, dass er leichter verwaltet werden kann.

Anweisungen der obersten Ebene vereinfachen Programme, die auf Konsolenanwendungen basieren. Hierzu gehören Azure-Funktionen, GitHub-Aktionen und andere kleine Hilfsprogramme.
