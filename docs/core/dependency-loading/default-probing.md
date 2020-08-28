---
title: Standardüberprüfung – .NET Core
description: Übersicht über die Überprüfungslogik in System.Runtime.Loader.AssemblyLoadContext.Default von .NET Core zum Suchen von Abhängigkeiten.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608427"
---
# <a name="default-probing"></a>Standardüberprüfung

Die <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz ist für das Suchen der Abhängigkeiten einer Assembly verantwortlich. In diesem Artikel wird die Überprüfungslogik der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>-Instanz beschrieben.

## <a name="host-configured-probing-properties"></a>Vom Host konfigurierte Überprüfungseigenschaften

Wenn die Runtime gestartet wird, stellt der Laufzeithost eine Reihe von benannten Überprüfungseigenschaften bereit, mit denen die Testpfade im <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> konfiguriert werden.

Jede der Überprüfungseigenschaften ist optional. Ist eine Eigenschaft vorhanden, ist sie ein Zeichenfolgenwert, der eine durch Trennzeichen getrennte Liste absoluter Pfade enthält. Das Trennzeichen ist unter Windows „;“ und auf allen anderen Plattformen „:“.

|Eigenschaftenname                 |Beschreibung  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Liste der Plattform- und Anwendungsassembly-Dateipfade |
|`PLATFORM_RESOURCE_ROOTS`       | Liste der Verzeichnispfade für die Suche nach Satellitenressourcenassemblys |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Liste der Verzeichnispfade für die Suche nach nicht verwalteten (nativen) Bibliotheken        |
|`APP_PATHS`                     | Liste der Verzeichnispfade für die Suche nach verwalteten Assemblys |
|`APP_NI_PATHS`                  | Liste der Verzeichnispfade für die Suche nach nativen Images verwalteter Assemblys |

### <a name="how-are-the-properties-populated"></a>Wie werden diese Eigenschaften aufgefüllt?

Es gibt zwei Hauptszenarios für das Auffüllen der Eigenschaften, die davon abhängen, ob eine *\<myapp>.deps.json*-Datei vorhanden ist.

- Wenn eine *\*.deps.json*-Datei vorhanden ist, wird sie analysiert, um die Überprüfungseigenschaften aufzufüllen.
- Wenn keine *\*.deps.json*-Datei vorhanden ist, wird davon ausgegangen, dass alle Abhängigkeiten im Anwendungsverzeichnis enthalten sind. Der Inhalt des Verzeichnisses wird dann verwendet, um die Überprüfungseigenschaften aufzufüllen.

Außerdem werden die *\*.deps.json*-Dateien auf die gleiche Weise auf referenzierte Frameworks analysiert.

Schließlich kann auch die Umgebungsvariable `ADDITIONAL_DEPS` verwendet werden, um zusätzliche Abhängigkeiten hinzuzufügen.  `dotnet.exe` enthält auch einen optionalen `--additional-deps`-Parameter, um diesen Wert beim Anwendungsstart festzulegen.

Die Eigenschaften `APP_PATHS` und `APP_NI_PATHS` werden nicht standardmäßig aufgefüllt und für die meisten Anwendungen weggelassen.

Die Liste aller *\*.deps.json*-Dateien, die von der Anwendung verwendet werden, kann über `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")` aufgerufen werden.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Wie kann ich die Überprüfungseigenschaften von verwaltetem Code anzeigen?

Jede Eigenschaft ist über einen Aufruf der <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType>-Funktion mit dem Eigenschaftennamen aus der obigen Tabelle verfügbar.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Wie debugge ich die Erstellung der Überprüfungseigenschaften?

Der .NET Core-Laufzeithost gibt nützliche Ablaufverfolgungsmeldungen aus, wenn bestimmte Umgebungsvariablen aktiviert sind:

|Umgebungsvariable        |Beschreibung  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Aktiviert die Ablaufverfolgung|
|`COREHOST_TRACEFILE=<path>` |Gibt die Ablaufverfolgung in einem Dateipfad anstelle der Standardausgabe an `stderr` aus|
|`COREHOST_TRACE_VERBOSITY`  |Legt die Ausführlichkeit zwischen 1 (niedrigste) und 4 (höchste) fest|

## <a name="managed-assembly-default-probing"></a>Standardüberprüfung verwalteter Assemblys

Beim Überprüfen einer verwalteten Assembly sucht der <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> in der folgenden Reihenfolge:

- Dateien, die mit dem <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` übereinstimmen (nach dem Entfernen von Dateierweiterungen)
- Assemblydateien für native Images in `APP_NI_PATHS` mit allgemeinen Dateierweiterungen
- Assemblydateien in `APP_PATHS` mit allgemeinen Dateierweiterungen

## <a name="satellite-resource-assembly-probing"></a>Überprüfungen von Satellitenassemblys (Ressourcen)

Um eine Satellitenassembly für eine bestimmte Kultur zu suchen, erstellen Sie einen Satz von Dateipfaden.

Fügen Sie für jeden Pfad in `PLATFORM_RESOURCE_ROOTS` und dann `APP_PATHS` die Zeichenfolge <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, ein Verzeichnistrennzeichen, die Zeichenfolge <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> und die Erweiterung „.dll“ an.

Wenn eine übereinstimmende Datei vorhanden ist, versuchen Sie, diese zu laden und zurückzugeben.

## <a name="unmanaged-native-library-probing"></a>Überprüfung nicht verwalteter (nativer) Bibliotheken

Bei einer Überprüfung einer nicht verwalteten Bibliothek werden die `NATIVE_DLL_SEARCH_DIRECTORIES` nach einer übereinstimmenden Bibliothek durchsucht.
