---
title: Erstellen eines REST-Clients mithilfe von .NET Core
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: bc3c23b277b233efba9f32cc49b29ac905f3abc8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480155"
---
# <a name="rest-client"></a>REST-Client

## <a name="introduction"></a>Einführung
In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen. Es werden die folgenden Themen abgedeckt:
*   Grundlagen der .NET Core-Befehlszeilenschnittstelle (CLI)
*   Eine Übersicht über die Features der Sprache C#
*   Verwalten von Abhängigkeiten mit NuGet
*   HTTP-Kommunikation
*   Verarbeiten von JSON-Informationen
*   Verwalten der Konfiguration mit Attributen 

Sie erstellen eine Anwendung, die HTTP-Anforderungen an einen REST-Dienst in GitHub ausgibt. Sie lesen Informationen im JSON-Format ein und konvertieren das JSON-Paket in C#-Objekte. Abschließend lernen Sie die Arbeit mit C#-Objekten kennen.

In diesem Tutorial werden viele Features abgedeckt. Gehen wir sie einzeln an.

Wenn Sie lieber das [letzte Beispiel](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) für dieses Thema befolgen möchten, können Sie es herunterladen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Erforderliche Komponenten
Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core). Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen. Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.
## <a name="create-the-application"></a>Erstellen der Anwendung
Im ersten Schritt wird eine neue Anwendung erstellt. Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung. Legen Sie das Verzeichnis als aktuelles Verzeichnis fest. Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein. Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.

Bevor Sie damit beginnen, Änderungen durchzuführen, gehen wir die Schritte zur Ausführung der einfachen Hello World-Anwendung durch. Geben Sie nach dem Erstellen der Anwendung den Befehl `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) bei Eingabeaufforderung ein. Mit diesem Befehl wird der Prozess zur NuGet-Paketwiederherstellung ausgeführt. NuGet ist ein .NET-Paket-Manager. Mit diesem Befehl werden alle fehlenden abhängigen Komponenten für Ihr Projekt heruntergeladen. Da es sich um ein neues Projekt handelt, ist keine der abhängigen Komponenten vorhanden, deshalb wird zunächst das .NET Core-Framework heruntergeladen. Nach diesem ersten Schritt müssen Sie `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) nur ausführen, wenn Sie neue abhängige Pakete hinzufügen oder die Versionen abhängiger Komponenten aktualisieren.  

Nach dem Wiederherstellen der Pakete führen Sie `dotnet build` aus. Hiermit wird die Build-Engine ausgeführt und Ihre Anwendung erstellt. Abschließend führen Sie `dotnet run` aus, um Ihre Anwendung zu starten.

## <a name="adding-new-dependencies"></a>Hinzufügen von neuen Abhängigkeiten
Eines der wichtigsten Entwurfsziele für .NET Core ist die Minimierung der Größe der .NET Framework-Installation. Das .NET Core-Anwendungsframework enthält nur die am häufigsten verwendeten Elemente der vollständigen .NET Framework-Version. Wenn eine Anwendung zusätzliche Bibliotheken für bestimmte Features benötigt, fügen Sie diese abhängigen Komponenten Ihrer C#-Projektdatei (\*.csproj) hinzu. Beispielweise müssen Sie das `System.Runtime.Serialization.Json`-Paket hinzufügen, damit Ihre Anwendung JSON-Antworten verarbeiten kann.

Öffnen Sie Ihre `csproj`-Projektdatei. Die erste Zeile der Datei sollte so aussehen:

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

Fügen Sie direkt nach dieser Zeile Folgendes ein: 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
Die meisten Code-Editoren bieten Codevervollständigung für verschiedene Versionen dieser Bibliotheken. Sie werden in der Regel die neueste Version der hinzugefügten Pakete verwenden. Es ist jedoch wichtig, sicherzustellen, dass die Versionen aller Pakete übereinstimmen und auch der Version des .NET Core-Anwendungsframeworks entsprechen.

