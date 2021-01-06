---
title: Schreiben eines benutzerdefinierten .NET Core-Laufzeithosts
description: Erfahren Sie, wie Sie die.NET Core-Runtime vom nativen Code aus hosten können, um erweiterte Szenarien zu unterstützen, die eine Kontrolle der Funktionsweise der.NET Core-Runtime erfordern.
author: mjrousos
ms.topic: how-to
ms.date: 12/21/2018
ms.openlocfilehash: 358cbff1ded3bd4ee9a3f78965eac1e1b1883ede
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633845"
---
# <a name="write-a-custom-net-core-host-to-control-the-net-runtime-from-your-native-code"></a>Schreiben Sie einen benutzerdefinierten .NET Core-Host, um die .NET-Runtime über den systemeigenen Code zu steuern.

Wie alle verwalteten Codes werden .NET Core-Anwendungen von einem Host ausgeführt. Der Host ist für das Starten der Runtime (einschließlich Komponenten wie die JIT und Garbage Collector) und das Aufrufen von verwalteten Einstiegspunkten verantwortlich.

Das Hosten der Laufzeit von .NET Core ist ein erweitertes Szenario, und in den meisten Fällen brauchen sich .NET Core-Entwickler nicht darum kümmern, da die Buildprozesse von .NET Core einen Standardhost bereitstellen, der die .NET Core-Anwendungen ausführt. Unter speziellen Umständen kann es jedoch hilfreich sein, die .NET Core-Laufzeit explizit zu hosten, entweder als Mittel zum Aufrufen von verwalteten Codes in einem nativen Prozess oder um mehr Kontrolle über die Funktionsweise der Laufzeit zu erhalten.

Dieser Artikel bietet einen Überblick über die erforderlichen Schritte zum Starten der .NET Core-Runtime aus nativem Code und für das Ausführen von darin enthaltenem verwalteten Code.

## <a name="prerequisites"></a>Voraussetzungen

Da Hosts native Anwendungen sind, wird in diesem Tutorial das Erstellen einer C++-Anwendung zum Hosten von .NET Core behandelt. Sie benötigen eine C++-Entwicklungsumgebung (z.B. von [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)).

