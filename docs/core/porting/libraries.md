---
title: "Portieren auf .NET Core – Bibliotheken"
description: "Portieren auf .NET Core – Bibliotheken"
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a0fd860d-d6b6-4659-b325-8a6e6f5fa4a1
translationtype: Human Translation
ms.sourcegitcommit: 46061efa8e33c6a73befa5181eb33b8deb2fa637
ms.openlocfilehash: 503cf3628ee317f701f467bddc4bcb5998b82af4

---

# <a name="porting-to-net-core-libraries"></a>Portieren auf .NET Core – Bibliotheken

Mit dem Release von .NET Core 1.0 gibt es die Möglichkeit, vorhandenen Bibliothekscode zu portieren, sodass er plattformübergreifend ausgeführt werden kann.  Dieser Artikel behandelt die .NET-Standardbibliothek, nicht verfügbare Technologien, wie Sie die kleinere Anzahl der verfügbaren APIS auf .NET Core 1.0 belegen, und wie Sie die Tools verwenden, die mit .NET Core SDK Preview 2 versendet werden, sowie empfohlene Vorgehensweisen zum Portieren Ihres Codes.

Das Portieren dauert möglicherweise eine gewisse Zeit, besonders, wenn Sie über eine große Codebasis verfügen.  Sie sollten auch darauf vorbereitet sein, die hier genannten Empfehlungen soweit anzupassen, dass sie zu Ihrem Code passen.  Jede Codebasis ist anders, daher versucht dieser Artikel die Dinge so flexibel wie möglich zu sehen, jedoch kann es vorkommen, dass Sie sich etwas von den Anweisungen in diesem Artikel entfernen müssen.

## <a name="prerequisites"></a>Erforderliche Komponenten

In diesem Artikel wird davon ausgegangen, dass Sie Visual Studio 2015 oder höher unter Windows verwenden.  Die Bits, die Sie zum Erstellen von .NET Core-Code benötigen, sind nicht in früheren Versionen von Visual Studio verfügbar.

In diesem Artikel wird ebenso vorausgesetzt, dass sie den [empfohlenen Portierungsprozess](index.md) verstehen, und dass Sie die Probleme mit [Abhängigkeiten von Drittanbietern](third-party-deps.md) gelöst haben.

## <a name="targeting-the-net-standard-library"></a>Festlegen der .NET Standardbibliothek als Ziel

Die beste Möglichkeit, eine plattformübergreifende Bibliothek für .NET Core zu erstellen, ist es, die [.NET-Standardbibliothek](../../standard/library.md) als Ziel festzulegen.  Die .NET-Standardbibliothek ist die formale Spezifikation von .NET-APIs, die für alle .NET-Laufzeiten verfügbar sein sollen.  Sie wird von der .NET Core Runtime unterstützt.

Dies bedeutet, dass Sie einen Kompromiss zwischen APIs eingehen müssen, die Sie verwenden können, und Plattformen, die Sie unterstützen können, und die Version des .NET-Plattform Standards auswählen müssen, die am besten zu Ihrem Kompromiss passt.

Ab jetzt gilt es, 7 verschiedene Versionen zu bedenken: .NET Standard 1.0 bis 1.6.  Wenn Sie eine höhere Version auswählen, erhalten Sie mehr Zugriff auf APIs, was bedeutet, dass es auf weniger Zielen ausgeführt wird.  Wenn Sie eine niedrigere Version auswählen, kann Ihr Code auf mehreren Zielen ausgeführt werden, jedoch stehen Ihnen weniger APIs zur Verfügung.

Der Einfachheit halber, steht Ihnen hier eine Matrix jeder .NET-Standardversion und jedes angegebenen Bereichs zur Verfügung, in dem sie ausgeführt wird:

| Plattformname | Alias |  |  |  |  |  | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|.NET-Standard | netstandard | 1,0 | 1,1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 |
|.NET Core|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1,0|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|4.6.3|
|Mono-/Xamarin-Plattformen||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|*|
|Universelle Windows-Plattform|uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|||
|Windows|win|&rarr;|8.0|8.1|||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1|||||
|Windows Phone Silverlight|wp|8.0|||||||

