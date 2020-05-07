---
title: Generieren und Nutzen asynchroner Datenströme
description: In diesem Tutorial für Fortgeschrittene wird veranschaulicht, wie asynchrone Streams generiert und verwendet werden. Asynchrone Streams erleichtern die Arbeit mit Datensequenzen, die asynchron generiert werden können.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: 03254e5208a048469f4753d632de7b0d451cde40
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200105"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a>Tutorial: Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0

C# 8.0 führt **asynchrone Streams** ein, die eine Streamingdatenquelle modellieren. In Datenströmen werden Elemente häufig asynchron abgerufen oder generiert. Asynchrone Streams basieren auf neuen Schnittstellen, die in .NET Standard 2.1 eingeführt wurden. Diese Schnittstellen werden in .NET Core 3.0 und höher unterstützt. Sie stellen ein intuitives Programmiermodell für asynchrone Streamingdatenquellen bereit.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Erstellen einer Datenquelle, die eine Sequenz von Datenelementen asynchron generiert
> - Asynchrones Nutzen dieser Datenquelle
> - Unterstützung für Abbruchvorgänge und erfasste Kontexte für asynchrone Streams
> - Erkennen, wenn die neue Schnittstelle und Datenquelle früheren synchronen Datensequenzen vorgezogen werden

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers. Der C# 8-Compiler steht ab [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder mit dem [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) zur Verfügung.

Sie müssen ein [GitHub-Zugriffstoken](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) erstellen, damit Sie auf den GitHub GraphQL-Endpunkt zugreifen können. Wählen Sie die folgenden Berechtigungen für Ihr GitHub-Zugriffstoken aus:

- repo:status
- public_repo

Speichern Sie das Zugriffstoken an einem sicheren Ort, damit Sie es für den Zugriff auf den GitHub-API-Endpunkt verwenden können.

> [!WARNING]
> Schützen Sie Ihr persönliches Zugriffstoken. Jede Software mit Ihrem persönlichen Zugriffstoken kann mit Ihren Zugriffsrechten GitHub-API-Aufrufe ausführen.

In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.

## <a name="run-the-starter-application"></a>Ausführen der Startanwendung