Nachdem Sie diese Änderungen durchgeführt haben, sollten Sie erneut `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) ausführen, damit das Paket auf Ihrem System installiert wird.

## <a name="making-web-requests"></a>Ausführen von Webanforderungen
Jetzt können Sie damit beginnen, Daten aus dem Web abzurufen. In dieser Anwendung lesen Sie Informationen aus der [GitHub-API](https://developer.github.com/v3/) ein. Beginnen wir damit, Informationen zu den Projekten unterhalb der Kategorie [.NET Foundation](http://www.dotnetfoundation.org/) einzulesen. Hierzu senden Sie zunächst eine Anforderung an die GitHub-API, um Informationen zu den Projekten abzurufen. Der verwendete Endpunkt ist [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos). Sie möchten alle Informationen zu diesen Projekten abrufen, deshalb verwenden Sie eine HTTP GET-Anforderung.
Ihr Browser verwendet ebenfalls HTTP GET-Anforderungen, deshalb können Sie diese URL in Ihren Browser einfügen, um zu sehen, welche Informationen abgerufen und verarbeitet werden.

Sie verwenden die <xref:System.Net.Http.HttpClient> -Klasse zum Ausführen der Webanforderungen. Wie alle modernen .NET-APIs unterstützt <xref:System.Net.Http.HttpClient> nur asynchrone Methoden für APIs mit langer Ausführungszeit.
Sie beginnen mit dem Erstellen einer asynchronen Methode. Sie vervollständigen die Implementierung, wenn Sie die Funktionalität der Anwendung erstellen. Öffnen Sie zunächst die Datei `program.cs` in Ihrem Projektverzeichnis, und fügen Sie der `Program`-Klasse die folgende Methode hinzu:

```csharp
private static async Task ProcessRepositories()
{
    
}
```

Sie müssen am Anfang Ihrer `Main`-Methode eine `using`-Anweisung hinzufügen, damit der C#-Compiler den <xref:System.Threading.Tasks.Task> -Typ erkennt:

```csharp
using System.Threading.Tasks;
```

Wenn Sie zu diesem Zeitpunkt Ihr Projekt erstellen, erhalten Sie eine Warnung für diese Methode, weil sie keine `await`-Operatoren enthält und synchron ausgeführt wird. Ignorieren Sie dies für den Moment. Sie fügen `await`-Operatoren hinzu, wenn Sie die Methode vervollständigen.

Als Nächstes benennen Sie den in der `namespace`-Anweisung definierten Namespace vom Standardwert `ConsoleApp` in `WebAPIClient` um. Später definieren wir eine `repo`-Klasse in diesem Namespace.

Aktualisieren Sie jetzt die `Main`-Methode, um diese Methode aufzurufen. Die `ProcessRepositories`-Methode gibt einen Task zurück, und Sie dürfen das Programm nicht beenden, bevor dieser Task abgeschlossen wurde. Deshalb müssen Sie die `Wait` -Methode verwenden, um eine Blockierung einzurichten und auf den Abschluss des Tasks zu warten:

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

Sie verfügen jetzt über ein Programm, das keinerlei Vorgänge ausführt, aber asynchron arbeitet. Es gibt aber noch Raum zur Verbesserung.

Zunächst benötigen Sie ein Objekt, das dazu fähig ist, Daten aus dem Web abzurufen. Hierfür können Sie <xref:System.Net.Http.HttpClient> verwenden. Dieses Objekt verarbeitet die Anforderung und die Antworten. Instanziieren Sie eine einzelne Instanz dieses Typs in der Klasse `Program` innerhalb der Datei „Program.cs“.

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
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

Damit eine Kompilierung möglich ist, müssen Sie am Anfang der Datei außerdem zwei neue using-Anweisungen hinzufügen:

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

Das JSON-Serialisierungsprogramm konvertiert JSON-Daten in C#-Objekte. Ihre erste Aufgabe ist es, einen C#-Klassentyp zur Aufnahme der Informationen zu definieren, die Sie aus dieser Antwort verwenden. Gehen wir langsam vor und beginnen mit einem einfachen C#-Typ, der den Namen des Repositorys enthält:

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

Platzieren Sie den obigen Code in einer neuen Datei namens „repo.cs“. Diese Version der Klasse repräsentiert die einfachste Möglichkeit zum Verarbeiten von JSON-Daten. Der Klassenname und der Membername stimmen mit den im JSON-Paket verwendeten Namen überein, statt den C#-Konventionen zu folgen. Sie beheben dies später, indem Sie einige Konfigurationsattribute angeben. Diese Klasse veranschaulicht ein weiteres wichtiges Feature der JSON-Serialisierung und -Deserialisierung: Nicht alle Felder im JSON-Paket sind Teil dieser Klasse.
Das JSON-Serialisierungsprogramm ignoriert Informationen, die nicht im verwendeten Klassentyp enthalten sind.
Dieses Feature vereinfacht es, Typen zu erstellen, die nur mit einem Teilsatz der Felder im JSON-Paket funktionieren.

Nun, da Sie den Typ erstellt haben, deserialisieren wir ihn. Sie müssen ein <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> -Objekt erstellen. Dieses Objekt muss den CLR-Typ kennen, der für das abgerufene JSON-Paket erwartet wird. Das Paket aus GitHub enthält eine Sequenz aus Repositorys, deshalb ist `List<repo>` der richtige Typ. Fügen Sie Ihrer `ProcessRepositories`-Methode die folgende Zeile hinzu:

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

Sie verwenden jetzt zwei neue Namespaces, deshalb müssen Sie diese auch hinzufügen:

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

Als Nächstes verwenden Sie das Serialisierungsprogramm, um JSON-Daten in C#-Objekte zu konvertieren. Ersetzen Sie den Aufruf von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in Ihrer `ProcessRepositories`-Methode durch die folgenden zwei Zeilen:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

Beachten Sie, dass Sie jetzt <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anstelle von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> verwenden. Das Serialisierungsprogramm verwendet anstelle einer Zeichenfolge einen Stream als Quelle. Erläutern wir einige Features von C#, die oben in der zweiten Zeile verwendet werden. Das Argument für <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> ist ein `await`-Ausdruck. Await-Ausdrücke können fast überall in Ihrem Code auftauchen, auch wenn sie bisher nur als Teil einer Zuweisungsanweisung verwendet wurden.

Zweitens wird der `as`-Operator vom Kompilierzeittyp `object` in `List<repo>` konvertiert. Die Deklaration von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> gibt an, dass ein Objekt vom Typ <xref:System.Object?displayProperty=nameWithType> zurückgegeben wird. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> gibt den Typ zurück, den Sie bei der Erstellung angegeben haben (in diesem Tutorial `List<repo>`). Wenn die Konvertierung nicht erfolgreich ist, wird der `as`-Operator als `null` ausgewertet, statt eine Ausnahme auszulösen.

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

Bevor Sie weitere Features hinzufügen, lassen Sie uns den `repo`-Typ bearbeiten, sodass er eher den Standardkonventionen von C# entspricht. Sie erreichen dies, indem Sie den `repo`-Typ mit *Attributen* versehen, die die Funktionsweise des JSON-Serialisierungsprogramms steuern. In diesem Fall verwenden Sie die Attribute, um eine Zuordnung zwischen den JSON-Schlüsselnamen und den Namen der C#-Klassen und -Members zu definieren. Die zwei verwendeten Attribute sind `DataContract` und `DataMember`. Laut Konvention enden alle Attributklassen auf das Suffix `Attribute`. Sie müssen dieses Suffix jedoch nicht verwenden, wenn Sie ein Attribut anwenden. 

Die Attribute `DataContract` und `DataMember` befinden sich in einer anderen Bibliothek, deshalb müssen Sie Ihrer C#-Projektdatei diese Bibliothek als abhängige Komponente hinzufügen. Fügen Sie dem Abschnitt `<ItemGroup>` Ihrer Projektdatei die folgende Zeile hinzu:

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

Führen Sie nach dem Speichern der Datei `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) aus, um dieses Paket abzurufen.