Wichtig zum Verständnis ist, dass **ein Projekt, das eine niedrigere Version als Ziel festlegt nicht auf ein Projekt verweisen kann, das eine höhere Version als Ziel festlegt**.  Beispielsweise kann ein Projekt, das die Version 1.2 des .NET-Plattform Standards als Ziel festlegt, nicht auf Projekte verweisen, die die Version 1.3 oder höher des .NET-Plattform Standards als Ziel festlegen.  Projekte **können** jedoch auf niedrigere Versionen verweisen. Ein Projekt, das .NET-Plattform Standard 1.3 als Ziel festlegt, kann also auf ein Projekt verweisen, das .NET-Plattform Standard 1.2 oder als Ziel festlegt.

Es wird empfohlen, dass Sie die niedrigste mögliche .NET Standardversion auswählen und diese in Ihrem gesamten Projekt verwenden.

Erfahren Sie mehr in der [.NET Plattform Standard-Bibliothek](../../standard/library.md).

## <a name="key-technologies-not-yet-available-on-the-net-standard-or-net-core"></a>Noch nicht verfügbare Schlüsseltechnologien auf dem .NET Standard oder .NET Core

Sie verwenden möglicherweise einige Technologien für das .NET Framework, die derzeit nicht für .NET Core verfügbar sind.  Jeder der folgenden Unterabschnitte entspricht einer dieser Technologien.  Alternative Optionen werden aufgelistet, falls es für Sie realisierbar ist, diese anzuwenden.

### <a name="app-domains"></a>App-Domänen

App-Domänen können für verschiedene Zwecke für .NET Framework verwendet werden. Für die Codeisolierung empfehlen wir separate Prozesse und/oder Container als Alternative. Für das dynamische Laden von Assemblys empfehlen wir die neue Klasse @System.Runtime.Loader.AssemblyLoadContext.

### <a name="remoting"></a>Remoting