Sie sollten außerdem über eine einfache .NET Core-Anwendung zum Testen des Hosts verfügen, daher sollten Sie die [.NET Core SDK](https://dotnet.microsoft.com/download) installieren und [eine kleine .NET Core-Testanwendung erstellen](with-visual-studio.md) (z.B. die Anwendung „Hello World“). Die „Hello World“-Anwendung, die von der neuen Projektvorlage der .NET Core-Konsole erstellt wird, ist ausreichend.

## <a name="hosting-apis"></a>Hosting-APIs

Sie können zwei verschiedene APIs verwenden, um .NET Core zu hosten. In diesem Artikel (und den zugehörigen [Beispielen](https://github.com/dotnet/samples/tree/master/core/hosting)) werden diese beiden Optionen behandelt.

* Die bevorzugte Methode zum Hosten der .NET Core-Runtime ab .NET Core 3.0 ist mithilfe der APIs der Bibliotheken `nethost` und `hostfxr`. Diese Einstiegspunkte bewältigen die Komplexität des Auffindens und Einrichtens der Runtime für die Initialisierung und ermöglichen sowohl das Starten einer verwalteten Anwendung als auch das Aufrufen einer statischen verwalteten Methode.
* Die API [`coreclrhost.h`](https://github.com/dotnet/runtime/blob/master/src/coreclr/hosts/inc/coreclrhost.h) wird jedoch bei früheren Versionen als .NET Core 3.0 bevorzugt für das Hosten der .NET Core-Runtime verwendet. Diese API enthält Funktionen, mit denen Sie die Runtime einfach starten und beenden können und verwalteten Code aufrufen können, indem Sie entweder eine entsprechende ausführbare Datei ausführen oder verwaltete statische Methoden aufrufen.

## <a name="sample-hosts"></a>Beispielhosts

[Beispielhosts](https://github.com/dotnet/samples/tree/master/core/hosting) zur Veranschaulichung der Schritte in diesen Tutorials sind im GitHub-Repository „dotnet/samples“ auf verfügbar. Durch die Kommentare in den Beispielen werden die nummerierten Schritte in diesem Tutorial ihrer Position im Beispiel eindeutig zugeordnet. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#view-and-download-samples).

Bedenken Sie, dass die Beispielhosts zu Lernzwecken gedacht und somit bei der Fehlerüberprüfung nachsichtig sind. Die Lesbarkeit steht in diesem Fall über der Effizienz.

## <a name="create-a-host-using-nethosth-and-hostfxrh"></a>Erstellen eines Hosts mithilfe von `nethost.h` und `hostfxr.h`

In den folgenden Schritten wird detailliert beschrieben, wie Sie die Bibliotheken `nethost` und `hostfxr` verwenden können, um die .NET Core-Runtime in einer nativen Anwendung zu starten und eine verwaltete statische Methode aufzurufen. Im [Beispiel](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr) werden der mit dem .NET SDK installierte Header `nethost` und die Bibliothek sowie Kopien der Dateien [`coreclr_delegates.h`](https://github.com/dotnet/runtime/blob/master/src/installer/corehost/cli/coreclr_delegates.h) und [`hostfxr.h`](https://github.com/dotnet/runtime/blob/master/src/installer/corehost/cli/hostfxr.h) aus dem Repository [dotnet/runtime](https://github.com/dotnet/runtime) verwendet.

### <a name="step-1---load-hostfxr-and-get-exported-hosting-functions"></a>Schritt 1: Laden von `hostfxr` und Abrufen der exportierten Hostingfunktionen

Die Bibliothek `nethost` bietet die Funktion `get_hostfxr_path` für das Auffinden der Bibliothek `hostfxr`. Die Bibliothek `hostfxr` macht die Funktionen zum Hosten der .NET Core-Runtime verfügbar. Die vollständige Liste der Funktionen finden Sie in [`hostfxr.h`](https://github.com/dotnet/runtime/blob/master/src/installer/corehost/cli/hostfxr.h) und im [Entwurfsdokument zum nativen Hosting](https://github.com/dotnet/runtime/blob/master/docs/design/features/native-hosting.md). Im Beispiel und in diesem Tutorial wird Folgendes verwendet:

* `hostfxr_initialize_for_runtime_config`: Initialisiert einen Hostkontext und bereitet die Initialisierung der .NET Core-Runtime mithilfe der angegebenen Runtimekonfiguration vor.
* `hostfxr_get_runtime_delegate`: Ruft einen Delegaten für Runtimefunktionalität ab.
* `hostfxr_close`: Schließt einen Hostkontext.

Die Bibliothek `hostfxr` wird mithilfe von `get_hostfxr_path` gefunden. Sie wird anschließend geladen, und ihre Exporte werden abgerufen.

[!code-cpp[HostFxrHost#LoadHostFxr](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadHostFxr)]

### <a name="step-2---initialize-and-start-the-net-core-runtime"></a>Schritt 2: Initialisieren und Starten der .NET Core-Runtime

Die Funktionen `hostfxr_initialize_for_runtime_config` und `hostfxr_get_runtime_delegate` initialisieren und starten die .NET Core-Runtime unter Verwendung der Runtimekonfiguration für die verwaltete Komponente, die geladen wird. Die Funktion `hostfxr_get_runtime_delegate` wird verwendet, um einen Runtimedelegaten abzurufen, der das Laden einer verwalteten Assembly und das Abrufen eines Funktionszeigers auf eine statische Methode in dieser Assembly ermöglicht.

[!code-cpp[HostFxrHost#Initialize](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#Initialize)]

### <a name="step-3---load-managed-assembly-and-get-function-pointer-to-a-managed-method"></a>Schritt 3: Laden der verwalteten Assembly und Abrufen des Funktionszeigers auf eine verwaltete Methode

Der Runtimedelegat wird aufgerufen, um die verwaltete Assembly zu laden und einen Funktionszeiger auf eine verwaltete Methode abzurufen. Der Delegat benötigt den Assemblypfad, Typ- und Methodennamen als Eingaben und gibt einen Funktionszeiger zurück, mit dem die verwaltete Methode aufgerufen werden kann.

[!code-cpp[HostFxrHost#LoadAndGet](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadAndGet)]

Durch die Übergabe von `nullptr` als Delegatentypname beim Aufruf des Runtimedelegaten verwendet das Beispiel eine Standardsignatur für die verwaltete Methode:

```csharp
public delegate int ComponentEntryPoint(IntPtr args, int sizeBytes);
```

Eine andere Signatur kann verwendet werden, indem beim Aufruf des Runtimedelegaten der Name des Delegatentyps angegeben wird.

### <a name="step-4---run-managed-code"></a>Schritt 4: Ausführen von verwaltetem Code

Der native Host kann nun die verwaltete Methode aufrufen und die gewünschten Parameter an sie übergeben.

[!code-cpp[HostFxrHost#CallManaged](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#CallManaged)]

## <a name="create-a-host-using-coreclrhosth"></a>Erstellen eines Hosts mithilfe von `coreclrhost.h`

In den folgenden Schritten wird detailliert beschrieben, wie Sie die API `coreclrhost.h` verwenden können, um die .NET Core-Runtime in einer nativen Anwendung zu starten und eine verwaltete statische Methode aufzurufen. Für die Codeausschnitte in diesem Artikel werden einige Windows-spezifische APIs verwendet. Im [vollständigen Beispielhost](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost) sind jedoch Windows- und Linux-Codepfade enthalten.

Der [Host Unix CoreRun](https://github.com/dotnet/runtime/tree/master/src/coreclr/hosts/unixcorerun) zeigt ein komplexeres, realistisches Beispiel für das Hosting mit `coreclrhost.h`.

### <a name="step-1---find-and-load-coreclr"></a>Schritt 1: Suchen und Laden von CoreCLR

Die APIs für die .NET Core-Runtime befinden sich in *coreclr.dll* (Windows), *libcoreclr.so* (Linux) und *libcoreclr.dylib* (macOS). Wenn Sie .NET Core hosten möchten, müssen Sie zunächst die CoreCLR-Bibliothek laden. Einige Hosts durchsuchen unterschiedliche Pfade oder verwenden Eingabeparameter, um die Bibliothek zu suchen, während anderen bekannt ist, dass diese aus einem bestimmten Pfad geladen werden muss (z. B. neben dem Host oder von einem computerweiten Speicherort).

Sobald die Bibliothek gefunden wurde, wird sie mit `LoadLibraryEx` (Windows) oder `dlopen` (Linux/macOS) geladen.

[!code-cpp[CoreClrHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#1)]

### <a name="step-2---get-net-core-hosting-functions"></a>Schritt 2: .NET Core-Hostingfunktionen

In CoreClrHost sind einige wichtige Methoden enthalten, die für das Hosten von .NET Core nützlich sind:

* `coreclr_initialize`: Startet die .NET Core-Runtime und richtet die (einzige) Standardanwendungsdomäne ein.
* `coreclr_execute_assembly`: Führt eine verwaltete Assembly aus.
* `coreclr_create_delegate`: Erstellt einen Funktionszeiger zu einer verwalteten Methode.
* `coreclr_shutdown`: Beendet die .NET Core-Runtime.
* `coreclr_shutdown_2`: Funktioniert wie `coreclr_shutdown`, ruft jedoch zusätzlich den Exitcode des verwalteten Codes ab.

Nachdem Sie die CoreCLR-Bibliothek geladen haben, müssen Sie mithilfe von `GetProcAddress` (Windows) oder `dlsym` (Linux/macOS) auf diese Funktion verweisen.

[!code-cpp[CoreClrHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#2)]

### <a name="step-3---prepare-runtime-properties"></a>Schritt 3: Vorbereiten der Runtimeeigenschaften

Bevor Sie die Runtime starten, müssen Sie einige Eigenschaften auf bestimmte Verhaltensweisen festlegen (insbesondere für das Assemblyladeprogramm).

Das gilt üblicherweise für folgende Eigenschaften:

* `TRUSTED_PLATFORM_ASSEMBLIES`: Diese Eigenschaft stellt eine Liste der Assemblypfade (unter Windows durch „;“ und unter Linux durch „:“ getrennt) dar, die die Runtime standardmäßig auflösen kann. Einige Hosts verfügen über hartcodierte Manifeste mit Assemblys, die geladen werden können. Andere platzieren Bibliotheken in dieser Liste an bestimmten Positionen (z. B. neben *coreclr.dll*).
* `APP_PATHS` Dies ist eine Liste der Pfade, in denen nach einer Assembly gesucht werden soll, wenn sie in der Liste der vertrauenswürdigen Plattformassemblys (TPA) nicht gefunden werden kann. Da der Host mehr Kontrolle darüber hat, welche Assemblys mithilfe der TPA-Liste geladen werden, wird empfohlen, für alle Hosts festzulegen, welche Assemblys diese erwarten und diese explizit aufzulisten. Über diese Eigenschaft können Sie auch die Überprüfung von Runtimes aktivieren.
* `APP_NI_PATHS`: Diese Liste ähnelt APP_PATHS sehr ähnlich, gilt jedoch für Pfade, die nach nativen Images durchsucht werden sollen.
* `NATIVE_DLL_SEARCH_DIRECTORIES`: Diese Eigenschaft ist eine Liste der Pfade, die das Ladeprogramm durchsuchen soll, wenn es nach nativen Bibliotheken sucht, die über p/invoke aufgerufen werden.
* `PLATFORM_RESOURCE_ROOTS` Diese Liste enthält die Pfade, in denen nach Assemblys der Ressourcensatelliten (in kulturspezifischen Unterverzeichnissen) gesucht wird.

In diesem Beispielhost wird die TPA-Liste erstellt, indem alle Bibliotheken im aktuellen Verzeichnis aufgelistet werden:

[!code-cpp[CoreClrHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#7)]

Da es sich um ein einfaches Beispiel handelt, ist nur die Eigenschaft `TRUSTED_PLATFORM_ASSEMBLIES` erforderlich:

[!code-cpp[CoreClrHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#3)]

### <a name="step-4---start-the-runtime"></a>Schritt 4: Starten der Runtime

`coreclrhost.h`-APIs starten die Runtime und erstellen die Standard-AppDomain mit einem einzigen Befehl. Die Funktion `coreclr_initialize` akzeptiert einen Basispfad, einen Namen und die zuvor beschriebenen Eigenschaften und gibt ein Handle zum Host über den Parameter `hostHandle` zurück.

[!code-cpp[CoreClrHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#4)]

### <a name="step-5---run-managed-code"></a>Schritt 5: Ausführen von verwaltetem Code

Wenn die Runtime gestartet wurde, kann der Host verwalteten Code abrufen. Dafür stehen verschiedene Möglichkeiten zur Auswahl. Im Beispielcode für dieses Tutorial wird die Funktion `coreclr_create_delegate` verwendet, um einen Delegaten für eine verwaltete statische Methode zu erstellen. Diese API akzeptiert den [Assemblynamen](../../standard/assembly/names.md), den namespacequalifizierten Typnamen und den Methodennamen als Eingabe und gibt einen Delegaten zurück, mit dem die Methode aufgerufen werden kann.

[!code-cpp[CoreClrHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#5)]

In diesem Beispiel kann der Host nun `managedDelegate` verwenden, um die Methode `ManagedWorker.DoWork` aufzurufen.

Alternativ kann die `coreclr_execute_assembly`-Funktion verwendet werden, um eine verwaltete ausführbare Datei zu starten. Diese API akzeptiert einen Assemblypfad und ein Array aus Argumenten als Eingabeparameter. Sie lädt die Assembly aus diesem Pfad und ruft deren main-Methode auf.

```c++
int hr = executeAssembly(
        hostHandle,
        domainId,
        argumentCount,
        arguments,
        "HelloWorld.exe",
        (unsigned int*)&exitCode);
```

### <a name="step-6---shutdown-and-clean-up"></a>Schritt 6: Beenden und Bereinigen

Wenn der Host den verwalteten Code ausgeführt hat, wird die .NET Core-Runtime schließlich mithilfe von `coreclr_shutdown` oder `coreclr_shutdown_2` beendet.

[!code-cpp[CoreClrHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#6)]

CoreCLR unterstützt keine erneute Initialisierung oder das Entladen. Rufen Sie `coreclr_initialize` nicht erneut auf oder entladen Sie die CoreCLR-Bibliothek.

## <a name="conclusion"></a>Zusammenfassung

Sobald Ihr Host erstellt wurde, können Sie ihn testen, indem Sie ihn über die Befehlszeile ausführen und Argumente übergeben, die der Host erwartet. Beim Angeben der .NET Core-Anwendung, die den Host ausführt, müssen Sie die DLL-Datei verwenden, die von `dotnet build` erzeugt wurde. Ausführbare Dateien (EXE-Dateien), die für eigenständige Anwendungen von `dotnet publish` erstellt wurden, stellen die Standardeinstellung des .NET Core-Hosts dar, sodass die Anwendung in Hauptszenarios direkt über die Befehlszeile gestartet werden kann. Der Benutzercode wird in eine DLL-Datei mit dem gleichen Namen kompiliert.

Wenn anfangs Funktionsstörungen auftreten, überprüfen Sie, ob *coreclr.dll* an dem Speicherort zur Verfügung steht, den der Host erwartet, ob sich alle erforderlichen Frameworkbibliotheken in der TPA-Liste befinden und ob die CoreCLR-Bitanzahl (32-Bit oder 64-Bit) der Erstellungsart des Host entspricht.

Das Hosten der Laufzeit von .NET Core ist ein erweitertes Szenario, das für viele Entwickler nicht erforderlich ist, aber für diejenigen, die verwalteten Code von einem nativen Prozess starten müssen, oder die mehr Kontrolle über das Verhalten der .NET Core-Laufzeit benötigen, kann es sehr nützlich sein.