Öffnen Sie dann die Datei `repo.cs`. Jetzt ändern wir den Namen in die Pascal-Schreibweise und schreiben den Namen `Repository` vollständig aus. JSON-repo-Knoten sollen weiterhin diesem Typ zugeordnet werden, deshalb müssen Sie das `DataContract`-Attribut zur Klassendeklaration hinzufügen. Sie legen die `Name`-Eigenschaft des Attributs auf den Namen der JSON-Knoten fest, die diesem Typ zugeordnet sind:

```csharp
[DataContract(Name="repo")]
public class Repository
```

<xref:System.Runtime.Serialization.DataContractAttribute> ist ein Member des <xref:System.Runtime.Serialization> -Namespace, deshalb müssen Sie oben in der Datei die geeignete `using` -Anweisung hinzufügen:

```csharp
using System.Runtime.Serialization;
```

Sie haben den Namen der `repo`-Klasse in `Repository` geändert, deshalb müssen Sie die gleiche Namensänderung in „Program.cs“ durchführen (einige Editoren unterstützen möglicherweise ein Refactoring mit Umbenennung, wodurch diese Änderung automatisch durchgeführt wird):

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

Führen wir jetzt die gleiche Änderung mit dem `name`-Feld unter Verwendung der <xref:System.Runtime.Serialization.DataMemberAttribute> -Klasse durch. Ändern Sie die Deklaration des `name`-Felds in „repo.cs“ folgendermaßen ab:

