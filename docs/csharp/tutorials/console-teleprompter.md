---
title: Konsolenanwendung
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
ms.date: 03/06/2017
ms.technology: csharp-fundamentals
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: 921c8fc7824bdb48f08e4d9f5a276bf2284f8a17
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714602"
---
# <a name="console-app"></a>Konsolen-App

In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen. Es werden die folgenden Themen abgedeckt:

- Grundlagen der .NET Core-Befehlszeilenschnittstelle (CLI)
- Die Struktur einer C#-Konsolenanwendung
- Konsolen-E/A
- Grundlagen der Datei-E/A-APIs in .NET
- Grundlagen des taskbasierten asynchronen Programmiermodells in .NET

Sie erstellen eine Anwendung, die eine Textdatei liest und die Inhalte dieser Textdatei an die Konsole ausgibt. Das Tempo der Ausgabe in der Konsole ist so festgelegt, dass ein lautes Mitlesen möglich ist. Sie können die Ausgabe beschleunigen oder verlangsamen, indem Sie die Tasten „<“ (kleiner als) oder „>“ (größer als) drücken.

In diesem Tutorial werden viele Features abgedeckt. Gehen wir sie einzeln an.

## <a name="prerequisites"></a>Voraussetzungen

- Richten Sie Ihren Computer für die Ausführung von .NET Core ein. Die Installationsanweisungen finden Sie auf der Seite [.NET Core-Downloads](https://dotnet.microsoft.com/download). Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.

- Installieren Sie Ihren bevorzugten Code-Editor.

## <a name="create-the-app"></a>Erstellen der App

Im ersten Schritt wird eine neue Anwendung erstellt. Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung. Legen Sie das Verzeichnis als aktuelles Verzeichnis fest. Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein. Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.

Bevor Sie damit beginnen, Änderungen durchzuführen, gehen wir die Schritte zur Ausführung der einfachen Hello World-Anwendung durch. Geben Sie nach dem Erstellen der Anwendung den Befehl `dotnet restore` an der Eingabeaufforderung ein. Mit diesem Befehl wird der Prozess zur NuGet-Paketwiederherstellung ausgeführt. NuGet ist ein .NET-Paket-Manager. Mit diesem Befehl werden alle fehlenden abhängigen Komponenten für Ihr Projekt heruntergeladen. Da es sich um ein neues Projekt handelt, ist keine der abhängigen Komponenten vorhanden, deshalb wird zunächst das .NET Core-Framework heruntergeladen. Nach diesem ersten Schritt müssen Sie `dotnet restore` nur ausführen, wenn Sie neue abhängige Pakete hinzufügen oder die Versionen abhängiger Komponenten aktualisieren.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Nach dem Wiederherstellen der Pakete führen Sie `dotnet build` aus. Hiermit wird die Build-Engine ausgeführt und die ausführbare Datei für Ihre Anwendung erstellt. Abschließend führen Sie `dotnet run` aus, um Ihre Anwendung zu starten.

Der gesamte Code für die einfache Hello World-Anwendung ist in „Program.cs“ enthalten. Öffnen Sie diese Datei mit Ihrem bevorzugten Text-Editor. Wir werden jetzt die ersten Änderungen vornehmen. Am Anfang der Datei sehen Sie eine using-Anweisung:

```csharp
using System;
```

Diese Anweisung informiert den Compiler, dass alle Typen aus dem `System`-Namespace im Gültigkeitsbereich liegen. Wie andere objektorientierte Sprachen, die Sie vielleicht schon verwendet haben, verwendet C# Namespaces, um Typen zu organisieren. Dieses Hello World-Programm funktioniert genauso. Sie können sehen, dass das Programm in den Namespace eingeschlossen ist, wobei der Name auf dem des aktuellen Verzeichnisses basiert. Für dieses Tutorial ändern wir den Namen des Namespace in `TeleprompterConsole`:

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a>Lesen und Ausgeben der Datei

Das erste hinzuzufügende Feature ist die Möglichkeit zum Lesen einer Textdatei und zum Anzeigen des gesamten Texts in der Konsole. Fügen wir zunächst eine Textdatei hinzu. Kopieren Sie die Datei [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) aus dem GitHub-Repository für dieses [Beispiel](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) in Ihr Projektverzeichnis. Diese Datei dient als Skript für Ihre Anwendung. Wenn Sie Informationen dazu erhalten möchten, wie Sie die Beispiel-App für dieses Thema herunterladen, finden Sie Anweisungen im Thema [Beispiele und Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Fügen Sie als Nächstes die folgende Methode in Ihre `Program`-Klasse ein (rechts neben der `Main`-Methode):

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

Diese Methode verwendet Typen aus zwei neuen Namespaces. Für die Kompilierung müssen Sie oben in der Datei die folgenden zwei Zeilen einfügen:

```csharp
using System.Collections.Generic;
using System.IO;
```

Die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle ist im <xref:System.Collections.Generic>-Namespace definiert. Die <xref:System.IO.File>-Klasse ist im <xref:System.IO>-Namespace definiert.

Diese Methode ist ein besonderer Typ von C#-Methode, der als *Iteratormethode* bezeichnet wird. Enumeratormethoden geben Sequenzen zurück, die verzögert ausgewertet werden. Dies bedeutet, dass jedes Element in der Sequenz dann generiert wird, wenn es vom Code angefordert wird, der die Sequenz verarbeitet. Enumeratormethoden sind Methoden, die mindestens eine [`yield return`](../language-reference/keywords/yield.md)-Anweisung enthalten. Das von der `ReadFrom`-Methode zurückgegebene Objekt enthält den Code zum Generieren aller Elemente in der Sequenz. In diesem Beispiel umfasst dies das Einlesen der nächsten Textzeile aus der Quelldatei und die Rückgabe dieser Zeichenfolge. Jedes Mal, wenn der aufrufende Code die nächste Zeile aus der Sequenz anfordert, liest der Code die nächste Zeile aus der Textdatei und gibt sie zurück. Wenn die Datei vollständig gelesen wurde, gibt die Sequenz an, dass keine weiteren Elemente vorhanden sind.

Es gibt zwei weitere C#-Syntaxelemente, die möglicherweise neu für Sie sind. Die [`using`](../language-reference/keywords/using-statement.md)-Anweisung in dieser Methode verwaltet die Ressourcenbereinigung. Die Variable, die in der `using`-Anweisung initialisiert wird – in diesem Beispiel `reader` –, muss die <xref:System.IDisposable>-Schnittstelle implementieren. Diese Schnittstelle definiert eine einzige Methode, `Dispose`, die aufgerufen werden muss, wenn die Ressource freigegeben werden soll. Der Compiler generiert diesen Aufruf, wenn die Ausführung die schließende geschweifte Klammer der `using`-Anweisung erreicht. Der vom Compiler generierte Code stellt sicher, dass die Ressource selbst dann freigegeben wird, wenn der Code im durch die using-Anweisung definierten Block eine Ausnahme auslöst.

Die `reader`-Variable wird mit dem `var`-Schlüsselwort definiert. [`var`](../language-reference/keywords/var.md) definiert eine *implizit typisierte lokale Variable*. Dies bedeutet, dass der Typ der Variablen durch den Kompilierzeittyp des Objekts bestimmt wird, das der Variablen zugewiesen ist. Hier ist dies der Rückgabewert der <xref:System.IO.File.OpenText(System.String)>-Methode, bei dem es sich um ein <xref:System.IO.StreamReader>-Objekt handelt.

Geben Sie jetzt den Code ein, um die Datei in der `Main`-Methode zu lesen:

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

Führen Sie das Programm (unter Verwendung von `dotnet run`) aus. Jede Zeile wird einzeln an der Konsole ausgegeben.

## <a name="adding-delays-and-formatting-output"></a>Hinzufügen von Verzögerungen und Formatieren der Ausgabe

Der Text wird momentan zu schnell ausgegeben, um ihn laut mitzulesen. Jetzt müssen Sie Verzögerungen in der Ausgabe hinzufügen. Zu Beginn erstellen Sie einen Teil des grundlegenden Codes, der asynchrone Verarbeitung ermöglicht. Auf diese ersten Schritte folgen jedoch einige Antimuster. Die Antimuster werden in Kommentaren erläutert, die Sie im Code hinzufügen, und der Code wird in späteren Schritten aktualisiert.

Dieser Abschnitt umfasst zwei Schritte. Zunächst aktualisieren Sie die Iteratormethode, um anstelle von ganzen Zeilen einzelne Wörter zurückzugeben. Dies wird durch diese Änderungen erreicht. Ersetzen Sie die `yield return line;`-Anweisung durch den folgenden Code:

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

Als Nächstes ändern Sie die Art und Weise, in der die Dateizeilen verarbeitet werden und fügen nach jedem geschriebenen Wort eine Verzögerung hinzu. Ersetzen Sie die `Console.WriteLine(line)`-Anweisung in der `Main`-Methode durch den folgenden Block:

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

Die <xref:System.Threading.Tasks.Task>-Klasse ist im <xref:System.Threading.Tasks>-Namespace enthalten, deshalb müssen Sie diese `using`-Anweisung am Anfang der Datei hinzufügen:

```csharp
using System.Threading.Tasks;
```

Führen Sie das Beispiel aus, und überprüfen Sie die Ausgabe. Jetzt folgt nach der Ausgabe jedes Worts eine Pause von 200 ms. Die angezeigte Ausgabe ist jedoch fehlerhaft, weil der Quelltext mehrere Zeilen umfasst, die mehr als 80 Zeichen ohne Zeilenumbruch aufweisen. Der Text ist möglicherweise schwer zu lesen, wenn er ohne Umbrüche angezeigt wird. Dieses Problem kann einfach gelöst werden. Sie verfolgen einfach die Länge jeder Zeile nach und generieren immer dann eine neue Zeile, wenn die Zeilenlänge einen bestimmten Schwellenwert überschreitet. Deklarieren Sie nach der Deklaration von `words` in der `ReadFrom`-Methode eine lokale Variable, die die Zeilenlänge enthält:

```csharp
var lineLength = 0;
```

Fügen Sie dann nach der `yield return word + " ";`-Anweisung (vor der schließenden geschweiften Klammer) den folgenden Code hinzu:

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

Führen Sie das Beispiel aus. Jetzt sollten Sie in der Lage sein, den Text im festgelegten Tempo laut mitzulesen.

## <a name="async-tasks"></a>Asynchrone Tasks

In diesem letzten Schritt fügen Sie den Code hinzu, mit dem in einem Task die Ausgabe asynchron geschrieben wird, während in einem weiteren Task Eingaben vom Benutzer gelesen werden, um ggf. die Geschwindigkeit der Textanzeige zu erhöhen oder zu verringern oder die Textanzeige ganz zu beenden. Hierzu sind einige Schritte erforderlich, damit Sie am Ende über alle benötigten Aktualisierungen verfügen. Im ersten Schritt erstellen Sie eine asynchrone <xref:System.Threading.Tasks.Task>-Rückgabemethode, die den Code darstellt, den Sie bisher zum Lesen und Anzeigen der Datei erstellt haben.

Fügen Sie diese Methode Ihrer `Program`-Klasse hinzu (diese stammt aus dem Textkörper Ihrer `Main`-Methode):

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

Sie werden zwei Änderungen bemerken. Zunächst wird im Methodenkörper anstelle eines Aufrufs von <xref:System.Threading.Tasks.Task.Wait> zum synchronen Warten auf eine Taskbeendigung in dieser Version das Schlüsselwort `await` verwendet. Hierzu müssen Sie der Methodensignatur den `async`-Modifizierer hinzufügen. Diese Methode gibt einen `Task` zurück. Beachten Sie, dass es keine return-Anweisungen gibt, die ein `Task`-Objekt zurückgeben. Stattdessen wird dieses `Task`-Objekt durch Code erstellt, den der Compiler beim Verwenden des `await`-Operators generiert. Sie können sich dies so vorstellen, dass die Methode eine Rückgabe durchführt, wenn sie ein `await`-Schlüsselwort erreicht. Der zurückgegebene `Task` gibt an, dass der Vorgang noch nicht abgeschlossen wurde. Die Methode wird fortgesetzt, wenn der erwartete Task abgeschlossen ist. Nach Abschluss der Ausführung weist der zurückgegebene `Task` darauf hin, dass er abgeschlossen wurde.
Der aufrufende Code kann den zurückgegebenen `Task` überwachen, um zu ermitteln, wann dieser abgeschlossen ist.

Sie können diese neue Methode in Ihrer `Main`-Methode aufrufen:

```csharp
ShowTeleprompter().Wait();
```

Hier führt der Code in `Main` einen asynchronen Wartevorgang aus. Sie sollten nach Möglichkeit anstelle eines synchronen Wartevorgangs immer den `await`-Operator verwenden. In der `Main`-Methode einer Konsolenanwendung kann der `await`-Operator jedoch nicht verwendet werden. Dies würde dazu führen, dass die Anwendung beendet wird, bevor alle Tasks abgeschlossen sind.

> [!NOTE]
> Wenn Sie C# 7.1 oder höher verwenden, können Sie Konsolenanwendungen mit der [`async` `Main`-Methode](../whats-new/csharp-7-1.md#async-main) erstellen.

Als Nächstes müssen Sie die zweite asynchrone Methode schreiben, um Inhalte aus der Konsole zu lesen und auf die Tasteneingaben „<“ (kleiner als) und „>“ (größer als) sowie „X“ und „x“ zu überwachen. Dies ist die Methode, die Sie für diesen Task hinzufügen:

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
            {
                break;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

Hiermit wird ein Lambdaausdruck zur Darstellung eines <xref:System.Action>-Delegaten erstellt. Mit diesem wird ein Schlüssel aus der Konsole gelesen und eine lokale Variable geändert, die die Verzögerung beim Drücken der Tasten „<“ (kleiner als) oder „>“ (größer als) durch den Benutzer darstellt. Die Delegatmethode wird beendet, wenn der Benutzer die Tasten „X“ oder „x“ drückt, sodass der Benutzer die Textanzeige jederzeit beenden kann. Diese Methode verwendet <xref:System.Console.ReadKey> zum Blockieren und wartet darauf, dass der Benutzer eine Taste drückt.

Um dieses Feature abzuschließen, müssen Sie eine neue `async Task`-Rückgabemethode erstellen, die beide Tasks (`GetInput` und `ShowTeleprompter`) startet und außerdem die von diesen Tasks gemeinsam verwendeten Daten verwaltet.

Es muss eine neue Klasse erstellt werden, mit der die von diesen zwei Tasks gemeinsam verwendeten Daten verarbeitet werden können. Diese Klasse enthält zwei öffentliche Eigenschaften: die Verzögerung und ein Flag `Done`, mit dem angegeben wird, dass die Datei vollständig gelesen wurde:

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            DelayInMilliseconds = newDelay;
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

Platzieren Sie diese Klasse in einer neuen Datei, und fügen Sie diese Klasse in den `TeleprompterConsole`-Namespace ein (wie oben gezeigt). Sie benötigen außerdem eine `using static`-Anweisung, damit Sie ohne die Namen der übergeordneten Klasse oder des Namespace auf die `Min`- und `Max`-Methode verweisen können. Eine [`using static`](../language-reference/keywords/using-static.md)-Anweisung importiert die Methoden einer Klasse. Dies steht in Kontrast zu den bisher verwendeten `using`-Anweisungen, die alle Klassen aus einem Namespace importiert haben.

```csharp
using static System.Math;
```

Im nächsten Schritt müssen Sie die `ShowTeleprompter`- und `GetInput`-Methoden zur Verwendung des neuen `config`-Objekts aktualisieren. Schreiben Sie einen finalen `Task`, der die `async`-Methode zurückgibt, um beide Tasks zu starten und den Vorgang zu beenden, sobald der erste Task beendet wird:

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

Die neue Methode hier ist der <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>-Aufruf. Hiermit wird ein `Task` erstellt, der abgeschlossen wird, sobald einer der Tasks in dieser Argumentliste beendet ist.

Im nächsten Schritt müssen Sie die `ShowTeleprompter`- und `GetInput`-Methoden zur Verwendung des neuen `config`-Objekts aktualisieren:

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
                config.SetDone();
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

Diese neue Version von `ShowTeleprompter` ruft eine neue Methode in der `TeleprompterConfig`-Klasse auf. Jetzt müssen Sie `Main` aktualisieren, um anstelle von `ShowTeleprompter``RunTeleprompter` aufzurufen:

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a>Schlussbemerkung

In diesem Tutorial wurden verschiedene Features von C# und den .NET Core-Bibliotheken vorgestellt, die bei der Arbeit in Konsolenanwendungen benötigt werden. Sie können auf diesem Wissen aufbauen, um C# und die hier beschriebenen Klassen weiter zu erkunden. Sie haben die Grundlagen der Datei- und Konsolen-E/A kennengelernt, und es wurden die blockierende und die nicht blockierende Verwendung der taskbasierten asynchronen Programmierung vorgestellt. Außerdem haben Sie einen Überblick über die Sprache C# und die Struktur von C#-Programmen erhalten, und Sie haben die .NET Core-Befehlszeilenschnittstelle (CLI) und andere Tools kennengelernt.

Weitere Informationen zur Datei-E/A finden Sie im Thema [Datei- und Stream-E/A](../../standard/io/index.md). Weitere Informationen zu dem in diesem Tutorial verwendeten asynchronen Programmiermodell finden sie in den Themen [Aufgabenbasierte asynchrone Programmierung](../..//standard/parallel-programming/task-based-asynchronous-programming.md) und [Asynchrone Programmierung](../async.md).
