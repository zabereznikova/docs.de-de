---
title: Migrieren von DNX zur .Net Core-CLI
description: Migrieren der Verwendung von DNX-Tools zu .NET Core-CLI-Tools.
ms.date: 06/20/2016
ms.openlocfilehash: e15e7ce10bb7a36deb2acd2abb9a0bd4ec8cd4a9
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920627"
---
# <a name="migrating-from-dnx-to-net-core-cli-projectjson"></a>Migrieren von DNX zur .NET Core-CLI (project.json)

## <a name="overview"></a>Übersicht
Im RC1-Release von .NET Core und ASP.NET Core 1.0 wurde DNX eingeführt. Im RC2-Release von .NET Core und ASP.NET Core 1.0 wurde der Wechsel von DNX auf die NET Core-CLI vollzogen.

Lassen Sie uns als kurze Auffrischung noch einmal zusammenfassen, worum es bei DNX ging. DNX war eine Laufzeit und ein Toolset, das zum Erstellen von .NET Core und, genauer gesagt, ASP.NET Core 1.0-Anwendungen verwendet wurde. DNX bestand aus 3 Hauptteilen:

1. DNVM – ein Installationsskript zum Abrufen von DNX
2. DNX (Dotnet Execution Runtime) – die Laufzeit, die Ihren Code ausführt
3. DNU (Dotnet Developer Utility) – Tools zum Verwalten von Abhängigkeiten, Erstellen und Veröffentlichen Ihrer Anwendungen

Mit der Einführung der CLI (command line interface, Befehlszeilenschnittstelle) sind alle oben genannten Teile jetzt Bestandteil eines einzigen Toolsets. Nachdem DNX im RC1-Zeitrahmen verfügbar war, könnten Sie allerdings noch über Projekte verfügen, die mit DNX erstellt wurden, und die Sie möglicherweise zu den neuen CLI-Tools verschieben möchten.

Dieses Migrationshandbuch behandelt die Grundlagen, wie Sie Projekte weg von DNX und zur .NET Core-CLI migrieren können. Wenn Sie ein Projekt auf .NET Core von Grund auf neu erstellen, können Sie dieses Dokument getrost überspringen.

## <a name="main-changes-in-the-tooling"></a>Wichtigste Änderungen in den Tools
Es gibt einige allgemeine Änderungen in den Tools, die zuerst ausgeführt werden sollten.

### <a name="no-more-dnvm"></a>DNVM ist nicht mehr vorhanden
DNVM, kurz für *DotNet Version Manager* war ein Bash/PowerShell-Skript mit dem ein DNX auf Ihrem Computer installiert wurde. Benutzer konnten dadurch das benötigte DNX von einem von ihnen angegebenen Feed (oder Standard-Feeds) erhalten sowie ein bestimmtes DNX als „aktiv“ markieren, das $PATH für die jeweilige Sitzung als Umgebungsvariable setzte. Dies ermöglichte die Nutzung der verschiedenen Tools.

DNVM wurde eingestellt, da die zugehörigen Features durch die Änderungen in der .NET Core-CLI überflüssig wurden.

Die CLI wird in zwei Paketen angeboten:

1. Native Installationsprogramme für eine bestimmte Plattform
2. Installationsskript für andere Situationen (wie CI-Server)

Angesichts dessen werden die Installationsfeatures von DNVM nicht benötigt. Was ist aber mit den Features zur Auswahl von Laufzeiten?

Sie verweisen auf eine Laufzeit in Ihrer `project.json`-Datei, indem Sie ein Paket einer bestimmten Version zu Ihren Abhängigkeiten hinzufügen. Durch diese Änderung kann die Anwendung die neuen Laufzeit-Bits verwenden. Diese Bits auf Ihren Computer zu verschieben ist der gleiche Prozess wie bei der CLI: Sie installieren die Laufzeit über eines der unterstützten nativen Installationsprogramme oder das Installationsskript.