```csharp
[DataMember(Name="name")]
public string Name;
```

Diese Änderung bedeutet, dass Sie den Code ändern müssen, mit dem der Name jedes Repositorys in „program.cs“ geschrieben wird:

```csharp
Console.WriteLine(repo.Name);
```

Führen Sie `dotnet build` und anschließend `dotnet run` aus, um sicherzustellen, dass die Zuordnungen korrekt sind. Es sollte dieselbe Ausgabe angezeigt werden wie zuvor. Bevor wir weitere Eigenschaften vom Webserver verarbeiten, lassen Sie uns eine weitere Änderung an der `Repository`-Klasse durchführen. Der `Name`-Member ist ein Feld mit öffentlichem Zugriff. Dies ist keine bewährte Vorgehensweise in der objektorientierten Programmierung, deshalb führen wir eine Änderung in eine Eigenschaft durch. Für unsere Zwecke ist kein spezifischer Code zum Abrufen oder Festlegen der Eigenschaft erforderlich, aber die Änderung in eine Eigenschaft macht es leichter, diese Änderungen später hinzuzufügen, ohne die Lauffähigkeit von Code zu beeinträchtigen, der die `Repository`-Klasse verwendet.

Entfernen Sie die Felddefinition, und ersetzen Sie sie durch eine [automatisch implementierte Eigenschaft](../programming-guide/classes-and-structs/auto-implemented-properties.md):

```csharp
public string Name { get; set; }
```

Der Compiler generiert den Körper der `get`- und `set`-Accessors sowie ein privates Feld zum Speichern des Namens. Dies ähnelt dem folgenden Code, den Sie per Hand eingeben könnten:

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

Führen wir eine weitere Änderung durch, bevor wir neue Features hinzufügen. Die `ProcessRepositories`-Methode kann die asynchrone Arbeit erledigen und eine Auflistung der Repositorys zurückgeben. Geben wir die `List<Repository>` über diese Methode zurück, und verschieben wir den Code zum Schreiben dieser Informationen in die `Main`-Methode.

Ändern Sie die Signatur von `ProcessRepositories`, um einen Task zurückzugeben, dessen Ergebnis eine Liste mit `Repository`-Objekten ist:

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

Geben Sie anschließend einfach die Repositorys zurück, nachdem die JSON-Antwort verarbeitet wurde:

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

Der Compiler generiert das `Task<T>`-Objekt für die Rückgabe, weil Sie diese Methode als `async` markiert haben.
Ändern wir dann die `Main`-Methode, sodass sie diese Ergebnisse erfasst und den Namen jedes Repositorys an die Konsole schreibt. Ihre `Main`-Methode sieht nun folgendermaßen aus:

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

