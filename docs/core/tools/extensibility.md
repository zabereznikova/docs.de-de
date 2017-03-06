---
title: .NET Core-CLI-Erweiterbarkeitsmodell | Microsoft-Dokumentation
description: .NET Core-CLI-Erweiterbarkeitsmodell
keywords: CLI, Erweiterbarkeit, benutzerdefinierte Befehle, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 1bebd25a-120f-48d3-8c25-c89965afcbcd
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 0a136e69e103994a69084b09f481489880d5df42

---

# <a name="net-core-cli-extensibility-model"></a>.NET Core-CLI-Erweiterbarkeitsmodell 

> [!WARNING]
> Dieses Thema gilt für .NET Core Preview 2-Tools. Informationen zur .NET Core Tools RC4-Version finden Sie im Thema [.NET Core-CLI-Erweiterbarkeitsmodell (.NET Core Tools RC4)](../preview3/tools/extensibility.md).

## <a name="overview"></a>Übersicht
In diesem Dokument werden die Hauptverfahren beschrieben, mit denen die CLI-Tools erweitert werden, und die Szenarios erläutert, die jedes dieser Tools antreiben. Es wird dargestellt, wie die Tools genutzt werden sollen und wie beide Arten der Tools erstellt werden. 

## <a name="how-to-extend-cli-tools"></a>So können Sie CLI-Tools erweitern
Die CLI-Tools können auf zwei Arten erweitert werden:

1. Projektweise über NuGet-Pakete
2. Über den SYSTEMPFAD

Die beiden oben beschriebenen Erweiterbarkeitsmechanismen schließen sich nicht gegenseitig aus; Sie können beide oder nur einen verwenden. Welchen Sie auswählen, hängt größtenteils davon ab, welches Ziel Sie mit der Erweiterung erreichen möchten.

## <a name="per-project-based-extensibility"></a>Erweiterbarkeit pro Projekt
Tools pro Projekt sind [tragbare Konsolenanwendungen](../deploying/index.md), die als NuGet-Pakete verteilt werden. Tools sind nur im Kontext des Projekts, das auf sie verweist, und für das sie wiederhergestellt werden, verfügbar. Ein Aufruf außerhalb des Projektkontexts (beispielsweise außerhalb des Verzeichnisses, das das Projekt enthält) schlägt fehl, da der Befehl nicht gefunden werden kann.

Diese Tools sind auch ideal für Buildserver, da außer `project.json` nichts erforderlich ist. Der Buildprozess führt die Wiederherstellung für das Projekt, das es erstellt, aus, und die Tools stehen zur Verfügung. Sprachprojekte, wie F#, befinden sich auch in dieser Kategorie. Immerhin kann jedes Projekt nur in einer bestimmten Sprache geschrieben werden. 

