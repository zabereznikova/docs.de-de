---
title: Erstellen von .NET Core aus einer Quelle
description: Erfahren Sie, wie Sie .NET Core und .NET Core-CLI aus dem Quellcode erstellen.
author: bleroy
ms.date: 06/28/2017
ms.openlocfilehash: fe5431667d861d830c2ec56252e6e3e2ca08a866
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740920"
---
# <a name="build-net-core-from-source"></a>Erstellen von .NET Core aus einer Quelle

Die Möglichkeit, .NET Core aus dem Quellcode zu erstellen, ist auf verschiedene Weise wichtig: Es erleichtert das Portieren von .NET Core auf neue Plattformen, es ermöglicht Beiträge und Korrekturen des Produkts, und es ermöglicht das Erstellen von benutzerdefinierten Versionen von .NET.
Dieser Artikel enthält eine Anleitung für Entwickler, die ihre eigenen Versionen von .NET Core erstellen und verteilen möchten.

## <a name="build-the-clr-from-source"></a>Erstellen der CLR aus der Quelle

Den Quellcode für .NET CoreCLR finden Sie im Repository [dotnet/runtime](https://github.com/dotnet/runtime/) auf GitHub.

Der Build hängt derzeit von folgenden Voraussetzungen ab:

- [Git](https://git-scm.com/)
- [CMake](https://cmake.org/)
- [Python](https://www.python.org/)
- ein C++-Compiler.

Nach der Installation dieser Komponenten können Sie die CLR erstellen, indem Sie das Buildskript (`build.cmd` unter Windows oder `build.sh` unter Linux und macOS) an der Basis des Repositorys [dotnet/runtime](https://github.com/dotnet/runtime/) aufrufen.

Das Installieren der Komponenten unterscheidet sich je nach Betriebssystem. Weitere Informationen finden Sie in den Buildanweisungen Ihres Betriebssystems:

- [Windows](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
- [Linux](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
- [macOS](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
- [FreeBSD](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md)
- [NetBSD](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

Es gibt keine betriebssystemübergreifenden Erstellungen (nur für ARM, das in X64 erstellt wurde).  
Sie müssen sich auf der speziellen Plattform befinden, um diese Plattform zu erstellen.  

Der Build verfügt über zwei Haupt-`buildTypes`:

- Debuggen (Standard): Kompiliert die Runtime mit minimalen Optimierungen und zusätzlichen Überprüfungen der Runtime (Assert-Vorgänge). Diese minimierte Optimierungsstufe und die zusätzlichen Überprüfungen verlangsamen die Runtimeausführung, sind aber wichtig für das Debuggen. Dies ist die empfohlene Einstellung für Entwicklungs- und Testumgebungen.
- Release: Kompiliert die Runtime mit vollständigen Optimierungen, aber ohne die zusätzlichen Überprüfungen der Runtime. Dies führt zu einer wesentlich schnelleren Leistung der Runtime, die Erstellung des Builds kann jedoch länger dauern, und das Debuggen kann schwieriger sein. Übergeben Sie `release` an das Buildskript, um diesen Buildtyp auszuwählen.

Darüber hinaus erstellt der Build standardmäßig nicht nur ausführbare Dateien für die Runtime, sondern auch alle Tests.
Es gibt einige Tests, die viel Zeit in Anspruch nehmen, was jedoch nicht nötig ist, wenn Sie nur mit Änderungen experimentieren möchten.
Sie können die Testbuilds überspringen, indem Sie das Argument `skiptests` zum Buildskript hinzufügen, wie im folgenden Beispiel (ersetzen Sie `.\build` durch `./build.sh` auf Unix-Computern):

```bat
    .\build skiptests
```

Im vorherigen Beispiel wurde gezeigt, wie die `Debug`-Konfiguration erstellt wird, bei der Überprüfungen zur Entwicklungszeit (Assert-Vorgänge) und Optimierungen deaktiviert sind. Führen Sie folgende Schritte aus, um die Releasekonfiguration (volle Geschwindigkeit) zu erstellen:

```bat
    .\build release skiptests
```

Sie können mit „build“ weitere Buildoptionen finden, indem Sie den Qualifizierer „-?“ oder „-help“ verwenden.

### <a name="using-your-build"></a>Verwenden Ihres Builds

Der Build platziert alle seine generierten Dateien in das `bin`-Verzeichnis an der Basis des Repository.
Es gibt ein *bin\Log*-Verzeichnis, das während des Erstellungsvorgangs generierte Protokolldateien enthält (besonders hilfreich, wenn der Buildvorgang scheitert).
Die tatsächliche Ausgabe befindet sich in einem Verzeichnis *bin\Product\[Plattform].[CPU-Architektur].[Buildtyp]* , z.B. *bin\Product\Windows_NT.x64.Release*.

Während die „rohe“ Ausgabe des Builds in einigen Fällen nützlich ist, sind normalerweise nur die NuGet-Paketen für Sie von Interesse, die sich im Unterverzeichnis `.nuget\pkg` des vorherigen Ausgabeverzeichnisses befinden.

Es gibt zwei grundlegende Verfahren für die Verwendung der neuen Runtime:

 1. **Verwenden Sie zum Verfassen einer Anwendung „dotnet.exe“ und NuGet**.
    Unter [Using Your Build (Verwenden Ihres Builds)](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-your-build.md) finden Sie Anweisungen zum Erstellen eines Programms, das Ihre neue Runtime verwendet, indem es die NuGet-Pakete, die Sie zuvor erstellt haben, und die „dotnet“-CLI verwendet. Diese Technik ist die erwartete Methode, mit der Entwickler ohne Runtime wahrscheinlich Ihre neue Runtime nutzen.

 2. **Verwenden Sie „corerun.exe“ zum Ausführen einer Anwendung, die unverpackte DLLs verwendet**.
    Dieses Repository definiert außerdem einen einfachen Host mit dem Namen „corerun.exe“, der NICHT von NuGet abhängig ist.
    Sie müssen den Host darüber informieren, wo er die benötigten DLLs erhält, die Sie tatsächlich verwenden, und Sie müssen sie manuell sammeln.
    Diese Technik wird von allen Tests im Repository [dotnet/runtime](https://github.com/dotnet/runtime) verwendet und eignet sich zur schnellen lokalen „Bearbeiten-Kompilieren-Debuggen“-Schleife, z. B. für vorläufige Komponententests.
    Weitere Informationen zur Verwendung dieser Technik finden Sie unter [Executing .NET Core Apps with CoreRun.exe (Ausführen von .NET Core-Apps mit „CoreRun.exe“)](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-corerun.md).

## <a name="build-the-cli-from-source"></a>Erstellen der CLI aus der Quelle

Den Quellcode für die .NET Core-CLI finden Sie im Repository [dotnet/cli](https://github.com/dotnet/cli/) auf GitHub.

Um die .NET Core-CLI zu erstellen, müssen Sie Folgendes auf dem Computer installiert haben.

- Windows und Linux:
  - Git auf dem Pfad
- macOS:
  - Git auf dem Pfad
  - Xcode
  - OpenSSL

Führen Sie zum Erstellen `build.cmd` unter Windows oder `build.sh` unter Linux und macOS aus dem Stamm aus. Wenn Sie keine Tests ausführen möchten, führen Sie `build.cmd -t:Compile` oder `./build.sh -t:Compile` aus. Um die CLI unter macOS Sierra zu erstellen, müssen Sie die Umgebungsvariable DOTNET_RUNTIME_ID festlegen, indem Sie `export DOTNET_RUNTIME_ID=osx.10.11-x64` ausführen.

### <a name="using-your-build"></a>Verwenden Ihres Builds

Verwenden Sie die ausführbare Datei `dotnet` von *artifacts/{os}-{arch}/stage2*, um die neu erstellte CLI auszuprobieren. Wenn Sie beim Aufrufen von `dotnet` aus der aktuellen Konsole die Buildausgabe verwenden möchten, können Sie auch *artifacts/{os}-{arch}/stage2* zum Pfad hinzufügen.

## <a name="see-also"></a>Siehe auch

- [.NET Runtime](https://github.com/dotnet/runtime/blob/master/README.md)
- [.NET Core CLI Developer Guide (Entwicklerhandbuch für .NET Core-CLI)](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
- [.NET Core distribution packaging (Verpacken der Verteilung in .NET Core)](./distribution-packaging.md)