Der Zugriff auf die `Result`-Eigenschaft ist bis zum Abschluss des Tasks blockiert. Normalerweise wäre es vorzuziehen, wie in der `ProcessRepositories`-Methode mit `await` auf den Abschluss des Tasks zu warten, aber das ist in der `Main`-Methode nicht zulässig.

## <a name="reading-more-information"></a>Einlesen weiterer Informationen

Zum Abschluss verarbeiten wir einige weitere Eigenschaften im JSON-Paket, das von der GitHub-API gesendet wird. Sie müssen nicht alle Informationen abrufen, aber das Hinzufügen einiger Eigenschaften veranschaulicht einige weitere Features von C#.

Beginnen wir damit, ein paar weitere einfache Typen in die Definition der `Repository`-Klasse einzufügen. Fügen Sie diese Eigenschaften zu dieser Klasse hinzu:

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
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

Dieses Format entspricht nicht den standardmäßigen .NET-<xref:System.DateTime> -Formaten. Deshalb müssen Sie eine benutzerdefinierte Konvertierungsmethode schreiben. Darüber hinaus möchten Sie wahrscheinlich nicht, dass die unformatierte Zeichenfolge für Benutzer der `Repository`-Klasse verfügbar gemacht wird. Dies kann ebenfalls mithilfe von Attributen gesteuert werden. Definieren Sie zunächst eine `private`-Eigenschaft, die die Zeichenfolgendarstellung des DateTime-Werts in Ihrer `Repository`-Klasse enthält:

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

Das `DataMember`-Attribut informiert das Serialisierungsprogramm, dass eine Verarbeitung durchgeführt werden soll, obwohl es sich nicht um einen öffentlichen Member handelt. Erstellen Sie als Nächstes eine schreibgeschützte öffentliche Eigenschaft, mit der die Zeichenfolge in ein gültiges <xref:System.DateTime>-Objekt konvertiert wird und diesen <xref:System.DateTime>-Wert zurückgibt:

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

Gehen wir die neuen Konstrukte von oben durch. Das `IgnoreDataMember`-Attribut weist das Serialisierungsprogramm an, dass dieser Typ nicht aus einem JSON-Objekt gelesen oder geschrieben werden darf. Diese Eigenschaft enthält nur einen `get`-Accessor. Es ist kein `set`-Accessor vorhanden. So wird eine *schreibgeschützte* Eigenschaft in C# definiert. (Ja, Sie können *lesegeschützte* Eigenschaften in C# erstellen, aber ihr Wert ist begrenzt.) Die <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)>-Methode analysiert eine Zeichenfolge und erstellt ein <xref:System.DateTime>-Objekt mit dem angegebenen Datumsformat. Außerdem werden mit einem `CultureInfo`-Objekt zusätzliche Metadaten zu `DateTime` hinzugefügt. Wenn die Analyse nicht erfolgreich ist, löst der Eigenschaftsaccessor eine Ausnahme aus.

Zur Verwendung von <xref:System.Globalization.CultureInfo.InvariantCulture> müssen Sie den <xref:System.Globalization> -Namespace zu den `using`-Anweisungen in `repo.cs` hinzufügen:

```csharp
using System.Globalization;
```

Abschließend fügen Sie eine weitere Ausgabeanweisung in der Konsole hinzu. Jetzt können Sie diese Anwendung erstellen und erneut ausführen:

```csharp
Console.WriteLine(repo.LastPush);
```

Ihre Version sollte nun der [abgeschlossenen Version](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) entsprechen.
 
## <a name="conclusion"></a>Schlussbemerkung

In diesem Tutorial wurde gezeigt, wie Sie Webanforderungen ausführen, das Ergebnis analysieren und Eigenschaften dieser Ergebnisse anzeigen. Sie haben außerdem neue Pakete als abhängige Komponenten in Ihr Projekt eingefügt. Sie haben einige der Features von C# kennengelernt, die objektorientierte Verfahren unterstützen.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