Schließlich bietet dieses Erweiterbarkeitsmodell Unterstützung für die Erstellung von Tools, die Zugriff auf die Buildausgabe des Projekts benötigen. Verschiedene Razor-Ansicht-Tools in [ASP.NET](https://www.asp.net/)-MVC-Anwendungen fallen z.B. in diese Kategorie. 

### <a name="consuming-per-project-tools"></a>Tools pro Projekt verwenden
Wenn Sie diese Tools verwenden, müssen Sie einen `tools`-Knoten zu Ihrem `project.json` hinzufügen. Innerhalb des `tools`-Knotens verweisen Sie auf das Paket, in dem sich das Tool befindet. Nach der Ausführung von `dotnet restore` werden das Tool und die zugehörigen Abhängigkeiten wiederhergestellt. 

Für Tools, die die Buildausgabe des Projekts zur Ausführung laden müssen, gibt es normalerweise eine andere Abhängigkeit, die unter den regulären Abhängigkeiten in der Projektdatei angezeigt wird. Dies bedeutet, dass Tools, mit denen Projektcodes geladen werden, zwei Komponenten haben: 

1. Die wichtigste aufrufende Instanz des „Tools“
2. Eine beliebige Anzahl anderer Tools, die die Logik enthalten, mit der gearbeitet wird 

Warum zwei Komponenten? Tools, die die Buildausgabe eines Projekts laden müssen, benötigen ein einheitliches Abhängigkeitsdiagramm mit dem Projekt, an dem sie arbeiten. Indem das Abhängigkeits-Bit hinzugefügt wird, aktivieren wir NuGet, diese Abhängigkeiten als einheitliches Diagramm aufzulösen. Die aufrufende Instanz ist vorhanden, um den Speicherort sowie die Frameworks des Abhängigkeitstools zu bestimmen. Die aufrufende Instanz kann alle Argumente zur Umleitung akzeptieren (`-c`, `-o`, `-b`), die der Benutzer angibt und findet das Abhängigkeitstool. Sie kann auch jegliche Richtlinien implementieren, in Fällen, in denen mehrere Abhängigkeitstools für mehrere Frameworks vorhanden sind (werden alle ausgeführt, oder nur ein einziges, usw.) Im Allgemeinen kann Logik zwischen diesen beiden Tools so wie erforderlich freigegeben werden. 

Betrachten wir ein Beispiel, bei dem ein Tools-Only-Tool zu einem einfachen Projekt hinzugefügt wird. Für einen Beispielbefehl namens `dotnet-api-search`, mit dem Sie die NuGet-Pakete nach der angegebenen API durchsuchen können, sehen Sie hier die `project.json`-Datei einer Konsolenanwendung, die dieses Tool verwendet:

```json
{
    "version": "1.0.0",
    "compilationOptions": {
        "emitEntryPoint": true
    },
    "dependencies": {
        "Microsoft.NETCore.App": {
            "type": "platform",
            "version": "1.0.0"
        }
    },
    "tools": {
        "dotnet-api-search": {
            "version": "1.0.0",
            "imports": ["dnxcore50"]
        }
    },
    "frameworks": {
        "netcoreapp1.0": {}
    }
}
```

Der `tools`-Knoten weist eine ähnliche Struktur auf wie der `dependencies`-Knoten. Er benötigt mindestens die Paket-ID des Pakets mit dem Tool und dessen Version. Im obigen Beispiel sehen wir eine weitere Anweisung: `imports`. Dies beeinflusst den Wiederherstellungsprozess des Tools und gibt an, dass das Tool zusätzlich zu jeglichen gezielten Frameworks, über die das Tool verfügt, auch mit dem `dnxcore50`-Ziel kompatibel ist. Weitere Informationen finden Sie im [project.json reference (Verweis project.json)](project-json.md).

### <a name="building-tools"></a>Erstellen von Tools
Wie bereits erwähnt, sind Tools nur portable Konsolenanwendungen. Sie würden eins erstellen, so wie Sie alle Konsolenanwendungen erstellen würden. Nachdem Sie es erstellt haben, würden Sie den [`dotnet pack`](dotnet-pack.md)-Befehl ausführen, um ein NuGet-Paket (Nupkg) zu erstellen, das Ihren Code, die Informationen zu seinen Abhängigkeiten usw. enthält. Der Verfasser kann den Paketnamen bestimmen, aber die Anwendung darin, das tatsächliche Binär-Tool, muss der `dotnet-<command>`-Konvention entsprechen, damit `dotnet` es aufrufen kann. 

Da Tools portable Anwendungen sind, benötigt der Benutzer des Tools die Version der .NET Core-Bibliotheken, für die das Tool entwickelt wurde, um das Tool auszuführen. Jede andere Abhängigkeit, die das Tool verwendet und nicht in den .NET Core-Bibliotheken enthalten ist, wird wiederhergestellt und im NuGet-Cache gespeichert. Das gesamte Tool wird daher mithilfe der Assemblys aus den .NET Core-Bibliotheken sowie Assemblys aus dem NuGet-Cache ausgeführt. 

Diese Art von Tools haben ein Abhängigkeitsdiagramm, das komplett unabhängig ist vom Abhängigkeitsdiagramm des Projekts, welches sie verwendet. Der Wiederherstellungsvorgang wird zuerst die Projektabhängigkeiten wiederherstellen und dann jedes der Tools und deren Abhängigkeiten. 

Umfangreichere Beispiele und verschiedene Kombinationen dessen finden Sie im [.NET Core-CLI-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestProjects). Sie finden auch die [Implementierung von verwendeten Tools](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages) im gleichen Repository. 

Die Erstellung von Tools, die Buildausgaben für die Ausführung des Projekts laden, weicht etwas davon ab. Wie bereits erwähnt, gibt es für diese Tool-Arten zwei Komponenten:

1. Ein Dispatcher-Tool, das der Benutzer aufruft
2. Eine Framework-spezifische Abhängigkeit, die die Logik zum Suchen der Buildausgaben und was damit zu erledigen ist, enthält

Ein gutes Beispiel dafür sind [Entity Framework (EF)](https://github.com/aspnet/EntityFramework)-Befehle sowie der [`dotnet test`](dotnet-test.md)-Befehl. In beiden Fällen gibt es ein Tool, auf das im `tools`-Knoten des `project.json` verwiesen wird und das der wichtigste Verteiler ist. Der Benutzer ruft dieses Tool in der Befehlszeile auf. Das zweite Puzzleteil ist die Abhängigkeit, die in den Hauptabhängigkeiten des Projekts angegeben ist (entweder Stammabhängigkeiten oder Framework-spezifische Abhängigkeiten). Dieses Paket enthält die eigentliche Logik des Tools. Das Paket ist eine normale Abhängigkeit, und wird daher im Rahmen des Wiederherstellungsvorgangs für das Projekt wiederhergestellt werden. 

Im Gegensatz zu vorherigen Tools sind diese Tools tatsächlich Teil des Diagramms des Projekts, das sie verwendet. Dies ist der Fall, da sie Zugriff auf den Projektcode und möglicherweise auch auf alle Abhängigkeiten benötigen. Beispielsweise benötigen die EF-Tools dies, da sie die Assemblys überprüfen müssen, um den Code, den sie brauchen, zu finden, wie z.B. Migrationen.  

Diese zweigeteilte Lösung besteht außerdem auch, damit ein saubereres Aufrufmodell zugelassen werden kann. Die meisten CLI-Befehle, mit denen bestimmte Elemente auf dem Datenträger abgelegt werden (z.B. `dotnet build`, `dotnet publish`), ermöglichen es Benutzern, die Ausgaben an einen anderen Pfad umzuleiten, indem sie das `--output`- oder das `--build-base-path`- oder das `--configuration`-Argument nutzen. Sie müssten die gleichen Argumente mit den gleichen Werten *sowohl* für den `dotnet`-Treiber als auch den `ef`-Befehl bereitstellen, damit EF-Tools z.B. die Buildausgabe Ihres Projekts finden können. Mit dem Aufrufmodell übergeben die Benutzer jegliche Argumente an das Dispatcher-Tool, das damit dann die erforderliche Binärdatei finden kann, die die Logik in den Ausgabeverzeichnisse enthält. 

Ein gutes Beispiel für diesen Ansatz finden Sie im [.NET Core-CLI-Repository](https://github.com/dotnet/cli):

* [Beispieldatei project.json](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/TestAssets/DesktopTestProjects/AppWithDirectDependencyDesktopAndPortable/project.json)
* [Implementierung des Dispatchers](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages/dotnet-dependency-tool-invoker)
* [Implementierung der Framework-spezifischen Abhängigkeit](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages/dotnet-desktop-and-portable)


### <a name="path-based-extensibility"></a>PFAD-basierte Erweiterbarkeit
Die PFAD-basierte Erweiterbarkeit wird in der Regel für Entwicklungscomputer verwendet, bei denen Sie ein Tool brauchen, das konzeptionell mehr als ein einzelnes Projekt abdeckt. Der größte Nachteil dieses Extensionsmechanismus ist, dass es mit dem Computer verknüpft ist, auf dem das Tool existiert. Wenn Sie ihn auf einem anderen Computer benötigen, müssten Sie ihn bereitstellen.

Dieses Muster der Erweiterbarkeit des CLI-Toolsets ist sehr einfach. Wie in der [Übersicht über die .NET Core-CLI](index.md) beschrieben, kann der `dotnet`-Treiber jeden Befehl ausführen, der nach der `dotnet-<command>`-Konvention benannt ist. Die Standardaufkösungslogik wird zuerst mehrere Speicherorte überprüfen und schließlich an den SYSTEMPFAD fallen. Wenn der angeforderte Befehl im SYSTEMPFAD vorhanden und eine Binärdatei ist, die aufgerufen werden kann, wird sie der `dotnet`-Treiber aufrufen. 

Die Binärdatei kann nahezu alles sein, das vom Betriebssystem ausgeführt werden kann. Auf Unix-Systemen bedeutet dies alles, das das ausführbare Bit über `chmod +x` festgelegt hat. Auf Windows bedeutet dies alles, das Windows ausführen kann. 

Als Beispiel sehen wir uns eine sehr einfache Implementierung eines `dotnet clean`-Befehls an. Wir verwenden `bash`, um den Befehl zu implementieren. Der Befehl löscht einfach die `bin/`- und `obj/`-Verzeichnisse im aktuellen Verzeichnis. Wenn das `--lock`-Argument übergeben wird, wird es auch die `project.lock.json`-Datei löschen. Der gesamte Befehl wird unten angezeigt. 

```bash
#!/bin/bash

# Delete the bin and obj dirs
rm -rf bin/ obj/

LOCK_FILE=$1
if [[ "$LOCK_FILE" = "--lock" ]]; then
    rm project.lock.json
fi


echo "Cleaning complete..."
```

Auf Mac OS können wir dieses Skript als `dotnet-clean` speichern und sein ausführbares Bit mit `chmod +x dotnet-clean` festlegen. Wir erstellen dann eine symbolische Verknüpfung in `/usr/local/bin` mit dem Befehl `ln -s dotnet-clean /usr/local/bin/`. So kann der Befehl „Bereinigen“ mit der `dotnet clean`-Syntax aufgerufen werden. Sie können dies testen, indem Sie eine App erstellen, `dotnet build` und anschließend `dotnet clean` darauf ausführen. 

## <a name="conclusion"></a>Schlussfolgerung
Die .NET Core CLI-Tools lassen zwei wichtige Erweiterungspunkte zu. Die Tools pro Projekt sind im Kontext des Projekts enthalten, aber sie ermöglichen eine einfache Installation über die Wiederherstellung. PFAD-basierte Tools eignen sich für allgemeine projektübergreifende Tools, die auf einem einzelnen Computer verwendet werden. 



<!--HONumber=Feb17_HO2-->


