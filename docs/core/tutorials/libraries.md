---
title: "Entwickeln von Bibliotheken mit plattformübergreifenden Tools"
description: "Entwickeln von Bibliotheken mit plattformübergreifenden Tools"
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9f6e8679-bd7e-4317-b3f9-7255a260d9cf
translationtype: Human Translation
ms.sourcegitcommit: 0882a5ca2f7814e2fd168dce40705d11b199f102
ms.openlocfilehash: de44f103bef6006dd1a952c48c1e172f6277a95b

---

# <a name="developing-libraries-with-cross-platform-tools"></a>Entwickeln von Bibliotheken mit plattformübergreifenden Tools

**Einige Details unterliegen noch Änderungen, da sich die Toolkette noch in der Entwicklung befindet.**

Dieser Artikel behandelt, wie man mithilfe von plattformübergreifenden CLI-Tools Bibliotheken für .NET schreibt.  Die CLI bietet effiziente Funktionalität auf niedriger Stufe, die auf allen unterstützten Betriebssystemen funktioniert.  Sie können trotzdem noch Bibliotheken mit Visual Studio erstellen. Wenn das Ihre bevorzugte Methode ist, finden Sie [weitere Informationen im Handbuch für Visual Studio](libraries-with-vs.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

[Das .NET Core SDK und die CLI](https://www.microsoft.com/net/core) müssen auf Ihrem Computer installiert sein.

Für die Abschnitte dieses Dokuments, in denen es um .NET Framework-Versionen oder Portable Klassenbibliotheken (Portable Class Libraries, PCL) geht, muss das [.NET Framework](http://getdotnet.azurewebsites.net/) auf einem Windows-Computer installiert sein.  

Wenn Sie ältere .NET Framework-Ziele unterstützen möchten, müssen Sie außerdem Pakete zum Festlegen von Zielversionen und Entwicklerpakete für ältere Frameworkversionen installieren. Sie erhalten diese auf der Seite [.NET target platforms (.NET Zielplattformen)](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).  Weitere Informationen finden Sie in dieser Tabelle:

| .NET Framework-Version | Empfohlene Downloads |
| ---------------------- | ----------------- |
| 4.6.1 | Paket zur Festlegung von Zielversionen für .NET Framework 4.6.1 |
| 4.6 | Paket zur Festlegung von Zielversionen für .NET Framework 4.6 |
| 4.5.2 | .NET Framework 4.5.2 Entwicklerpaket |
| 4.5.1 | .NET Framework 4.5.1 Entwicklerpaket |
| 4.5 | Windows Software Development Kit für Windows 8 |
| 4.0 | Windows SDK für Windows 7 und .NET Framework 4 |
| 2.0, 3.0 und 3.5 | .NET Framework 3.5 SP1-Runtime (oder Windows 8+-Version) |

## <a name="how-to-target-the-net-standard"></a>So legen Sie .NET Standard als Ziel fest

Wenn Sie noch nicht mit .NET Standard vertraut sind, finden Sie unter [NET Standard Library (.NET-Standardbibliothek)](../../standard/library.md) weitere Informationen.

In diesem Artikel finden Sie eine Tabelle, in der die Versionen von .NET Standard zahlreichen Implementierungen zugeordnet werden:

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

Im Folgenden wird erklärt, was diese Tabelle für das Erstellen einer Bibliothek bedeutet:

Die Version von .NET Plattform Standard, die Sie auswählen, bildet einen Kompromiss zwischen dem Zugang zu den neuesten APIs und der Möglichkeit, mehr .NET-Plattformen und Frameworkversionen als Ziel festzulegen.  Sie kontrollieren den Bereich der Plattformen, die als Ziel gesetzt werden können, und der Versionen, indem Sie eine `netstandardX.X`-Version auswählen (`X.X` steht für eine Versionsnummer) und Sie zu Ihrer `project.json`-Datei hinzufügen.

Außerdem ist `NETStandard.Library`, Version `1.6.0` das entsprechende [NuGet-Paket, auf das man sich beziehen soll](https://www.nuget.org/packages/NETStandard.Library/).  Es hindert Sie zwar nichts daran, sich auf `Microsoft.NETCore.App` zu beziehen, wie bei Konsolenanwendungen, es wird allerdings nicht empfohlen.  Wenn Sie APIs aus einem Paket benötigen, dass nicht in `NETStandard.Library` angegeben ist, können Sie dieses Paket immer zusätzlich zu `NETStandard.Library` im Bereich `dependencies` (Abhängigkeiten) Ihrer `project.json`-Datei angeben.

Wenn Sie .NET Standard als Ziel festlegen, stehen Ihnen je nach Bedarf drei Optionen zur Verfügung.

1. Sie können die höchste Version von .NET Standard – `netstandard1.6` – verwenden. Diese ist geeignet, wenn Sie Zugriff auf die meisten APIs haben möchten, und es Ihnen nichts ausmacht, wenn Sie weniger Reichweite bei Implementierungen haben.
2. Sie können eine ältere Version von .NET Standard verwenden, um frühere Implementierungen von .NET als Ziel festzulegen. Der Nachteil ist, dass Sie keinen Zugriff auf einige der neuesten APIs haben.
    
    Wenn Sie zum Beispiel garantierte Kompatibilität mit .NET Framework 4.6 und höher haben möchten, können Sie `netstandard1.3` auswählen:

    ```json
    {
        "dependencies":{
            "NETStandard.Library":"1.6.0"
        },
        "frameworks":{
            "netstandard1.3":{}
        }
    }
    ```
    
    .NET Standard-Versionen sind abwärtskompatibel. Das bedeutet, dass `netstandard1.0`-Bibliotheken auf `netstandard1.1`-Plattformen und höher ausgeführt werden können.  Es gibt allerdings keine Aufwärtskompatibilität – niedrigere .NET Standard-Plattformen können nicht auf höhere verweisen.  Das bedeutet, dass `netstandard1.0`-Bibliotheken nicht auf Bibliotheken verweisen können, die `netstandard1.1` oder höher als Ziel haben.  Wählen Sie die Standard-Version aus, die die beste Mischung aus APIs und Plattformunterstützung für Ihre Anforderungen bietet.
    
3. Wenn Sie die .NET Framework-Version 4.0 oder niedriger als Ziel festlegen wollen, oder Sie eine API verwenden wollen, die in .NET Framework verfügbar ist, aber nicht in .NET Standard (z.B. `System.Drawing`), lesen Sie die folgenden Abschnitte. Hier lernen Sie, wie man die Zielversion festlegt.

## <a name="how-to-target-the-net-framework"></a>So legen Sie .NET Framework als Ziel fest

> [!NOTE]
> In diesen Anweisungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist.  Informationen zum Installieren von Abhängigkeiten finden Sie unter [Erforderliche Komponenten](#prerequisites).

Bedenken Sie, dass einige der hier verwendeten .NET Framework-Versionen nicht mehr unterstützt werden.  Für weitere Informationen über nicht unterstütze Versionen, besuchen Sie [.NET Framework Support Lifecycle Policy FAQ (.NET Framework Support Lifecycle-Richtlinien FAQ)](https://support.microsoft.com/gp/framework_faq/en-us).

Wenn Sie so viele Entwickler und Projekte erreichen möchten wie möglich, verwenden Sie .NET Framework 4 als Baseline-Ziel. Um .NET Framework als Ziel festzulegen, müssen Sie zuerst den richtigen Zielframeworkmoniker (Target Framework Moniker, TMF) auswählen, der der .NET Framework-Version entspricht, die Sie unterstützen möchten.

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.6.3 --> net463
```

Hier sehen Sie zum Beispiel, wie Sie eine Bibliothek schreiben, die .NET Framework 4 als Ziel festlegt:

```json
{
    "frameworks":{
        "net40":{}
    }
}
```

Und das ist schon alles!  Obwohl dies nur für .NET Framework 4 kompiliert, können Sie die Bibliothek auf neueren Versionen von .NET Framework verwenden.

## <a name="how-to-target-a-portable-class-library-pcl"></a>So legen Sie eine Portable Klassenbibliothek (PCL) als Ziel fest

> [!NOTE]
> In diesen Anweisungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist.  Informationen zum Installieren von Abhängigkeiten finden Sie unter [Erforderliche Komponenten](#prerequisites).

Ein PCL-Profil als Ziel festzulegen ist ein bisschen komplizierter als bei .NET Standard oder .NET Framework.  Zunächst einmal [verweisen Sie auf diese Liste von PCL-Profilen](http://embed.plnkr.co/03ck2dCtnJogBKHJ9EjY/preview), um das NuGet-Ziel zu finden, das dem PCL-Profil entspricht, das Sie als Ziel festlegen.

Danach müssen Sie folgende Schritte befolgen:

1. Erstellen Sie einen neuen Eintrag mit dem Namen `.NETPortable,Version=v{version},Profile=Profile{profile}` unter `frameworks` in Ihrer `project.json`-Datei, wobei `{version}` und `{profile}` jeweils einer Versions- und Profilnummer einer PCL entsprechen.
2. In diesem neuen Eintrag listen Sie jede einzelne Assembly für dieses Ziel unter einem `frameworkAssemblies`-Eintrag auf.  Dazu gehören `mscorlib`, `System` und `System.Core`.
3. Wenn Sie Zielversionen festlegen (siehe nächster Abschnitt), müssen Sie Abhängigkeiten für jedes Ziel eindeutig unter deren Zieleinträgen auflisten.  Sie können keinen globalen `dependencies`-Eintrag mehr verwenden.

Im Folgenden finden Sie ein Beispiel mit PCL-Profil 328 als Ziel. Profil 328 unterstützt: .NET Standard 1.4, .NET Framework 4, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8.1 und Silverlight 5.

```json
{
    "frameworks":{
        ".NETPortable,Version=v4.0,Profile=Profile328":{
            "frameworkAssemblies":{
                "mscorlib":"",
                "System":"",
                "System.Core":""
            }
        }
    }
}
```

Wenn Sie ein Projekt erstellen, das das PCL-Profil 328 als Framework in der *project.json*-Datei enthält, finden Sie diesen Unterordner im Ordner */bin/debug*:

```
portable-net40+sl50+netcore45+wpa81+wp8/
```

Dieser Ordner enthält die `.dll`-Dateien, die notwendig sind, um Ihre Bibliothek auszuführen.

## <a name="how-to-multitarget"></a>So legen Sie die Zielversion fest

> [!NOTE]
> In den folgenden Anweisungen wird vorausgesetzt, dass .NET Framework auf Ihrem Computer installiert ist.  Im Abschnitt [Erforderliche Komponenten](#prerequisites) finden Sie weitere Informationen darüber, welche Abhängigkeiten Sie installieren müssen, und wo Sie diese herunterladen können.

Sie müssen möglicherweise ältere Versionen von .NET Framework als Ziel festlegen, wenn Ihr Projekt sowohl .NET Framework als auch .NET Core unterstützt. Wenn Sie neuere APIs und Sprachkonstrukte für die neueren Ziele verwenden möchten, verwenden Sie in diesem Szenario `#if`-Anweisungen in Ihrem Code. Möglicherweise müssen Sie auch andere Pakete und Abhängigkeiten in Ihrer `project.json file`-Datei hinzufügen. Sie müssen dies für jede Plattform, die Sie als Ziel festlegen durchführen, um die verschiedenen APIs hinzuzufügen, die für jeden Fall gebraucht werden.

Nehmen wir z.B. einmal an, dass Sie eine Bibliothek haben, die Netzwerkvorgänge über HTTP ausführt. Für .NET Standard und die .NET Framework-Versionen 4.5 oder höher können Sie die `HttpClient`-Klasse aus dem `System.Net.Http`-Namespace verwenden. Frühere Versionen von .NET Framework verfügen jedoch nicht über die Klasse `HttpClient`, daher können Sie für diese stattdessen die Klasse `WebClient` aus dem Namespace `System.Net` verwenden.

Die `project.json`-Datei könnte also folgendermaßen aussehen:

```json
{
    "frameworks":{
        "net40":{
            "frameworkAssemblies": {
                "System.Net":"",
                "System.Text.RegularExpressions":""
            }
        },
        "net452":{
            "frameworkAssemblies":{
                "System.Net":"",
                "System.Net.Http":"",
                "System.Text.RegularExpressions":"",
                "System.Threading.Tasks":""
            }
        },
        "netstandard1.6":{
            "dependencies": {
                "NETStandard.Library":"1.6.0",
            }
        }
    }
}
```

Beachten Sie, dass in den Zielen `net40` und `net452` eindeutig auf .NET Framework-Assemblys verwiesen werden muss. Außerdem müssen NuGet-Verweise eindeutig in Ziel `netstandard1.6` aufgelistet werden.  Dies ist bei Szenarios zur Festlegung von Zielversionen erforderlich.

Als Nächstes können die `using`-Anweisungen in der Quelldatei wie folgt angepasst werden:

```csharp
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
// This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif
```

Das Buildsystem beachtet die folgenden Präprozessorsymbole, die in `#if`-Anweisungen verwendet werden:

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

Außerdem können Sie die `#if`-Anweisungen in der Mitte der Quelle verwenden, um diese Bibliotheken bedingt zu verwenden. Zum Beispiel:

```csharp
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "http://www.dotnetfoundation.org/";
          
            var uri = new Uri(url);
            
            string result = "";
            
            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }
            
            int dotNetCount = Regex.Matches(result, ".NET").Count;
            
            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "http://www.dotnetfoundation.org/";
            
            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);
            
            int dotNetCount = Regex.Matches(result, ".NET").Count;
            
            return $"dotnetfoundation.orgmentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
```

Wenn Sie ein Projekt erstellen, das `net40`, `net45` und `netstandard1.6` als Framework in der *project.json*-Datei enthält, finden Sie diesen Unterordner im Ordner */bin/debug*:

```
net40/
net45/
netstandard1.6/
```

### <a name="but-what-about-multitargeting-with-portable-class-libraries"></a>Aber wie sieht es beim Festlegen von Zielversionen mit Portablen Klassenbibliotheken aus?

Wenn Sie mit einem PCL-Ziel übergreifend kompilieren möchten, müssen Sie in Ihrer `project.json`-Datei unter `buildOptions` in Ihrem PCL-Ziel eine Builddefinition hinzufügen.  Anschließend können Sie `#if`-Anweisungen in der Quelle verwenden, die die Builddefinition als Präprozessorsymbol verwenden.

Wenn Sie zum Beispiel [PCL-Profil 328](http://embed.plnkr.co/03ck2dCtnJogBKHJ9EjY/preview) (das .NET Framework 4, Windows 8, Windows Phone Silverlight 8, Windows Phone 8.1, Silverlight 5) als Ziel festlegen möchten, können Sie als „PORTABLE328“ auf dieses verweisen, wenn Sie übergreifend kompilieren.  Fügen sie einfach die `project.json`-Datei als ein Attribut `buildOptions` hinzu:

```json
{
    "frameworks":{
        "netstandard1.6":{
           "dependencies":{
                "NETStandard.Library":"1.6.0",
            }
        },
        ".NETPortable,Version=v4.0,Profile=Profile328":{
            "buildOptions": {
                "define": [ "PORTABLE328" ]
            },
            "frameworkAssemblies":{
                "mscorlib":"",
                "System":"",
                "System.Core":"",
                "System.Net"
            }
        }
    }
}

```

Nun können Sie dieses Ziel bedingt kompilieren:

```csharp
#if !PORTABLE328
using System.Net.Http;
using System.Threading.Tasks;
// Potentially other namespaces which aren't compatible with Profile 328
#endif
```

Da `PORTABLE328` jetzt vom Compiler erkannt wird, enthält der Compiler, der von der Bibliothek PCL-Profil 328 erzeugt wurde, weder `System.Net.Http` noch `System.Threading.Tasks`.

Wenn Sie ein Projekt erstellen, das PCL-Profil 328 und `netstandard1.6` als Framework in der *project.json*-Datei enthält, finden Sie diese Unterordner im Ordner */bin/debug*:

```
portable-net40+sl50+netcore45+wpa81+wp8/
netstandard1.6/
```

## <a name="how-to-use-native-dependencies"></a>So verwenden Sie native Abhängigkeiten

Möglicherweise möchten Sie eine Bibliothek erstellen, die sich auf eine native `.dll`-Datei bezieht.  Wenn Sie eine solche Bibliothek erstellen, haben Sie zwei Optionen:

1. Verweisen Sie direkt in Ihrer `project.json`-Datei auf die native `.dll`-Datei.
2. Packen Sie diese `.dll`-Datei in Ihr NuGet-Paket, und beziehen Sie sich auf dieses Paket.

Bei der ersten Option müssen folgende Schritte in Ihrer `project.json`-Datei ausgeführt werden:

1. Festlegen von `allowUnsafe` zu `true` in einem Abschnitt `buildOptions`.
2. Angeben eines [Laufzeitbezeichners (Runtime IDentifier, RID)](../rid-catalog.md) in einem Abschnitt `runtimes`.
3. Angeben des Pfads zu der/den nativen `.dll`-Datei(en), auf die Sie verweisen.

Hier sehen Sie ein Beispiel einer `project.json`-Datei mit einer nativen `.dll`-Datei im Stammverzeichnis, das unter Windows ausgeführt wird:

```json
{
    "buildOptions":{
        "allowUnsafe":true
    },
    "runtimes":{
        "win10-x64":{}
    },
    "packOptions":{
        "files":{
            "mappings":{
                "runtimes/win10-x64/native":{
                    "includeFiles":[ "native-lib.dll"]
                }
            }            
        }
    }
}
```

Wenn Sie die Bibliothek als Paket verteilen, wird empfohlen, dass Sie die `.dll`-Datei auf der Stammebene Ihres Projekts platzieren.

Bei der zweiten Option müssen Sie ein NuGet-Paket aus Ihrer/Ihren `.dll`-Datei(en) erstellen, auf einem NuGet oder MyGet-Feed bereitstellen, und sich direkt darauf beziehen.  Sie müssen noch `allowUnsafe` auf `true` im Abschnitt `buildOptions` Ihrer `project.json`-Datei festlegen.  Hier sehen Sie ein Beispiel (gehen Sie davon aus, dass `MyNativeLib` ein NuGet-Paket der Version `1.2.0` ist):

```json
{
    "buildOptions":{
        "allowUnsafe":true
    },
    "dependencies":{
        "MyNativeLib":"1.2.0"
    }
}
```

Wenn Sie ein Beispiel für das Packen von plattformübergreifenden nativen Binärdateien sehen möchten, sehen Sie sich das [ASP.NET Libuv-Paket](https://github.com/aspnet/libuv-package) und [den entsprechenden Verweis in KestrelHttpServer](https://github.com/aspnet/KestrelHttpServer/blob/1.0.0/src/Microsoft.AspNetCore.Server.Kestrel/project.json#L19) an.

## <a name="how-to-test-libraries-on-net-core"></a>So testen Sie die Bibliotheken unter .NET Core

Es ist wichtig, über Plattformen hinweg testen zu können.  Es ist am einfachsten, [xUnit](http://xunit.github.io/) zu verwenden. Das ist auch das Testtool, das von .NET Core-Projekten verwendet wird.  Wie Sie Ihre Lösung mit Testprojekten einrichten, hängt von der [Struktur Ihrer Lösung](#structuring-a-solution) ab.  Im folgenden Beispiel wird davon ausgegangen, dass alle Quellprojekte in einem `/src`-Ordner der obersten Ebene und alle Testprojekte in einem `/test`-Ordner der obersten Ebene zu finden sind.

1. Stellen Sie sicher, dass sich eine `global.json`-Datei auf Projektmappenebene befindet, die weiß, wo die Testprojekte sind:
    
    ```json
    {
        "projects":[ "src", "test"]
    }
    ```
    
    Die Struktur der Projektmappenordner sollte dann wie folgt aussehen:
    
    ```
    /SolutionWithSrcAndTest
    |__global.json
    |__/src
    |__/test
    ```
    
2. Erstellen Sie ein neues Testprojekt, indem Sie einen Projektordner unter Ihrem `/test`-Ordner und eine `project.json`-Datei in Ihrem neuen Projektordner erstellen.  Sie können den Befehl `dotnet new` ausführen, und danach die `project.json`-Datei bearbeiten, um die `project.json`-Datei zu erstellen.  Die Datei sollte folgendes enthalten:

   * `netcoreapp1.0` aufgelistet als der einzige Eintrag unter `frameworks`.
   * Einen Verweis auf `Microsoft.NETCore.App`, Version `1.0.0`.
   * Einen Verweis auf xUnit, Version `2.2.0-beta2-build3300`.
   * Einen Verweis auf `dotnet-test-xunit`, Version `2.2.0-preview2-build1029`
   * Einen Projektverweis auf die Bibliothek, die getestet wird.
   * Den Eintrag `"testRunner":"xunit"`.
   
   Hier sehen Sie ein Beispiel (`LibraryUnderTest`, Version `1.0.0` ist die Bibliothek, die getestet wird):
   
   ```json
   {
        "testRunner":"xunit",
        "dependencies":{
            "LibraryUnderTest":{
                "version":"1.0.0",
                "target":"project"
            },
            "Microsoft.NETCore.App":{
                "version":"1.0.0",
                "type":"platform"
            },
            "xunit":"2.2.0-beta2-build3300",
            "dotnet-test-xunit":"2.2.0-preview2-build1029",
        },
        "frameworks":{
            "netcoreapp1.0":{}
        }
   }
   ```
3. Stellen Sie Pakete durch Ausführen von `dotnet restore` wieder her.  Sie sollten dies auf Projektmappenebene durchführen, wenn Sie bisher noch keine Pakete wiederhergestellt haben.

4. Navigieren Sie zu Ihrem Testprojekt, und führen Sie Tests mit `dotnet test` aus:

    ```
    $ cd path-to-your-test-project
    $ dotnet test
    ```

Und das ist schon alles!  Jetzt können Sie Ihre Bibliothek mithilfe der Befehlszeilentools über alle Plattformen hinweg testen.  Nachdem jetzt alles eingerichtet ist, ist das weitere Testen Ihrer Bibliothek sehr einfach:

1. Nehmen Sie Änderungen an Ihrer Bibliothek vor.
2. Führen Sie mit dem Befehl `dotnet test` in Ihrem Testverzeichnis Tests über die Befehlszeile aus.

Der Code wird automatisch neu erstellt, wenn Sie den Befehl `dotnet test` aufrufen.

Denken Sie nur daran, `dotnet restore` über die Befehlszeile auszuführen, wenn eine neue Abhängigkeit hinzugefügt wird, und schon sind Sie startklar!

## <a name="how-to-use-multiple-projects"></a>So verwenden Sie mehrere Projekte

Eine häufige Anforderung an größere Bibliotheken ist es, Funktionalität in verschiedenen Projekten zu bieten.

Stellen Sie sich vor, Sie möchten eine Bibliothek erstellen, die in idiomatischem C# und F# benutzt wird.  Das würde bedeuten, dass Benutzer Ihrer Bibliotheken diese auf eine Art nutzen, die natürlich für C# und F# ist.  In C# z.B. könnten Sie die Bibliothek wie folgt nutzen:

```csharp
var convertResult = await AwesomeLibrary.ConvertAsync(data);
var result = AwesomeLibrary.Process(convertResult);
```  

In F# wird wie folgt formuliert:

```fsharp
let result =
    data
    |> AwesomeLibrary.convertAsync 
    |> Async.RunSynchronously 
    |> AwesomeLibrary.process
```

Solche Nutzungsszenarios bedeuten, dass die APIs, auf die zugegriffen wird, eine andere Struktur für C# und F# haben müssen.  Eine gängige Methode, dies zu erreichen ist, die gesamte Logik einer Bibliothek in ein Kernprojekt zu zerlegen, in dem C# und F# Projekte die API-Schichten definieren, die das Kernprojekt aufrufen.  Im übrigen Abschnitt werden die folgenden Namen verwendet:

* **AwesomeLibrary.Core** – Ein Kernprojekt, das die gesamte Logik für die Bibliothek enthält
* **AwesomeLibrary.CSharp** – Ein Projekt mit öffentlichen APIs, die für den Gebrauch in C vorgesehen sind#
* **AwesomeLibrary.FSharp** – Ein Projekt mit öffentlichen APIs, die für den Gebrauch in F vorgesehen sind#

### <a name="projecttoproject-referencing"></a>Projekt-zu-Projekt-Verweise

Die beste Möglichkeit, auf ein Projekt zu verweisen, ist wie folgt:

1. Stellen Sie sicher, dass das Projekt, auf das Sie verweisen möchten, einen guten Namen für den enthaltenden Ordner auf dem Datenträger trägt.  Dieser Name wird verwendet, um auf das Projekt zu verweisen.
2. Verweisen Sie in der `project.json`-Datei des genutzten Projekts auf den in (1) gewählten Namen, indem Sie `"target":"project"` angeben.

Die `project.json`-Dateien für **AwesomeLibrary.CSharp** und **AwesomeLibrary.FSharp** müssen nun auf **AwesomeLibrary.Core** als `project`-Ziel verweisen.  Wenn Sie nicht auf Zielversionen festlegen, können Sie den globalen Eintrag `dependencies` verwenden:

```json
{
    "dependencies":{
        "AwesomeLibrary.Core":{
            "target":"project"
        }
    }
}
```

Wenn Sie auf Zielversionen festlegen, können Sie möglicherweise keinen globalen `dependencies`-Eintrag verwenden, und müssen in einem `dependencies`-Eintrag auf Zielebene auf **AwesomeLibrary.Core** verweisen.  Wenn Sie z.B. `netstandard1.6` als Ziel gesetzt haben, können Sie wie folgt vorgehen:

```json
{
    "frameworks":{
        "netstandard1.6":{
            "dependencies":{
                "AwesomeLibrary.Core":{
                    "target":"project"
                }
            }
        }
    }
}
```

### <a name="structuring-a-solution"></a>Strukturieren einer Lösung

Ein weiterer wichtiger Aspekt bei mehreren Projekten in einer Projektmappe ist es, eine gute allgemeine Projektstruktur einzurichten. Sie müssen die Ordner `/src` und `/test` der obersten Ebene verwenden, um eine Bibliothek mit mehreren Projekten zu strukturieren:

```
/AwesomeLibrary
|__global.json
|__/src
   |__/AwesomeLibrary.Core
      |__Source Files
      |__project.json
   |__/AwesomeLibrary.CSharp
      |__Source Files
      |__project.json
   |__/AwesomeLibrary.FSharp
      |__Source Files
      |__project.json
|__/test
   |__/AwesomeLibrary.Core.Tests
      |__Test Files
      |__project.json
   |__/AwesomeLibrary.CSharp.Tests
      |__Test Files
      |__project.json
   |__/AwesomeLibrary.FSharp.Tests
      |__Test Files
      |__project.json
```

Die `global.json`-Datei für diese Lösung würde dann wie folgt aussehen:

```json
{
    "projects":["src", "test"]
}
```

Dieser Ansatz folgt dem gleichen Muster, das mit Projektvorlagen in der Befehlseinrichtung `dotnet new` eingerichtet wurde. In diesem Muster werden alle Projekte unter einem `/src`-Verzeichnis und alle Tests unter einem `/test`-Verzeichnis platziert.

So können Sie Pakete wiederherstellen, erstellen und Ihr gesamtes Projekt testen:

```
$ dotnet restore
$ cd src/AwesomeLibrary.FSharp
$ dotnet build
$ cd ../AwesomeLibrary.CSharp
$ dotnet build
$ cd ../../test/AwesomeLibrary.Core.Tests
$ dotnet test
$ cd ../AwesomeLibrary.CSharp.Tests
$ dotnet test
$ cd ../AwesomeLibrary.FSharp.Tests
$ dotnet test
```

Und das ist schon alles!



<!--HONumber=Nov16_HO3-->