Sie können den Code für die in diesem Tutorial verwendete Startanwendung aus unserem Repository [dotnet/docs](https://github.com/dotnet/docs) im Ordner [csharp/tutorials/AsyncStreams](https://github.com/dotnet/docs/tree/master/csharp/tutorials/snippets/generate-consume-asynchronous-streams/start) abrufen.

Die Startanwendung ist eine Konsolenanwendung, die die [GitHub GraphQL](https://developer.github.com/v4/)-Schnittstelle zum Abrufen aktueller Issues verwendet, die in das Repository [dotnet/docs](https://github.com/dotnet/docs) geschrieben wurden. Sehen Sie sich zunächst folgenden Code für die `Main`-Methode der Starter-App an:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetStarterAppMain" :::

Sie können entweder eine `GitHubKey`-Umgebungsvariable auf Ihr persönliches Zugriffstoken festlegen, oder Sie können das letzte Argument im Aufruf von `GenEnvVariable` durch Ihr persönliches Zugriffstoken ersetzen. Fügen Sie Ihren Zugriffscode nicht in den Quellcode ein, wenn Sie die Quelle für andere freigeben. Laden Sie Zugriffscodes niemals in ein freigegebenes Quellrepository hoch.

Nach dem Erstellen des GitHub-Clients werden durch den Code in `Main` ein Objekt für Fortschrittsberichte und ein Abbruchtoken erstellt. Nachdem die Objekte erstellt wurden, wird `runPagedQueryAsync` durch `Main` aufgerufen, um die neuesten 250 Issues abzurufen. Nach Abschluss dieser Aufgabe werden die Ergebnisse angezeigt.

Bei Ausführung der Startanwendung können Sie einige wichtige Details zur Ausführung dieser Anwendung beobachten.  Für jede von GitHub zurückgegebene Seite wird der Fortschritt gemeldet. Sie können eine deutliche Pause beobachten, bevor GitHub eine weitere neue Seite mit Issues zurückgibt. Die Issues werden erst angezeigt, nachdem alle zehn Seiten aus GitHub abgerufen wurden.

## <a name="examine-the-implementation"></a>Untersuchen der Implementierung

Die Implementierung zeigt, warum Sie das im vorherigen Abschnitt beschriebene Verhalten beobachten konnten. Untersuchen Sie den Code für `runPagedQueryAsync`:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetRunPagedQuery" :::

Konzentrieren wir uns auf den Paginierungsalgorithmus und die asynchrone Struktur des obigen Codes. (Details zur GitHub GraphQL-API finden Sie in der [GitHub GraphQL-Dokumentation](https://developer.github.com/v4/guides/).) Die `runPagedQueryAsync`-Methode listet die Issues vom neuesten zum ältesten auf. Sie fordert 25 Issues pro Seite an und untersucht die `pageInfo`-Struktur der Antwort, um mit der vorherigen Seite fortzufahren. Dies entspricht der GraphQL-Standardpaginierungsunterstützung für mehrseitige Antworten. Die Antwort enthält ein `pageInfo`-Objekt mit einem `hasPreviousPages`-Wert und einem `startCursor`-Wert zum Anfordern der vorherigen Seite. Die Issues befinden sich im `nodes`-Array. Die `runPagedQueryAsync`-Methode fügt diese Knoten einem Array an, das alle Ergebnisse aus allen Seiten enthält.

Nach dem Abrufen und Wiederherstellen einer Seite mit Ergebnissen meldet `runPagedQueryAsync` den Fortschritt und prüft auf Abbruch. Wenn ein Abbruch angefordert wurde, löst `runPagedQueryAsync` eine <xref:System.OperationCanceledException> aus.

Es gibt mehrere Elemente in diesem Code, die verbessert werden können. Vor allem muss `runPagedQueryAsync` Speicherplatz für alle zurückgegebenen Issues zuordnen. In diesem Beispiel wird der Vorgang bei 250 Issues beendet, weil das Abrufen aller offenen Issues wesentlich mehr Arbeitsspeicher zum Speichern aller abgerufenen Issues erfordern würde. Der Algorithmus ist durch die Protokolle zur Unterstützung von Fortschrittsberichten und Abbruchvorgängen beim ersten Lesen schwieriger zu verstehen. Es sind mehr Typen und APIs beteiligt. Außerdem müssen Sie die Kommunikation über <xref:System.Threading.CancellationTokenSource> und die zugehörige <xref:System.Threading.CancellationToken>-Struktur verfolgen, um nachzuvollziehen, wo der Abbruch angefordert und wo er gewährt wird.

## <a name="async-streams-provide-a-better-way"></a>Bessere Möglichkeiten durch asynchrone Datenströme

Mit asynchronen Datenströmen und der zugehörigen Sprachunterstützung lassen sich diese Probleme beheben. Der Code, der die Sequenz generiert, kann mit `yield return` jetzt Elemente in einer Methode zurückgeben, die mit dem `async`-Modifizierer deklariert wurde. Sie können einen asynchronen Datenstrom mit einer `await foreach`-Schleife genau so nutzen, wie Sie eine beliebige Sequenz mit einer `foreach`-Schleife einsetzen.

Diese neuen Sprachfeatures hängen von drei neuen Schnittstellen ab, die dem .NET Standard 2.1 hinzugefügt und in .NET Core 3.0 implementiert wurden:

- <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>
- <xref:System.IAsyncDisposable?displayProperty=nameWithType>

Diese drei Schnittstellen sollten den meisten C#-Entwicklern vertraut sein. Sie verhalten sich ähnlich wie ihre synchronen Gegenstücke:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

Ein möglicherweise weniger bekannter Typ ist <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>. Die `ValueTask`-Struktur bietet eine ähnliche API für die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse. `ValueTask` wird in diesen Schnittstellen aus Leistungsgründen verwendet.

## <a name="convert-to-async-streams"></a>Konvertieren in asynchrone Datenströme

Als Nächstes konvertieren Sie die `runPagedQueryAsync`-Methode, um einen asynchronen Datenstrom zu generieren. Ändern Sie zunächst die Signatur von `runPagedQueryAsync` so, dass ein `IAsyncEnumerable<JToken>` zurückgegeben wird, und entfernen Sie das Abbruchtoken und die Fortschrittsobjekte aus der Parameterliste, wie im folgenden Code gezeigt:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetUpdateSignature" :::

Der Startcode verarbeitet die einzelnen Seiten, während sie abgerufen werden, wie im folgenden Code gezeigt:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetProcessPage" :::

Ersetzen Sie diese drei Zeilen durch den folgenden Code:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetYieldReturnPage" :::

Sie können auch die Deklaration von `finalResults` weiter oben in dieser Methode sowie die `return`-Anweisung entfernen, die der von Ihnen geänderten Schleife folgt.

Sie haben die Änderungen zum Generieren eines asynchronen Datenstroms abgeschlossen. Die fertige Methode sollte in etwa dem folgenden Code entsprechen:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetGenerateAsyncStream" :::

Als Nächstes ändern Sie den Code, der die Sammlung nutzt, um den asynchronen Datenstrom zu verwenden. Suchen Sie in `Main` den folgenden Code, der die Sammlung der Issues verarbeitet:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/start/Program.cs" id="SnippetEnumerateOldStyle" :::

Ersetzen Sie den Code durch die folgende `await foreach`-Schleife:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetEnumerateAsyncStream" :::

Die neue Schnittstelle <xref:System.Collections.Generic.IAsyncEnumerator%601> leitet von <xref:System.IAsyncDisposable> ab. Das bedeutet, dass die vorhergehende Schleife den Stream asynchron löscht, wenn die Schleife beendet wird. Die Schleife ähnelt dem folgenden Code:

```csharp
int num = 0;
var enumerator = runPagedQueryAsync(client, PagedIssueQuery, "docs").GetEnumeratorAsync();
try
{
    while (await enumerator.MoveNextAsync())
    {
        var issue = enumerator.Current;
        Console.WriteLine(issue);
        Console.WriteLine($"Received {++num} issues in total");
    }
} finally
{
    if (enumerator != null)
        await enumerator.DisposeAsync();
}
```

Standardmäßig werden Streamelemente im erfassten Kontext verarbeitet. Wenn Sie die Erfassung des Kontexts deaktivieren möchten, verwenden Sie die Erweiterungsmethode <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Weitere Informationen über Synchronisierungskontexte und die Erfassung des aktuellen Kontexts finden Sie im Artikel über das [Verwenden des aufgabenbasierten asynchronen Musters](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

Asynchrone Streams unterstützen Abbruchvorgänge mithilfe desselben Protokolls wie andere `async`-Methoden. Ändern Sie die Signatur für die asynchrone Iteratormethode folgendermaßen, damit Abbruchvorgänge unterstützt werden:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetGenerateWithCancellation" :::

Das <xref:System.Runtime.CompilerServices.EnumeratorCancellationAttribute?dipslayProperty=nameWithType>-Attribut bewirkt, dass der Compiler Code für <xref:System.Collections.Generic.IAsyncEnumerator%601> generiert, der dazu führt, dass das an `GetAsyncEnumerator` übergebene Token für den Text des asynchronen Iterators als dieses Argument sichtbar ist. In `runQueryAsync` können Sie den Status des Tokens überprüfen und sich ggf. weitere Arbeit sparen.

Eine andere Erweiterungsmethode (<xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.WithCancellation%2A>) wird verwendet, um das Abbruchtoken an den asynchronen Stream zu übergeben. Ändern Sie die Schleife, die die Issues enumeriert, folgendermaßen:

:::code language="csharp" source="snippets/generate-consume-asynchronous-streams/finished/Program.cs" id="SnippetEnumerateWithCancellation" :::

Sie können den Code für das abgeschlossene Tutorial aus dem Repository [dotnet/docs](https://github.com/dotnet/docs) im Ordner [csharp/tutorials/AsyncStreams](https://github.com/dotnet/docs/tree/master/csharp/tutorials/snippets/generate-consume-asynchronous-streams/finished) abrufen.

## <a name="run-the-finished-application"></a>Ausführen der fertig gestellten Anwendung

Führen Sie die Anwendung erneut aus. Vergleichen Sie deren Verhalten mit dem Verhalten der Startanwendung. Die erste Seite mit Ergebnissen wird aufgelistet, sobald sie verfügbar ist. Es gibt eine wahrnehmbare Pause, wenn eine neue Seite angefordert und abgerufen wird, und dann werden die Ergebnisse der nächsten Seite schnell aufgelistet. Der `try` / `catch`-Block ist zur Verarbeitung eines Abbruchs nicht erforderlich: Der Aufrufer kann das Auflisten der Sammlung beenden. Der Fortschritt wird deutlich gemeldet, weil der asynchrone Datenstrom die Ergebnisse generiert, während die einzelnen Seiten heruntergeladen werden. Der Status jedes zurückgegebenen Problems ist nahtlos in der `await foreach`-Schleife enthalten. Sie benötigen kein Rückrufobjekt, um den Fortschritt nachzuverfolgen.

Sie können Verbesserungen in der Arbeitsspeichernutzung erkennen, indem Sie den Code untersuchen. Sie müssen eine Sammlung nicht mehr zuordnen, um alle Ergebnisse zu speichern, bevor sie aufgelistet werden. Der Aufrufer kann festlegen, wie die Ergebnisse genutzt werden und ob eine Speichersammlung erforderlich ist.

Führen Sie sowohl die Startanwendung als auch die fertig gestellte Anwendung aus, um die Unterschiede zwischen den Implementierungen selbst zu beobachten. Wenn Sie fertig sind, können Sie das zu Beginn des Tutorials erstellte GitHub-Zugriffstoken löschen. Wenn ein Angreifer Zugriff auf dieses Token erlangt hat, kann er mit Ihren Anmeldeinformationen auf GitHub-APIs zugreifen.
