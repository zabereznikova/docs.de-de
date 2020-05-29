---
title: Erstellen eines REST-Clients mithilfe von .NET Core
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 4a3a76d1ec9893c2c3e0353e305a19e59c586fe5
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420382"
---
# <a name="rest-client"></a>REST-Client

In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen. Es werden die folgenden Themen abgedeckt:

* Die Grundlagen zur .NET Core-CLI
* Eine Übersicht über die Features der Sprache C#
* Verwalten von Abhängigkeiten mit NuGet
* HTTP-Kommunikation
* Verarbeiten von JSON-Informationen
* Verwalten der Konfiguration mit Attributen

Sie erstellen eine Anwendung, die HTTP-Anforderungen an einen REST-Dienst in GitHub ausgibt. Sie lesen Informationen im JSON-Format ein und konvertieren das JSON-Paket in C#-Objekte. Abschließend lernen Sie die Arbeit mit C#-Objekten kennen.

In diesem Tutorial werden viele Features abgedeckt. Gehen wir sie einzeln an.

Wenn Sie lieber das [letzte Beispiel](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) für dieses Thema befolgen möchten, können Sie es herunterladen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core-Downloads](https://dotnet.microsoft.com/download). Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.
Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

## <a name="create-the-application"></a>Erstellen der Anwendung

Im ersten Schritt wird eine neue Anwendung erstellt. Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung. Legen Sie das Verzeichnis als aktuelles Verzeichnis fest. Geben Sie den folgenden Befehl in ein Konsolenfenster ein:

```dotnetcli
dotnet new console --name WebApiClient
```

Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt. Der Projektname lautet „WebApiClient“. Da es sich hier um ein neues Projekt handelt, ist keine der Abhängigkeiten vorhanden. Mit der ersten Ausführung wird das .NET Core-Framework heruntergeladen, ein Entwicklungszertifikat installiert und der NuGet-Paket-Manager ausgeführt, um die fehlenden Abhängigkeiten wiederherzustellen.

Bevor Sie beginnen, Änderungen vornehmen, geben Sie `dotnet run` ([siehe Hinweis](#dotnet-restore-note)) zum Ausführen der Anwendung an der Eingabeaufforderung ein. `dotnet run` führt automatisch `dotnet restore` aus, wenn Ihrer Umgebung Abhängigkeiten fehlen. Wenn Ihre Anwendung neu erstellt werden muss, wird auch `dotnet build` ausgeführt.
Nach dem ersten Setup müssen Sie nur dann `dotnet restore` oder `dotnet build` ausführen, wenn es für Ihr Projekt sinnvoll ist.

## <a name="adding-new-dependencies"></a>Hinzufügen von neuen Abhängigkeiten

Eines der wichtigsten Entwurfsziele für .NET Core ist die Minimierung der Größe der .NET-Installation. Wenn eine Anwendung zusätzliche Bibliotheken für bestimmte Features benötigt, fügen Sie diese abhängigen Komponenten Ihrer C#-Projektdatei (\*.csproj) hinzu. Beispielweise müssen Sie das `System.Runtime.Serialization.Json`-Paket hinzufügen, damit Ihre Anwendung JSON-Antworten verarbeiten kann.

Sie benötigen das `System.Runtime.Serialization.Json`-Paket für diese Anwendung. Fügen Sie es Ihrem Projekt hinzu, indem Sie den folgenden [.NET CLI](../../core/tools/dotnet-add-package.md)-Befehl ausführen:

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a>Ausführen von Webanforderungen

Jetzt können Sie damit beginnen, Daten aus dem Web abzurufen. In dieser Anwendung lesen Sie Informationen aus der [GitHub-API](https://developer.github.com/v3/) ein. Beginnen wir damit, Informationen zu den Projekten unterhalb der Kategorie [.NET Foundation](https://www.dotnetfoundation.org/) einzulesen. Hierzu senden Sie zunächst eine Anforderung an die GitHub-API, um Informationen zu den Projekten abzurufen. Der verwendete Endpunkt ist <https://api.github.com/orgs/dotnet/repos>. Sie möchten alle Informationen zu diesen Projekten abrufen, deshalb verwenden Sie eine HTTP GET-Anforderung.
Ihr Browser verwendet ebenfalls HTTP GET-Anforderungen, deshalb können Sie diese URL in Ihren Browser einfügen, um zu sehen, welche Informationen abgerufen und verarbeitet werden.

Sie verwenden die <xref:System.Net.Http.HttpClient> -Klasse zum Ausführen der Webanforderungen. Wie alle modernen .NET-APIs unterstützt <xref:System.Net.Http.HttpClient> nur asynchrone Methoden für APIs mit langer Ausführungszeit.
Sie beginnen mit dem Erstellen einer asynchronen Methode. Sie vervollständigen die Implementierung, wenn Sie die Funktionalität der Anwendung erstellen. Öffnen Sie zunächst die Datei `program.cs` in Ihrem Projektverzeichnis, und fügen Sie der `Program`-Klasse die folgende Methode hinzu:

```csharp
private static async Task ProcessRepositories()
{
}
```

Sie müssen am Anfang Ihrer `Main`-Methode eine `using`-Anweisung hinzufügen, damit der C#-Compiler den <xref:System.Threading.Tasks.Task>-Typ erkennt:

```csharp
using System.Threading.Tasks;
```

Wenn Sie zu diesem Zeitpunkt Ihr Projekt erstellen, erhalten Sie eine Warnung für diese Methode, weil sie keine `await`-Operatoren enthält und synchron ausgeführt wird. Ignorieren Sie dies für den Moment. Sie fügen `await`-Operatoren hinzu, wenn Sie die Methode vervollständigen.

Aktualisieren Sie als Nächstes die Methode `Main`, um die Methode `ProcessRepositories` aufzurufen. Die `ProcessRepositories`-Methode gibt einen Task zurück. Sie dürfen das Programm nicht beenden, bevor dieser Task abgeschlossen wurde. Daher müssen Sie die Signatur von `Main` ändern. Fügen Sie den `async`-Modifizierer hinzu, und ändern Sie den Rückgabetyp in `Task`. Fügen Sie dann im Textkörper der Methode einen Aufruf von `ProcessRepositories`hinzu. Fügen Sie diesem Methodenaufruf das Schlüsselwort `await` hinzu:

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

Sie verfügen jetzt über ein Programm, das keinerlei Vorgänge ausführt, aber asynchron arbeitet. Es gibt aber noch Raum zur Verbesserung.

Zunächst benötigen Sie ein Objekt, das dazu fähig ist, Daten aus dem Web abzurufen. Hierfür können Sie <xref:System.Net.Http.HttpClient> verwenden. Dieses Objekt verarbeitet die Anforderung und die Antworten. Instanziieren Sie eine einzelne Instanz dieses Typs in der Klasse `Program` innerhalb der Datei *Program.cs*.

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

Kehren wir zur `ProcessRepositories`-Methode zurück und erstellen eine erste Version der Methode:

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

Damit eine Kompilierung möglich ist, müssen Sie am Anfang der Datei außerdem zwei neue `using`-Anweisungen hinzufügen:

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

Diese erste Version führt eine Webanforderung aus, um die Liste aller Repositorys unterhalb der dotnet foundation-Organisation einzulesen. (Die GitHub-ID für die .NET Foundation lautet „dotnet“.) In den ersten Zeilen wird <xref:System.Net.Http.HttpClient> für diese Anforderung eingerichtet. Zunächst wird der HttpClient so konfiguriert, dass er die GitHub-JSON-Antworten akzeptiert.
Das Format ist einfach JSON. In der nächsten Zeile wird ein Benutzer-Agent-Header für alle Anforderungen von diesem Objekt hinzugefügt. Diese zwei Header werden vom GitHub-Servercode überprüft und sind erforderlich, um Informationen aus GitHub abzurufen.

Nachdem Sie den <xref:System.Net.Http.HttpClient> konfiguriert haben, führen Sie eine Webanforderung aus und rufen die Antwort ab. In dieser ersten Version verwenden Sie die bequeme <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>-Methode. Diese Hilfsmethode startet einen Task zum Ausführen der Webanforderung. Wenn die Anforderung zurückgegeben wird, liest sie den Antwortstream und extrahiert den Inhalt aus dem Stream. Der Antwortkörper wird als <xref:System.String> zurückgegeben. Die Zeichenfolge ist verfügbar, wenn der Task abgeschlossen wurde.

Die letzten zwei Zeilen dieser Methode warten auf den Task und geben dann die Antwort an die Konsole aus.
Erstellen Sie die App, und führen Sie sie aus. Die Buildwarnung wird jetzt nicht mehr angezeigt, weil `ProcessRepositories` jetzt einen `await`-Operator enthält. Sie sehen eine umfangreiche Textanzeige im JSON-Format.

## <a name="processing-the-json-result"></a>Verarbeiten des JSON-Ergebnisses

Zu diesem Zeitpunkt haben Sie Code geschrieben, mit dem eine Antwort von einem Webserver abgerufen und der Text angezeigt wird, der in dieser Antwort enthalten ist. Konvertieren wir jetzt diese JSON-Antwort in C#-Objekte.

Die <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType>-Klasse serialisiert Objekte in JSON und deserialisiert JSON in-Objekte. Definieren Sie zunächst eine Klasse, die das `repo`-JSON-Objekt darstellt, das von der GitHub-API zurückgegeben wird:

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

Platzieren Sie den obigen Code in einer neuen Datei namens „repo.cs“. Diese Version der Klasse repräsentiert die einfachste Möglichkeit zum Verarbeiten von JSON-Daten. Der Klassenname und der Membername stimmen mit den im JSON-Paket verwendeten Namen überein, statt den C#-Konventionen zu folgen. Sie beheben dies später, indem Sie einige Konfigurationsattribute angeben. Diese Klasse veranschaulicht ein weiteres wichtiges Feature der JSON-Serialisierung und -Deserialisierung: Nicht alle Felder im JSON-Paket sind Teil dieser Klasse.
Das JSON-Serialisierungsprogramm ignoriert Informationen, die nicht im verwendeten Klassentyp enthalten sind.
Dieses Feature vereinfacht es, Typen zu erstellen, die nur mit einem Teilsatz der Felder im JSON-Paket funktionieren.

Nun, da Sie den Typ erstellt haben, deserialisieren wir ihn.

Als Nächstes verwenden Sie das Serialisierungsprogramm, um JSON-Daten in C#-Objekte zu konvertieren. Ersetzen Sie den Aufruf von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in Ihrer `ProcessRepositories`-Methode durch die folgenden Zeilen:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

Sie verwenden neue Namespaces, sodass Sie diesen ebenfalls am Anfang der Datei hinzufügen müssen:

```csharp
using System.Collections.Generic;
using System.Text.Json;
```

Beachten Sie, dass Sie jetzt <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anstelle von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> verwenden. Das Serialisierungsprogramm verwendet anstelle einer Zeichenfolge einen Stream als Quelle. Erläutern wir einige Features von C#, die in der zweiten Zeile des Codeausschnitts oben verwendet werden. Das erste Argument für <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> ist ein `await`-Ausdruck. (Die anderen beiden Parameter sind optional und werden im Codeausschnitt ausgelassen.) Await-Ausdrücke können fast überall in Ihrem Code auftauchen, auch wenn sie bisher nur als Teil einer Zuweisungsanweisung verwendet wurden. Die `Deserialize`-Methode ist *generisch*. Dies bedeutet, dass Sie Typargumente für die Art von Objekten angeben müssen, die aus dem JSON-Text erstellt werden sollen. In diesem Beispiel deserialisieren Sie in ein `List<Repository>`, bei dem es sich um ein weiteres generisches Objekt handelt, das <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Objekt. Die `List<>`-Klasse speichert eine Sammlung von Objekten. Das Typargument deklariert den Typ der in `List<>` gespeicherten Objekte. Der JSON-Text stellt eine Sammlung von Repositoryobjekten dar, sodass das Typargument `Repository` ist.

Dieser Abschnitt ist fast fertig. Nachdem Sie nun die JSON-Daten in C#-Objekte konvertiert haben, lassen Sie uns den Namen jedes Repositorys anzeigen. Ersetzen Sie diese Zeilen:

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

...durch die folgenden:

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

Kompilieren Sie die Anwendung, und führen Sie sie aus. Die Anwendung gibt die Namen der Repositorys aus, die Teil der .NET Foundation sind.

## <a name="controlling-serialization"></a>Steuern der Serialisierung

Bevor Sie weitere Features hinzufügen, wenden wir uns der `name`-Eigenschaft mithilfe des `[JsonPropertyName]`-Attributs zu. Ändern Sie die Deklaration des `name`-Felds in „repo.cs“ folgendermaßen ab:

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

Um das `[JsonPropertyName]`-Attribut verwenden zu können, müssen Sie den <xref:System.Text.Json.Serialization>-Namespace zu den `using`-Anweisungen hinzufügen:

```csharp
using System.Text.Json.Serialization;
```

Diese Änderung bedeutet, dass Sie den Code ändern müssen, mit dem der Name jedes Repositorys in „program.cs“ geschrieben wird:

```csharp
Console.WriteLine(repo.Name);
```

Führen Sie `dotnet run` aus, um sicherzustellen, dass die Zuordnungen richtig sind. Es sollte dieselbe Ausgabe angezeigt werden wie zuvor.

Führen wir eine weitere Änderung durch, bevor wir neue Features hinzufügen. Die `ProcessRepositories`-Methode kann die asynchrone Arbeit erledigen und eine Auflistung der Repositorys zurückgeben. Geben wir die `List<Repository>` über diese Methode zurück, und verschieben wir den Code zum Schreiben dieser Informationen in die `Main`-Methode.

Ändern Sie die Signatur von `ProcessRepositories`, um einen Task zurückzugeben, dessen Ergebnis eine Liste mit `Repository`-Objekten ist:

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

Geben Sie anschließend einfach die Repositorys zurück, nachdem die JSON-Antwort verarbeitet wurde:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

Der Compiler generiert das `Task<T>`-Objekt für die Rückgabe, weil Sie diese Methode als `async` markiert haben.
Ändern wir dann die `Main`-Methode, sodass sie diese Ergebnisse erfasst und den Namen jedes Repositorys an die Konsole schreibt. Ihre `Main`-Methode sieht nun folgendermaßen aus:

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a>Einlesen weiterer Informationen

Zum Abschluss verarbeiten wir einige weitere Eigenschaften im JSON-Paket, das von der GitHub-API gesendet wird. Sie müssen nicht alle Informationen abrufen, aber das Hinzufügen einiger Eigenschaften veranschaulicht einige weitere Features von C#.

Beginnen wir damit, ein paar weitere einfache Typen in die Definition der `Repository`-Klasse einzufügen. Fügen Sie diese Eigenschaften zu dieser Klasse hinzu:

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

Diese Eigenschaften verfügen über integrierte Konvertierungen vom Zeichenfolgentyp (dieser ist in den JSON-Paketen enthalten) in den Zieltyp. Der <xref:System.Uri> -Typ ist Ihnen möglicherweise neu. Er repräsentiert einen URI, oder in diesem Fall eine URL. Im Fall der `Uri`- und `int`-Typen wird über die Serialisierungsaktion eine Ausnahme ausgelöst, wenn das JSON-Paket Daten enthält, die nicht in den Zieltyp konvertiert werden können.

Aktualisieren Sie nach dem Hinzufügen die `Main`-Methode, um diese Elemente anzuzeigen:

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

Im letzten Schritt fügen wir jetzt die Informationen für den letzten Pushvorgang hinzu. Diese Informationen werden in der JSON-Antwort folgendermaßen formatiert:

```json
2016-02-08T21:27:00Z
```

Dieses Format verwendet die koordinierte Weltzeit (UTC), sodass Sie einen <xref:System.DateTime>-Wert erhalten, dessen <xref:System.DateTime.Kind%2A>-Eigenschaft <xref:System.DateTimeKind.Utc> lautet. Wenn Sie ein Datum in Ihrer Ortszeit bevorzugen, müssen Sie eine benutzerdefinierte Methode für die Konvertierung schreiben. Definieren Sie zunächst eine `public`-Eigenschaft, die die UTC-Darstellung von Datum und Uhrzeit in Ihrer `Repository`-Klasse enthält, und eine `LastPush` `readonly`-Eigenschaft, die das konvertierte Datum in Ortszeit zurückgibt:

```csharp
[JsonPropertyName("pushed_at")]
public DateTime LastPushUtc { get; set; }

public DateTime LastPush => LastPushUtc.ToLocalTime();
```

Gehen wir die soeben definierten neuen Konstrukte einzeln durch. Die `LastPush`-Eigenschaft wird mit einem *Ausdruckskörpermember* für die `get`-Zugriffsmethode definiert. Es ist kein `set`-Accessor vorhanden. Durch Auslassen der `set`-Zugriffsmethode definieren Sie eine *schreibgeschützte* Eigenschaft in C#. (Ja, Sie können *lesegeschützte* Eigenschaften in C# erstellen, aber ihr Wert ist begrenzt.)

Abschließend fügen Sie eine weitere Ausgabeanweisung in der Konsole hinzu. Jetzt können Sie diese Anwendung erstellen und erneut ausführen:

```csharp
Console.WriteLine(repo.LastPush);
```

Ihre Version sollte nun der [abgeschlossenen Version](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) entsprechen.

## <a name="conclusion"></a>Schlussbemerkung

In diesem Tutorial wurde gezeigt, wie Sie Webanforderungen ausführen, das Ergebnis analysieren und Eigenschaften dieser Ergebnisse anzeigen. Sie haben außerdem neue Pakete als abhängige Komponenten in Ihr Projekt eingefügt. Sie haben einige der Features von C# kennengelernt, die objektorientierte Verfahren unterstützen.

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