### <a name="different-commands"></a>Unterschiedliche Befehle
Wenn Sie DNX verwendet haben, haben Sie bisher einige Befehle aus einem der drei Teile genutzt (DNX, DNU oder DNVM). Mit der CLI ändern sich manche dieser Befehle, manche sind nicht mehr verfügbar und manche bleiben gleich, verfügen jedoch über eine etwas andere Semantik.

Die folgende Tabelle stellt die Zuordnung zwischen DNX-/DNU-Befehlen und ihren CLI-Gegenstücken dar.

| DNX-Befehl                    | CLI-Befehl    | Beschreibung                                                                                                     |
|--------------------------------|----------------|-----------------------------------------------------------------------------------------------------------------|
| dnx run                        | dotnet run     | Code aus Quelle ausführen.                                                                                           |
| dnu build                      | dotnet build   | Erstellen einer IL-Binärdatei des Codes.                                                                                |
| dnu pack                       | dotnet pack    | Verpacken eines NuGet-Pakets Ihres Codes.                                                                        |
| dnx \[command] (z.B. „dnx web“) | NICHT VERFÜGBAR\*          | In DNX, Ausführen eines Befehls wie in der Datei „project.json“ definiert.                                                     |
| dnu install                    | NICHT VERFÜGBAR\*          | In DNX, Installieren eines Pakets als Abhängigkeit.                                                            |
| dnu restore                    | dotnet restore | Wiederherstellen von Abhängigkeiten, die in der Datei „project.json“ angegeben sind. ([Siehe Hinweis](#dotnet-restore-note))                                                            |
| dnu publish                    | dotnet publish | Veröffentlichen Ihrer Anwendung für die Bereitstellung in einer der drei Formen (portabel, portabel-nativ und eigenständig). |
| dnu wrap                       | NICHT VERFÜGBAR\*          | In DNX, Umschließen von „project.json“ in „csproj“.                                                                    |
| dnu commands                   | NICHT VERFÜGBAR\*          | In DNX, Verwalten der global installierten Befehle.                                                           |

(\*) – diese Features werden in der CLI nicht unterstützt (dies ist beabsichtigt).

## <a name="dnx-features-that-are-not-supported"></a>DNX-Features, die nicht unterstützt werden
Wie in der obigen Tabelle gezeigt, gibt es Features in DNX, die absichtlich nicht in der CLI unterstützt werden, zumindest für den Moment. In diesem Abschnitt werden die wichtigsten Features aufgezählt und die Gründe, warum diese nicht unterstützt werden, beschrieben. Außerdem wird beschrieben, wie Sie dies umgehen können, falls Sie die Features benötigen.

### <a name="global-commands"></a>Globale Befehle
In DNU war ein Konzept namens „globale Befehle“ enthalten. Im Wesentlichen waren dies Konsolenanwendungen, die als NuGet Pakete mit einem Shell-Skript verpackt waren, und das angegebene DNX aufriefen, die Sie zum Ausführen der Anwendung angegeben hatten.

Dieses Konzept wird in CLI nicht unterstützt. CLI unterstützt jedoch das Konzept, Befehle pro Projekt hinzuzufügen, die mithilfe der bekannten Syntax `dotnet <command>` aufgerufen werden können.

### <a name="installing-dependencies"></a>Installieren von Abhängigkeiten
In V1 enthält die .NET Core-CLI keinen `install`-Befehl zum Installieren von Abhängigkeiten. Wenn Sie ein Paket von NuGet installieren möchten, müssen Sie es als Abhängigkeit zu Ihrer Datei `project.json` hinzufügen und dann `dotnet restore` ausführen ([siehe Hinweis](#dotnet-restore-note)).

### <a name="running-your-code"></a>Ausführen des Codes
Im Wesentlichen gibt es zwei Möglichkeiten, den Code auszuführen. Eine Möglichkeit ist das Ausführen von der Quelle mit dem Befehl `dotnet run`. Im Gegensatz zu `dnx run` führt dieser keine Kompilierung im Speicher durch. Stattdessen wird `dotnet build` aufgerufen, um den Code zu erstellen und dann die erstellte Binärdatei auszuführen.

Eine andere Möglichkeit ist das Verwenden von `dotnet` selbst zum Ausführen des Codes. Dies erfolgt durch das Bereitstellen eines Pfads zu Ihrer Assembly: `dotnet path/to/an/assembly.dll`.

## <a name="migrating-your-dnx-project-to-net-core-cli"></a>Migrieren Ihres DNX-Projekts zur .NET Core-CLI
Zusätzlich zur Nutzung von neuen Befehlen, wenn Sie mit Code arbeiten, gibt es noch drei weitere wichtige Punkte beim Migrieren von DNX:

1. Migrieren Sie die Datei `global.json` (wenn diese vorhanden ist) um CLI (Command Line Interface, Befehlszeilenschnittstelle) verwenden zu können.
2. Migrieren der Projektdatei (`project.json`) selbst zu den CLI-Tools.
3. Migrieren weg von beliebigen DNX-APIs zu ihren BLC-Entsprechungen.

### <a name="changing-the-globaljson-file"></a>Ändern der Datei „global.json“
Die Datei `global.json` verhält sich wie eine Projektmappendatei für RC1- und RC2- Projekte (oder höhere). Damit die .NET Core-CLI (wie auch Visual Studio) zwischen RC1 und höheren Versionen unterscheiden kann, verwendet sie die Eigenschaft `"sdk": { "version" }`, um zu ermitteln, welches Projekt RC1 oder höher ist. Wenn `global.json` nicht über diesen Knoten verfügt, wird davon ausgegangen, dass die höchste Version verwendet wird.

Entfernen Sie entweder die Eigenschaft, um die Datei `global.json` zu aktualisieren, oder stellen Sie sie auf die genaue Version der Tools ein, die Sie verwenden möchten, in diesem Fall **1.0.0-preview2-003121**:

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```

### <a name="migrating-the-project-file"></a>Migrieren der Projektdatei

Die CLI und DNX verwenden dasselbe grundlegende Projektsystem basierend auf der Datei `project.json`. Die Syntax und Semantik der Projektdatei sind weitgehend identisch, abgesehen von kleinen Unterschieden abhängig von den Szenarios. Es gibt auch einige Änderungen am Schema, die Sie in der [Schemadatei](http://json.schemastore.org/project) einsehen können.

Wenn Sie eine Konsolenanwendung erstellen, müssen Sie den folgenden Ausschnitt zu Ihrer Projektdatei hinzufügen:

```json
"buildOptions": {
    "emitEntryPoint": true
}
```

Dies weist `dotnet build` an, einen Einstiegspunkt für Ihre Anwendung auszugeben, und macht Ihren Code dadurch ausführbar. Wenn Sie eine Klassenbibliothek erstellen, lassen Sie einfach den obigen Abschnitt aus. Sobald Sie den oben angezeigten Ausschnitt zu Ihrer Datei `project.json` hinzugefügt haben, müssen Sie natürlich einen statischen Einstiegspunkt hinzufügen. Mit dem Wechsel weg von DNX sind die DI-Dienste nicht mehr verfügbar, deswegen muss ein einfacher .NET-Einstiegspunkt hinzugefügt werden: `static void Main()`.

Wenn sich ein Abschnitt „commands“ in Ihrer Datei `project.json` befindet, können Sie ihn entfernen. Manche der Befehle, die es als DNU-Befehle gab, zum Beispiel Entity Framework-CLI-Befehle, werden als pro Projekt-Erweiterung in die CLI portiert. Falls Sie eigene Befehle erstellt haben, die Sie in Ihren Projekten verwenden, müssen Sie diese mit der CLI-Erweiterung ersetzen. In diesem Fall muss der Knoten `commands` in der Datei `project.json` durch den Knoten `tools` ersetzt werden, und muss die Tool-Abhängigkeiten auflisten.

Nachdem diese Schritte abgeschlossen sind, müssen Sie entscheiden, über welche Art von Portabilität Ihre App verfügen soll. Wir haben mit .NET Core darin investiert, Ihnen eine Bandbreite von Optionen zur Portabilität anzubieten, aus denen Sie auswählen können. Sie können zum Beispiel zwischen einer voll *portablen* Anwendung oder einer *eigenständigen* Anwendung wählen. Die Option für die portable Anwendung entspricht eher der Arbeitsweise von .NET Framework-Anwendungen: Sie benötigt eine freigegebene Komponente, um sie auf dem Zielcomputer (.NET Core) auszuführen. Bei der eigenständigen Anwendung muss .NET Core nicht auf dem Zielcomputer installiert werden. Sie müssen allerdings für jedes Betriebssystem, das Sie unterstützen möchten, eine Anwendung erzeugen. Genauere Informationen zu diesen und weiteren Arten der Portabilität finden Sie im Dokument [application portability type (Typen der Portabilität von Anwendungen) ](../deploying/index.md).

Sobald Sie sich für eine Art der Portabilität entschieden haben, müssen Sie Ihr(e) Zielframework(s) ändern. Wenn Sie Anwendungen für .NET Core geschrieben haben, haben Sie wahrscheinlich `dnxcore50` als Zielframework verwendet. Aufgrund der CLI und der Änderungen durch den neuen [.NET-Standard](../../standard/net-standard.md) muss eines der folgenden Frameworks verwendet werden:

1. `netcoreapp1.0` – wenn Sie Anwendungen in .NET Core (einschließlich ASP.NET Core-Anwendungen) schreiben
2. `netstandard1.6` – wenn Sie Klassenbibliotheken für .NET Core schreiben

Wenn Sie andere `dnx`-Ziele verwenden, wie z.B. `dnx451`, müssen diese ebenfalls geändert werden. `dnx451` sollte in `net451` geändert werden.
Weitere Informationen finden Sie im Thema [.NET Standard](../../standard/net-standard.md).

Ihre Datei `project.json` ist nun weitgehend bereit. Sie müssen nun Ihre Liste der Abhängigkeiten durchgehen und die Abhängigkeiten auf deren neuere Versionen aktualisieren, besonders, wenn Sie Abhängigkeiten von ASP.NET Core verwenden. Wenn Sie separate Pakete für BLC APIs verwenden, können Sie das Laufzeitpaket verwenden, wie im Dokument [application portability type (Arten der Portabilität von Anwendungen)](../deploying/index.md) erklärt.

Sobald Sie bereit sind, können Sie eine Wiederherstellung mit `dotnet restore` ausführen ([siehe Hinweis](#dotnet-restore-note)). Je nach Version Ihrer Abhängigkeiten könnten Fehler auftreten, wenn NuGet die Abhängigkeiten für eines der oben genannten Zielframeworks nicht lösen kann. Dies ist ein „Zeitpunkt“-Problem; im Lauf der Zeit werden immer mehr Pakete eine Unterstützung dieser Frameworks bieten. Wenn dieses Problem auftritt, können Sie vorläufig die Anweisung `imports` innerhalb des Knotens `framework` verwenden, um NuGet mitzuteilen, dass es die Pakete, die das Framework als Ziel haben, innerhalb der „imports“-Anweisung wiederherstellen kann.
Die Fehler beim Wiederherstellen, die in diesem Fall auftreten, sollten genügend Informationen bereitstellen, damit Sie entscheiden können, welches Framework Sie importieren müssen. Wenn Sie sich hiermit nicht auskennen behebt normalerweise auch das Angeben von `dnxcore50` und `portable-net45+win8` in der `imports`-Anweisung das Problem. Der folgende JSON-Ausschnitt zeigt, wie dies aussieht:

```json
    "frameworks": {
        "netcoreapp1.0": {
            "imports": ["dnxcore50", "portable-net45+win8"]
        }
    }
```

Das Ausführen von `dotnet build` zeigt mögliche Buildfehler an, auch wenn es nicht zu viele geben sollte. Wenn Ihr Code ordnungsgemäß erstellt und ausgeführt wird, können Sie ihn ohne Runner testen. Führen Sie `dotnet <path-to-your-assembly>` aus, und beobachten Sie die Ausführung.

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
