---
title: Generieren und Nutzen asynchroner Datenströme
description: In diesem fortgeschrittenen Tutorial werden Szenarien dargestellt, in denen das Generieren und Nutzen asynchroner Datenströme eine natürlichere Möglichkeit zur Arbeit mit Datensequenzen bietet, die asynchron generiert werden können.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: de090eb9cc1e8b511956313ab5169ee4d07a492f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156739"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a>Tutorial: Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0

In C# 8.0 werden **asynchrone Datenströme** eingeführt. Diese modellieren eine Datenstromquelle, wenn die Elemente im Datenstrom asynchron abgerufen oder generiert werden können. Asynchrone Datenströme beruhen auf Schnittstellen, die in .NET Standard 2.1 neu eingeführt und in .NET Core 3.0 implementiert wurden, um ein natürliches Programmiermodell für Datenquellen für asynchrone Datenströme bereitzustellen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Erstellen einer Datenquelle, die eine Sequenz von Datenelementen asynchron generiert
> - Asynchrones Nutzen dieser Datenquelle
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

Sie können den Code für die in diesem Tutorial verwendete Startanwendung aus unserem Repository [dotnet/samples](https://github.com/dotnet/samples) im Ordner [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) abrufen.

Die Startanwendung ist eine Konsolenanwendung, die die [GitHub GraphQL](https://developer.github.com/v4/)-Schnittstelle zum Abrufen aktueller Issues verwendet, die in das Repository [dotnet/docs](https://github.com/dotnet/docs) geschrieben wurden. Sehen Sie sich zunächst folgenden Code für die `Main`-Methode der Starter-App an:

[!code-csharp[StarterAppMain](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

Sie können entweder eine `GitHubKey`-Umgebungsvariable auf Ihr persönliches Zugriffstoken festlegen, oder Sie können das letzte Argument im Aufruf von `GenEnvVariable` durch Ihr persönliches Zugriffstoken ersetzen. Schließen Sie Ihren Zugriffscode nicht im Quellcode ein, wenn Sie die Quelle zusammen mit anderen nutzen oder in einem Repository mit gemeinsamer Quelle ablegen.

Nach dem Erstellen des GitHub-Clients werden durch den Code in `Main` ein Objekt für Fortschrittsberichte und ein Abbruchtoken erstellt. Nachdem die Objekte erstellt wurden, wird `runPagedQueryAsync` durch `Main` aufgerufen, um die neuesten 250 Issues abzurufen. Nach Abschluss dieser Aufgabe werden die Ergebnisse angezeigt.

Bei Ausführung der Startanwendung können Sie einige wichtige Details zur Ausführung dieser Anwendung beobachten.  Für jede von GitHub zurückgegebene Seite wird der Fortschritt gemeldet. Sie können eine deutliche Pause beobachten, bevor GitHub eine weitere neue Seite mit Issues zurückgibt. Die Issues werden erst angezeigt, nachdem alle zehn Seiten aus GitHub abgerufen wurden.

## <a name="examine-the-implementation"></a>Untersuchen der Implementierung

Die Implementierung zeigt, warum Sie das im vorherigen Abschnitt beschriebene Verhalten beobachten konnten. Untersuchen Sie den Code für `runPagedQueryAsync`:

[!code-csharp[RunPagedQueryStarter](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

Konzentrieren wir uns auf den Paginierungsalgorithmus und die asynchrone Struktur des obigen Codes. (Details zur GitHub GraphQL-API finden Sie in der [GitHub GraphQL-Dokumentation](https://developer.github.com/v4/guides/).) Die `runPagedQueryAsync`-Methode listet die Issues vom neuesten zum ältesten auf. Sie fordert 25 Issues pro Seite an und untersucht die `pageInfo`-Struktur der Antwort, um mit der vorherigen Seite fortzufahren. Dies entspricht der GraphQL-Standardpaginierungsunterstützung für mehrseitige Antworten. Die Antwort enthält ein `pageInfo`-Objekt mit einem `hasPreviousPages`-Wert und einem `startCursor`-Wert zum Anfordern der vorherigen Seite. Die Issues befinden sich im `nodes`-Array. Die `runPagedQueryAsync`-Methode fügt diese Knoten einem Array an, das alle Ergebnisse aus allen Seiten enthält.

Nach dem Abrufen und Wiederherstellen einer Seite mit Ergebnissen meldet `runPagedQueryAsync` den Fortschritt und prüft auf Abbruch. Wenn ein Abbruch angefordert wurde, löst `runPagedQueryAsync` eine <xref:System.OperationCanceledException> aus.

Es gibt mehrere Elemente in diesem Code, die verbessert werden können. Vor allem muss `runPagedQueryAsync` Speicherplatz für alle zurückgegebenen Issues zuordnen. In diesem Beispiel wird der Vorgang bei 250 Issues beendet, weil das Abrufen aller offenen Issues wesentlich mehr Arbeitsspeicher zum Speichern aller abgerufenen Issues erfordern würde. Zudem ist der Algorithmus durch die Protokolle zur Unterstützung von Fortschritt und Abbruch beim ersten Lesen schwieriger zu verstehen. Sie müssen die Fortschrittsklasse suchen, um herauszufinden, wo der Fortschritt gemeldet wird. Außerdem müssen Sie die Kommunikation über die <xref:System.Threading.CancellationTokenSource> und das zugehörige <xref:System.Threading.CancellationToken> verfolgen, um nachzuvollziehen, wo der Abbruch angefordert und wo er gewährt wird.

## <a name="async-streams-provide-a-better-way"></a>Bessere Möglichkeiten durch asynchrone Datenströme

Mit asynchronen Datenströmen und der zugehörigen Sprachunterstützung lassen sich diese Probleme beheben. Der Code, der die Sequenz generiert, kann mit `yield return` jetzt Elemente in einer Methode zurückgeben, die mit dem `async`-Modifizierer deklariert wurde. Sie können einen asynchronen Datenstrom mit einer `await foreach`-Schleife genau so nutzen, wie Sie eine beliebige Sequenz mit einer `foreach`-Schleife einsetzen.

Diese neuen Sprachfeatures hängen von drei neuen Schnittstellen ab, die dem .NET Standard 2.1 hinzugefügt und in .NET Core 3.0 implementiert wurden:

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

Diese drei Schnittstellen sollten den meisten C#-Entwicklern vertraut sein. Sie verhalten sich ähnlich wie ihre synchronen Gegenstücke:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

Ein möglicherweise weniger bekannter Typ ist <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>. Die `ValueTask`-Struktur bietet eine ähnliche API für die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse. `ValueTask` wird in diesen Schnittstellen aus Leistungsgründen verwendet.

## <a name="convert-to-async-streams"></a>Konvertieren in asynchrone Datenströme

Als Nächstes konvertieren Sie die `runPagedQueryAsync`-Methode, um einen asynchronen Datenstrom zu generieren. Ändern Sie zunächst die Signatur von `runPagedQueryAsync` so, dass ein `IAsyncEnumerable<JToken>` zurückgegeben wird, und entfernen Sie das Abbruchtoken und die Fortschrittsobjekte aus der Parameterliste, wie im folgenden Code gezeigt:

[!code-csharp[FinishedSignature](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

Der Startcode verarbeitet die einzelnen Seiten, während sie abgerufen werden, wie im folgenden Code gezeigt:

[!code-csharp[StarterPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

Ersetzen Sie diese drei Zeilen durch den folgenden Code:

[!code-csharp[FinishedPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

Sie können auch die Deklaration von `finalResults` weiter oben in dieser Methode sowie die `return`-Anweisung entfernen, die der von Ihnen geänderten Schleife folgt.

Sie haben die Änderungen zum Generieren eines asynchronen Datenstroms abgeschlossen. Die endgültige Methode sollte dem folgenden Code entsprechen:

[!code-csharp[FinishedGenerate](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

Als Nächstes ändern Sie den Code, der die Sammlung nutzt, um den asynchronen Datenstrom zu verwenden. Suchen Sie in `Main` den folgenden Code, der die Sammlung der Issues verarbeitet:

[!code-csharp[EnumerateOldStyle](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

Ersetzen Sie den Code durch die folgende `await foreach`-Schleife:

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

Standardmäßig werden Streamelemente im erfassten Kontext verarbeitet. Wenn Sie die Erfassung des Kontexts deaktivieren möchten, verwenden Sie die Erweiterungsmethode <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Weitere Informationen über Synchronisierungskontexte und die Erfassung des aktuellen Kontexts finden Sie im Artikel über das [Verwenden des aufgabenbasierten asynchronen Musters](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

Sie können den Code für das abgeschlossene Tutorial aus dem Repository [dotnet/samples](https://github.com/dotnet/samples) im Ordner [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) abrufen.

## <a name="run-the-finished-application"></a>Ausführen der fertig gestellten Anwendung

Führen Sie die Anwendung erneut aus. Vergleichen Sie deren Verhalten mit dem Verhalten der Startanwendung. Die erste Seite mit Ergebnissen wird aufgelistet, sobald sie verfügbar ist. Es gibt eine wahrnehmbare Pause, wenn eine neue Seite angefordert und abgerufen wird, und dann werden die Ergebnisse der nächsten Seite schnell aufgelistet. Der `try` / `catch`-Block ist zur Verarbeitung eines Abbruchs nicht erforderlich: Der Aufrufer kann das Auflisten der Sammlung beenden. Der Fortschritt wird deutlich gemeldet, weil der asynchrone Datenstrom die Ergebnisse generiert, während die einzelnen Seiten heruntergeladen werden. Der Status jedes zurückgegebenen Problems ist nahtlos in der `await foreach`-Schleife enthalten. Sie benötigen kein Rückrufobjekt, um den Fortschritt nachzuverfolgen.

Sie können Verbesserungen in der Arbeitsspeichernutzung erkennen, indem Sie den Code untersuchen. Sie müssen eine Sammlung nicht mehr zuordnen, um alle Ergebnisse zu speichern, bevor sie aufgelistet werden. Der Aufrufer kann festlegen, wie die Ergebnisse genutzt werden und ob eine Speichersammlung erforderlich ist.

Führen Sie sowohl die Startanwendung als auch die fertig gestellte Anwendung aus, um die Unterschiede zwischen den Implementierungen selbst zu beobachten. Wenn Sie fertig sind, können Sie das zu Beginn des Tutorials erstellte GitHub-Zugriffstoken löschen. Wenn ein Angreifer Zugriff auf dieses Token erlangt hat, kann er mit Ihren Anmeldeinformationen auf GitHub-APIs zugreifen.