Für die Kommunikation zwischen Prozessen können die Mechanismen der prozessübergreifenden Kommunikation (interprocess communication, IPC) als Alternative zu Remoting verwendet werden. Diese sind z.B. [Pipes](https://docs.microsoft.com/dotnet/core/api/system.io.pipes) oder [Speicherabbilddateien](https://docs.microsoft.com/dotnet/core/api/system.io.memorymappedfiles.memorymappedfile).

Auf Computern können Sie eine netzwerkbasierte Lösung als Alternative anwenden, vorzugsweise ein Nur-Text-Protokoll mit geringem Mehraufwand, z.B. HTTP.  [KestrelHttpServer](https://github.com/aspnet/KestrelHttpServer), der von ASP.NET Core verwendete Webserver, ist hier eine Option.  Die remote Proxygenerierung über [Castle.Core](https://github.com/castleproject/Core) ist ebenfalls eine Option, die Sie in Erwägung ziehen sollten.

### <a name="binary-serialization"></a>Binäre Serialisierung

Als Alternative zur binären Serialisierung existieren mehrere verschiedene Serialisierungstechnologien, aus denen Sie auswählen können.  Sie sollten die Technologie auswählen, die sich am besten für Ihre Formatierungs- und Speicherplatzziele eignet.  Häufig verwendete Optionen sind:

* [JSON.NET](http://www.newtonsoft.com/json) für JSON
* @System.Runtime.Serialization.DataContractSerializer für XML und JSON
* @System.Xml.Serialization.XmlSerializer für XML
* [protobuf-net](https://github.com/mgravell/protobuf-net) für Protokollpuffer

Beziehen Sie sich auf die verlinkten Ressourcen, um weiteres über deren Vorteile zu erfahren, und wählen Sie diejenigen aus, die am besten für Sie geeignet sind.  Es gibt viele andere Serialisierungsformate und -technologien, von denen viele Open Source sind.

### <a name="sandboxes"></a>Sandkästen

Als Alternative zur Verwendung eines Sandkastens, können Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen verwenden, z.B. Benutzerkonten zum Ausführen von Prozessen mit den geringsten Rechten.

## <a name="overview-of-projectjson"></a>Übersicht über `project.json`

Das [project.json-Projektmodell](../tools/project-json.md) ist ein Projektmodell, das mit dem .NET Core-SDK 1.0 Preview 2 versendet wird.  Es bietet einige Vorteile, die Sie möglicherweise heute nutzen möchten:

* Die einfache Festlegung von Zielversionen, bei der zielspezifische Assemblys aus einem einzelnen Build erstellt werden können
* Die Möglichkeit, einfach ein NuGet-Paket mit einem Build des Projekts zu erstellen
* Kein Auflisten von Dateien in Ihrer Projektdatei nötig
* Vereinheitlichung von NuGet-Paketabhängigkeiten und Projekt-zu-Projekt-Abhängigkeiten

> Obwohl `project.json` schließlich als veraltet markiert werden wird, kann es jetzt noch verwendet werden, um Bibliotheken auf dem .NET Standard zu erstellen.

### <a name="the-project-file-projectjson"></a>Die Projektdatei: `project.json`

.NET Core-Projekte werden durch ein Verzeichnis definiert, das eine `project.json`-Datei enthält.  In dieser Datei werden Aspekte des Projekts deklariert, wie z.B. Paketabhängigkeiten, Compilerkonfiguration, Laufzeitkonfiguration usw.

Der Befehl `dotnet restore` liest die Projektdatei, stellt alle Abhängigkeiten des Projekts wieder her und generiert eine `project.lock.json`-Datei.  Diese Datei enthält alle erforderlichen Informationen, die das Buildsystem benötigt, um das Projekt zu erstellen.

Lesen Sie [project.json reference (project.json-Referenz)](../tools/project-json.md), um mehr über die `project.json`-Datei zu erfahren.

### <a name="the-solution-file-globaljson"></a>Die Projektmappendatei: `global.json`

Die `global.json`-Datei ist eine optionale Datei, um eine Projektmappe einzuschließen, die mehrere Projekte enthält.  Sie befindet sich in der Regel im Stammverzeichnis einer Reihe von Projekten.  Sie kann verwendet werden, um das Buildsystem verschiedener Unterverzeichnisse, die Projekte enthalten können, zu informieren.  Dies ist für größere Systeme vorgesehen, die aus einer Vielzahl von Projekten bestehen.

Sie können z.B. Ihren Code in den obersten `/src`- und `/test`-Ordern organisieren, z.B.:

```json
{
    "projects":[ "src", "test" ]
}
```

Mehrere `project.json`-Dateien dürfen dann unter Ihren eigenen Unterordnern innerhalb von `/src` und `/test` existieren.

### <a name="how-to-multitarget-with-projectjson"></a>So legen Sie die Zielversion mit `project.json` fest

Viele Bibliotheken legen die Zielversion fest, um über so viel Reichweite wie möglich zu verfügen.  Die Festlegung von Zielversionen mit .NET Core ist ein „First-Class-Objekt“, was bedeutet, dass Sie plattformspezifische Assemblys einfach mit einem einzelnen Build erstellen können.

Die Festlegung von Zielversionen ist genauso einfach wie das Hinzufügen eines Zielframeworkmonikers (Target Framework Moniker, TFM) zu Ihrer `project.json`-Datei mithilfe der richtigen Abhängigkeiten für jedes Ziel (`dependencies` für .NET Core und `frameworkAssemblies` für .NET Framework), möglicherweise unter Verwendung von `#if`-Anweisungen, um den Sourcecode für den plattformspezifischen API-Gebrauch bedingt zu kompilieren.

Angenommen, Sie erstellen z.B. eine Bibliothek, in der Sie einige Netzwerkvorgänge durchführen möchten, und sie möchten, dass diese Bibliothek auf allen Versionen von .NET Framework, einer portablen Klassenbibliothek (Portable Class Library, PCL) und .NET Core ausgeführt wird.  Für .NET Core und .NET Framework 4.5 + Ziele können Sie möglicherweise die `System.Net.Http`-Bibliothek und `async`/`await` verwenden.  Für frühere Versionen von .NET Framework sind diese APIs jedoch nicht verfügbar.

Hier ist ein Beispiel-`frameworks`-Abschnitt für eine `project.json`-Datei, die auf die .NET Framework-Versionen 2.0, 3.5, 4.0, 4.5 sowie .NET Standard 1.6 abzielt:

```javascript
{
    "frameworks":{
        "net20":{
            "frameworkAssemblies":{
                "System.Net":""
            }
        },
        "net35":{
            "frameworkAssemblies":{
                "System.Net":""
            }
        },
        "net40":{
            "frameworkAssemblies":{
                "System.Net":""
            }
        },
        "net45":{
            "frameworkAssemblies":{
                "System.Net.Http":"",
                "System.Threading.Tasks":""
            }
        },
        ".NETPortable,Version=v4.5,Profile=Profile259": {
            "buildOptions": {
                "define": [ "PORTABLE" ]
             },
             "frameworkAssemblies":{
                 "mscorlib":"",
                 "System":"",
                 "System.Core":"",
                 "System.Net.Http":""
             }
        },
        "netstandard16":{
            "dependencies":{
                "NETStandard.Library":"1.6.0",
                "System.Net.Http":"4.0.1",
                "System.Threading.Tasks":"4.0.11"
            }
        },
    }
}
```

Beachten Sie, dass PCL-Ziele besonders sind: Es ist erforderlich, dass Sie eine Builddefinition angeben, die der Compiler erkennt. Außerdem müssen Sie alle Assemblys angeben, die Sie verwenden, einschließlich `mscorlib`.  

Ihr Quellcode kann dann die Abhängigkeiten wie folgt verwenden:

```csharp
#if (NET20 || NET35 || NET40 || PORTABLE)
using System.Net;
#else
using System.Net.Http;
using System.Threading.Tasks;
#endif
```

Beachten Sie, dass alle .NET Framework und .NET Standard-Ziele Namen besitzen, die vom Compiler erkannt werden:

```
.NET Framework 2.0   --> NET20
.NET Framework 3.5   --> NET35
.NET Framework 4.0   --> NET40
.NET Framework 4.5   --> NET45
.NET Framework 4.5.1 --> NET451
.NET Framework 4.5.2 --> NET452
.NET Framework 4.6   --> NET46
.NET Framework 4.6.1 --> NET461
.NET Framework 4.6.2 --> NET462
.NET Standard 1.0    --> NETSTANDARD1_0
.NET Standard 1.1    --> NETSTANDARD1_1
.NET Standard 1.2    --> NETSTANDARD1_2
.NET Standard 1.3    --> NETSTANDARD1_3
.NET Standard 1.4    --> NETSTANDARD1_4
.NET Standard 1.5    --> NETSTANDARD1_5
.NET Standard 1.6    --> NETSTANDARD1_6
```

Wie oben erwähnt, müssen Sie eine Builddefinition angeben,die der Compiler versteht., wenn Sie auf eine PLC abzielen.  Es gibt keine Standarddefinition, die der Compiler verwenden kann.

### <a name="using-projectjson-in-visual-studio"></a>Verwenden von `project.json` in Visual Studio

Sie haben zwei Optionen für die Verwendung von `project.json` in Visual Studio:

1. Ein neuer XPROJ-Projekttyp
2. Ein neu zugewiesenes PCL-Projekt, das .NET Standard unterstützt

Es gibt verschiedene Vor- und Nachteile für jede Option.

#### <a name="when-to-pick-an-xproj-project"></a>Wann ein Pick- und ein XPROJ-Projekt ausgewählt wird

Das neue XPROJ-Projektsystem in Visual Studio nutzt die Funktionen des auf `project.json` basierenden Projektmodells, um zwei wichtige Features zu vorhandenen Projekttypen anzubieten: die nahtlose Festlegung von Zielversionen durch Erstellen mehrerer Assemblys und die Fähigkeit, direkt ein NuGet-Paket auf dem Build zu erstellen.

Der Nachteil ist jedoch, dass einige Features fehlen, die Sie möglicherweise verwenden, z.B.:

- Die Unterstützung für F# oder Visual Basic
- Die Generierung von Satellitenassemblys mit lokalisierten Ressourcenzeichenfolgen
- Das direkte Verweisen auf eine `.dll`-Datei innerhalb des Dateisystems
- Die Möglichkeit, auf ein CSPROJ-basiertes Projekt im Verweis-Manager zu verweisen (obwohl dies abhängig von der `.dll`-Datei unterstützt wird)

Wenn die Ansprüche für Ihr Projekt relativ klein sind, können sie von den neuen XPROJ-Features profitieren, die Sie als Projektsystem übernehmen sollten.  Dies kann in Visual Studio wie Folgt durchgeführt werden:

1. Überprüfen Sie, ob Sie Visual Studio 2015 oder höher verwenden.
2. Wählen Sie „Datei“ | „Neues Projekt“ aus.
3. Wählen Sie „.NET Core“ unter Visual C# aus.
4. Wählen Sie die Vorlage „Klassenbibliothek (.NET Core)“ aus. 

#### <a name="when-to-pick-a-pcl-project"></a>Wann ein PCL-Projekt ausgewählt wird

Sie können mit dem herkömmlichen Projektsystem in Visual Studio .NET Core als Ziel festlegen, indem Sie eine portable Klassenbibliothek erstellen und „.NET Core“ im Dialogfeld „Projektkonfiguration“ auswählen.  Anschließend müssen Sie das Projekt erneut auf den .NET Standard zuweisen.

1. Klicken Sie mit der rechten Maustaste auf die Projektdateien in Visual Studio, und klicken Sie auf „Eigenschaften“.
2. Wählen Sie unter Build „Convert to .NET Standard (Konvertieren zu .NET Standard)“ aus.

Wenn Sie mehr Projektsystembedarf haben, sollte dies Ihre erste Wahl sein.  Wenn Sie die Zielversion festlegen möchten, indem Sie plattformspezifische Assemblys etwa mit dem `xproj`-Projektsystem generieren, beachten Sie, dass Sie eine „Lockvogel“-PCL erstellen müssen, so wie in [How to Make Portable Class Libraries Work for You (So lassen Sie übertragbare Klassenbibliotheken für sich arbeiten)](https://blogs.msdn.microsoft.com/dsplaisted/2012/08/27/how-to-make-portable-class-libraries-work-for-you/) beschrieben.

## <a name="retargeting-your-net-framework-code-to-net-framework-462"></a>Neuzuweisung Ihres .NET Framework-Codes zu .NET Framework 4.6.2

Wenn Ihr Code nicht .NET Framework 4.6.2 als Ziel festlegt, wird empfohlen, dass Sie ihn neu zuweisen.  Dadurch wird sichergestellt, dass Sie die neuesten API-Alternativen für Fälle verwenden können, in denen .NET Standard vorhandene APIs nicht unterstützen kann.

Führen Sie für jedes Projekt in Visual Studio, das Sie portieren möchten, die folgenden Schritte durch:

1. Klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie „Eigenschaften“ aus.
2. Wählen Sie in der Dropdownliste „Zielframework“ den Eintrag „.NET Framework 4.6.2“ aus.
3. Kompilieren Sie Ihre Projekte neu.

Und das ist schon alles!  Da Ihre Projekte jetzt .NET Framework 4.6.2 als Ziel festgelegt haben, können Sie diese Version von .NET Framework als Grundlage zum Portieren von Code verwenden.

## <a name="determining-the-portability-of-your-code"></a>Bestimmen der Portabilität Ihres Codes

Führen Sie als nächsten Schritt das Tool zum Analysieren der API-Portabilität aus, um einen Portabilitätsbericht zu erstellen, den Sie daraufhin analysieren können.

Sie müssen sicherstellen, dass Sie das [Tool zum Analysieren der API-Portabilität (ApiPort)](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) verstehen und Portabilitätsberichte generieren können, die .NET Core als Ziel festlegen.  Wie Sie das bewerkstelligen, hängt von Ihren Bedürfnissen und Ihrem persönlichen Geschmack ab.  Im Folgenden sehen Sie ein paar unterschiedliche Ansätze – Sie können die Ansätze abhängig von der Struktur Ihres Codes mischen.

### <a name="dealing-primarily-with-the-compiler"></a>Schwerpunktmäßiger Umgang mit dem Compiler

Diese Vorgehensweise ist möglicherweise am Besten für kleine Projekte oder für Projekte, die nicht viele .NET Framework-APIs verwenden.  Die Vorgehensweise ist sehr einfach:

1. Führen Sie optional ApiPort auf Ihrem Projekt aus.
2. Wenn ApiPort ausgeführt wurde, sehen Sie sich kurz den Bericht an.
3. Kopieren Sie Ihren gesamten Code in ein neues .NET Core-Projekt.
4. Bereinigen Sie Compilerfehler bis eine Kompilierung erfolgt. Beziehen Sie sich falls nötig auf den Portabilitätsbericht.
5. Wiederholen Sie den Vorgang nach Bedarf.

Obwohl diese Vorgehensweise sehr unstrukturiert ist, kann die codeorientierte Vorgehensweise dazu führen, dass Fehler schnell gelöst werden können, und sie kann sich auch am besten für kleinere Projekte oder Bibliotheken eignen.  Ein Projekt, das nur Datenmodelle enthält, kann hier möglicherweise ein idealer Kandidat sein.

### <a name="staying-on-the-net-framework-until-portability-issues-are-resolved"></a>Auf dem .NET Framework bleiben, bis Portabilitätsprobleme gelöst sind

Diese Vorgehensweise ist möglicherweise die beste Lösung, wenn Sie lieber über Code verfügen möchten, der während des gesamten Prozesses kompiliert wird.  Die Vorgehensweise sieht wie Folgt aus:

1. Führen Sie ApiPort auf einem Projekt aus.
2. Beheben Sie Probleme mithilfe der verschiedenen APIs, die übertragbar sind.
3. Notieren Sie sich alle Bereiche, in denen Sie keine direkte Alternative verwenden können.
4. Wiederholen Sie die Schritte 1 bis 3 für alle Projekte, die Sie portieren, bis Sie sicher sind, dass jedes Projekt in ein .NET Core-Projekt kopiert wurde.
5. Kopieren Sie den Code in neue .NET Core-Projekte.
6. Lösen sie alle Probleme, die Sie sich notiert haben.

Diese sorgfältige Vorgehensweise ist strukturierter als einfach Compilerfehler zu beheben, ist jedoch auch relativ codeorientiert und hat den Vorteil, dass immer Code vorhanden ist, der kompiliert werden kann.  Die Herangehensweise, wie Sie bestimmte Probleme lösen, die nicht nur durch einfaches Verwenden der API behoben werden können, kann stark variieren.  Möglicherweise müssen Sie einen umfassenderen Plan für bestimmte Projekte entwickeln, der als weitere Vorgehensweise gilt.

### <a name="developing-a-comprehensive-plan-of-attack"></a>Entwickeln eines umfassenden Vorgehensplans

Diese Vorgehensweise ist möglicherweise am besten für größere und komplexere Projekte geeignet, bei denen es womöglich nötig ist, Code umzustrukturieren oder bestimmte Bereiche erneut zu schreiben, um .NET Core zu unterstützen.  Die Vorgehensweise sieht wie Folgt aus:

1. Führen Sie ApiPort auf einem Projekt aus.
2. Sie müssen verstehen, wo in Ihrem Code jeder nicht portable Typ verwendet wird und wie sich dies auf die gesamte Portabilität auswirkt.

   a.  Verstehen sie die Natur dieser Typen.  Stellen sie nur eine geringe Anzahl dar, werden jedoch oft verwendet?  Stellen sie eine hohe Anzahl dar, werden jedoch nicht oft verwendet?  Ist ihre Verwendung auf einen Punkt ausgerichtet oder im gesamten Code verteilt?
   
   b. Ist es einfach, Code zu isolieren, der nicht portabel ist, damit Sie leichter damit umgehen können?
   
   c. Müssen Sie Ihren Code umgestalten?
   
   d. Gibt es für nicht portable Typen alternative APIs, die die gleiche Aufgabe erfüllen?  Wenn Sie z.B. die `WebClient`-Klasse verwenden, können Sie stattdessen möglicherweise die `HttpClient`-Klasse verwenden.
   
   e. Gibt es unterschiedliche portable APIs, mit denen Sie eine Aufgabe erfüllen können, auch wenn es kein direkter Ersatz ist?  Wenn Sie beispielsweise `XmlSchema` zum Analysieren von XML verwenden, jedoch die XML-Schemasuche nicht benötigen, können Sie `System.Linq.Xml`-APIs verwenden, um die Daten manuell zu analysieren.

3. Wenn Sie über Assemblys verfügen, die schwierig zu portieren sind, bringt es etwas, Sie vorübergehend in .NET Framework zu lassen?  Nachfolgend sind einige Dinge aufgeführt, die Sie bedenken sollten:

   a. Sie verfügen womöglich über einige Funktionen in Ihrer Bibliothek, die mit .NET Core inkompatibel sind, da sie zu sehr auf der bestimmten.NET Framework- oder Windows-Funktionalität basiert.  Ist es also vorteilhaft, diese Funktionalität vorübergehend zu ignorieren, und für den Moment eine .NET Core-Version Ihrer Bibliothek mit weniger Features zu veröffentlichen?
   
   b. Würde eine Umgestaltung hier helfen?
   
4. Ist es sinnvoll, eine eigene Implementierung einer nicht verfügbaren .NET Framework-API zu schreiben?

   Sie könnten stattdessen kopieren, ändern und Code aus der [.NET Framework Reference Source](https://github.com/Microsoft/referencesource) verwenden.  Der Code wird unter der [MIT License (MIT-Lizenz)](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt) lizenziert, Sie haben also die Freiheit, dies zu tun.  Stellen Sie nur sicher, dass Sie Microsoft ordnungsgemäß Ihrem Code zugeordnet haben.
   
5. Wiederholen Sie diesen Vorgang für verschiedene Projekte nach Bedarf.
6. Nachdem Sie einen Plan erstellt haben, führen Sie diesen aus.
 
Die Analysephase kann je nach Größe Ihrer Codebasis einige Zeit dauern.  Sie können sich auf lange Sicht viel Zeit in dieser Phase sparen, wenn Sie den Umfang der erforderlichen Änderungen verstehen und einen Plan entwickeln, besonders, wenn sie über eine komplexere Codebasis verfügen.

Ihr Plan kann wichtige Änderungen an Ihrer Codebase erfordern, während Sie noch immer auf .NET Framework 4.6.2 abzielen. Dadurch entsteht eine strukturiertere Version des vorherigen Ansatzes.  Wie Sie Ihren Plan ausführen, hängt von Ihrer Codebasis ab.

### <a name="mixing-approaches"></a>Mischen von Vorgehensweisen

Es ist wahrscheinlich, dass Sie die oben genannten Vorgehensweisen jeweils pro Projekt mischen werden.  Sie sollten den Ansatz wählen, der am meisten Sinn für Sie und Ihre Codebasis macht.

## <a name="porting-your-tests"></a>Portieren der Tests

Die beste Möglichkeit, um sicherzustellen, dass alles funktioniert, wenn Sie Ihren Code importiert haben, ist das Testen Ihres Codes beim Portieren auf .NET Core.  Zu diesem Zweck müssen Sie ein Test-Framework verwenden, das Tests für .NET Core erstellt und ausführt.  Derzeit stehen Ihnen drei Optionen zur Verfügung:

* [xUnit](https://xunit.github.io/)
   - [Erste Schritte](http://xunit.github.io/docs/getting-started-dnx.html)
   - [Tool zum Konvertieren eines MSTest-Projekts zu xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
* [NUnit](http://www.nunit.org/)
  - [Erste Schritte](https://github.com/nunit/docs/wiki/Installation)
  - [Blogbeitrag zur Migration von MSTest zu NUnit (in englischer Sprache)](http://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
* [MSTest](https://msdn.microsoft.com/library/ms243147.aspx)

## <a name="recommended-approach-to-porting"></a>Empfohlene Vorgehensweise zum Portieren

Nun portieren wir endlich den Code selbst!  Die tatsächliche Arbeit für die Portierung hängt letztendlich schwer davon ab, wie Ihr .NET Framework-Code strukturiert ist.  Da dies jetzt geklärt ist, können Sie die nachfolgende Vorgehensweise verwenden, die sich gut für Ihre Codebasis eignen müsste.

Eine gute Möglichkeit, Ihren Code zu portieren, ist es, mit der „Basis“ Ihrer Bibliothek zu beginnen.  Dies sind womöglich Datenmodelle oder einige andere grundlegende Klassen und Methoden, die von allem anderen direkt oder indirekt verwendet werden.

1. Portieren Sie das Testprojekt, das die Ebene Ihrer Bibliothek testet, die Sie derzeit portieren.
2. Kopieren Sie die „Basis“ Ihrer Bibliothek in ein neues .NET Core-Projekt, und wählen Sie die Version von .NET Standard aus, die Sie unterstützen möchten.
3. Führen Sie alle erforderlichen Änderungen durch, sodass der Code kompiliert werden kann.  Vieles davon erfordert möglicherweise das Hinzufügen von NuGet-Paketabhängigkeiten zu ihrer `project.json`-Datei.
4. Führen Sie Tests aus, und führen Sie erforderliche Anpassungen durch.
5. Wählen Sie die nächste Codeebene aus, die portiert werden soll, und wiederholen Sie die Schritte 2 und 3.

Wenn Sie sich methodisch von der Basis Ihrer Bibliothek aus nach außen bewegen, und jede Ebene wie erforderlich testen, wird die Portierung ein schematischer Prozess sein, bei dem Probleme jeweils auf einer Codeebene isoliert werden.



<!--HONumber=Nov16_HO3-->


