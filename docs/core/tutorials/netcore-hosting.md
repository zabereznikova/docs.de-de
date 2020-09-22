---
title: Schreiben eines benutzerdefinierten .NET Core-Laufzeithosts
description: Erfahren Sie, wie Sie die.NET Core-Runtime vom nativen Code aus hosten können, um erweiterte Szenarien zu unterstützen, die eine Kontrolle der Funktionsweise der.NET Core-Runtime erfordern.
author: mjrousos
ms.topic: how-to
ms.date: 12/21/2018
ms.openlocfilehash: 9f45a75d7ec836c14a2285a1707649cc32c2a25c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537547"
---
# <a name="write-a-custom-net-core-host-to-control-the-net-runtime-from-your-native-code"></a>Schreiben Sie einen benutzerdefinierten .NET Core-Host, um die .NET-Runtime über den systemeigenen Code zu steuern.

Wie alle verwalteten Codes werden .NET Core-Anwendungen von einem Host ausgeführt. Der Host ist für das Starten der Runtime (einschließlich Komponenten wie die JIT und Garbage Collector) und das Aufrufen von verwalteten Einstiegspunkten verantwortlich.

Das Hosten der Laufzeit von .NET Core ist ein erweitertes Szenario, und in den meisten Fällen brauchen sich .NET Core-Entwickler nicht darum kümmern, da die Buildprozesse von .NET Core einen Standardhost bereitstellen, der die .NET Core-Anwendungen ausführt. Unter speziellen Umständen kann es jedoch hilfreich sein, die .NET Core-Laufzeit explizit zu hosten, entweder als Mittel zum Aufrufen von verwalteten Codes in einem nativen Prozess oder um mehr Kontrolle über die Funktionsweise der Laufzeit zu erhalten.

Dieser Artikel bietet einen Überblick über die erforderlichen Schritte zum Starten der .NET Core-Runtime aus nativem Code und für das Ausführen von darin enthaltenem verwalteten Code.

## <a name="prerequisites"></a>Voraussetzungen

Da Hosts native Anwendungen sind, wird in diesem Tutorial das Erstellen einer C++-Anwendung zum Hosten von .NET Core behandelt. Sie benötigen eine C++-Entwicklungsumgebung (z.B. von [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)).

Sie sollten außerdem über eine einfache .NET Core-Anwendung zum Testen des Hosts verfügen, daher sollten Sie die [.NET Core SDK](https://dotnet.microsoft.com/download) installieren und [eine kleine .NET Core-Testanwendung erstellen](with-visual-studio.md) (z.B. die Anwendung „Hello World“). Die „Hello World“-Anwendung, die von der neuen Projektvorlage der .NET Core-Konsole erstellt wird, ist ausreichend.

## <a name="hosting-apis"></a>Hosting-APIs
Sie können drei APIs verwenden, um .NET Core zu hosten. In diesem Artikel (und den zugehörigen [Beispielen](https://github.com/dotnet/samples/tree/master/core/hosting)) werden alle Optionen behandelt.

* Die bevorzugte Methode zum Hosten der .NET Core-Runtime ab .NET Core 3.0 ist mithilfe der APIs der Bibliotheken `nethost` und `hostfxr`. Diese Einstiegspunkte bewältigen die Komplexität des Auffindens und Einrichtens der Runtime für die Initialisierung und ermöglichen sowohl das Starten einer verwalteten Anwendung als auch das Aufrufen einer statischen verwalteten Methode.
* Die API [CoreClrHost.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/hosts/inc/coreclrhost.h) wird jedoch vor .NET Core 3.0 bevorzugt für das Hosten der .NET Core-Runtime verwendet. Diese API enthält Funktionen, mit denen Sie die Runtime einfach starten und beenden können und verwalteten Code aufrufen können, indem Sie entweder eine entsprechende ausführbare Datei ausführen oder verwaltete statische Methoden aufrufen.
* .NET Core kann jedoch auch mit der `ICLRRuntimeHost4`-Schnittstelle in [mscoree.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/mscoree.h) gehostet werden. Diese API ist älter als „CoreClrHost.h“, deshalb kann es vorkommen, dass ältere Hosts diese verwenden. Die API funktioniert weiterhin und ermöglicht eine bessere Steuerung des Hostprozesses als „CoreClrHost“. In den meisten Fällen wird „CoreClrHost.h“ jedoch aufgrund der einfacheren APIs bevorzugt.

## <a name="sample-hosts"></a>Beispielhosts

[Beispielhosts](https://github.com/dotnet/samples/tree/master/core/hosting) zur Veranschaulichung der Schritte in diesen Tutorials sind im GitHub-Repository „dotnet/samples“ auf verfügbar. Durch die Kommentare in den Beispielen werden die nummerierten Schritte in diesem Tutorial ihrer Position im Beispiel eindeutig zugeordnet. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#view-and-download-samples).

Bedenken Sie, dass die Beispielhosts zu Lernzwecken gedacht und somit bei der Fehlerüberprüfung nachsichtig sind. Die Lesbarkeit steht in diesem Fall über der Effizienz.

## <a name="create-a-host-using-nethosth-and-hostfxrh"></a>Erstellen eines Hosts mithilfe von NetHost.h und HostFxr.h

In den folgenden Schritten wird detailliert beschrieben, wie Sie die Bibliotheken `nethost` und `hostfxr` verwenden können, um die .NET Core-Runtime in einer nativen Anwendung zu starten und eine verwaltete statische Methode aufzurufen. Im [Beispiel](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr) werden der mit dem .NET SDK installierte Header `nethost` und die Bibliothek sowie Kopien der Dateien [`coreclr_delegates.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/coreclr_delegates.h) und [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) aus dem Repository [dotnet/core-setup](https://github.com/dotnet/core-setup) verwendet.

### <a name="step-1---load-hostfxr-and-get-exported-hosting-functions"></a>Schritt 1: Laden von HostFxr und Erhalten der exportierten Hostingfunktionen

Die Bibliothek `nethost` bietet die Funktion `get_hostfxr_path` für das Auffinden der Bibliothek `hostfxr`. Die Bibliothek `hostfxr` macht die Funktionen zum Hosten der .NET Core-Runtime verfügbar. Die vollständige Liste der Funktionen finden Sie in [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) und im [Entwurfsdokument zum nativen Hosting](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/native-hosting.md). Im Beispiel und in diesem Tutorial wird Folgendes verwendet:

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

## <a name="create-a-host-using-coreclrhosth"></a>Erstellen eines Hosts mithilfe von „CoreClrHost.h“

In den folgenden Schritten wird detailliert beschrieben, wie Sie die API „CoreClrHost.h“ verwenden können, um die .NET Core-Runtime in einer nativen Anwendung zu starten und eine verwaltete statische Methode aufzurufen. Für die Codeausschnitte in diesem Artikel werden einige Windows-spezifische APIs verwendet. Im [vollständigen Beispielhost](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost) sind jedoch Windows- und Linux-Codepfade enthalten.

[Unix CoreRun Host](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/unixcorerun) zeigt ein komplexeres, realistisches Beispiel für das Hosting mit „coreclrhost.h“.

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

Anders als bei der Hosting-API „mscoree.h“ (siehe unten) starten die APIs von „CoreCLRHost.h“ die Runtime und erstellen die Standardanwendungsdomäne mit einem einzigen Aufruf. Die Funktion `coreclr_initialize` akzeptiert einen Basispfad, einen Namen und die zuvor beschriebenen Eigenschaften und gibt ein Handle zum Host über den Parameter `hostHandle` zurück.

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

## <a name="create-a-host-using-mscoreeh"></a>Erstellen eines Hosts mithilfe von „Mscoree.h“

Wie zuvor erwähnt wird „CoreClrHost.h“ mittlerweile für das Hosten der .NET Core-Runtime bevorzugt. Die Schnittstelle `ICLRRuntimeHost4` kann jedoch weiterhin verwendet werden, wenn die Schnittstellen von „CoreClrHost.h“ nicht ausreichen (z. B. wenn Startflags benötigt werden, die vom Standard abweichen, oder wenn AppDomainManager in der Standarddomäne benötigt wird). Mit diesen Anleitungen werden Sie durch den Hostingvorgang von .NET Core mithilfe von „mscoree.h“ geführt.

[CoreRun Host](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/corerun) zeigt ein komplexeres, realistisches Beispiel für das Hosting mit „mscoree.h“.

### <a name="a-note-about-mscoreeh"></a>Ein Hinweis zur mscoree.h
Die .NET Core-Hostingschnittstelle (`ICLRRuntimeHost4`) wird in [MSCOREE. IDL](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/inc/MSCOREE.IDL) definiert. MIDL erzeugt eine Headerversion dieser Datei (mscoree.h), auf die Ihr Host verweisen muss, wenn die [.NET Core-Laufzeit](https://github.com/dotnet/runtime/) erstellt wird. Wenn Sie die .NET Core-Laufzeit nicht erstellen möchten, steht mscoree.h auch als [vorgefertigter Header](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/) im Repository dotnet/runtime zur Verfügung.

### <a name="step-1---identify-the-managed-entry-point"></a>Schritt 1: Ermitteln des verwalteten Einstiegspunkts
Nach Verweisen auf die erforderlichen Header (z.B. [mscoree.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/mscoree.h) und stdio.h), muss ein .NET Core-Host als eine der ersten Aktionen den verwalteten Einstiegspunkt suchen, den er verwenden wird. In unserem Beispielhost wird nur das erste Befehlszeilenargument als Pfad zu einer verwalteten Binärdatei verwendet, deren `main`-Methode ausgeführt wird.

[!code-cpp[NetCoreHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#1)]

### <a name="step-2---find-and-load-coreclr"></a>Schritt 2: Suchen und Laden von CoreCLR
Die .NET Core Runtime-APIs befinden sich in *CoreCLR.dll* (unter Windows). Um unsere Hostingschnittstelle (`ICLRRuntimeHost4`) abzurufen, ist es erforderlich, *CoreCLR.dll* zu suchen und zu laden. Es obliegt dem Host, eine Konvention für das Auffinden von *CoreCLR.dll* zu definieren. Einige Hosts erwarten, dass die Datei an einem bekannten, computerweiten Speicherort (z. B. *%programfiles%\dotnet\shared\Microsoft.NETCore.App\2.1.6*) vorhanden ist. Andere erwarten, dass *CoreCLR.dll* von einem anderen Speicherort neben dem Host selbst oder der zu hostenden Anwendung geladen wird. Noch andere konsultieren möglicherweise eine Umgebungsvariable, um die Bibliothek zu finden.

Unter Linux oder macOS ist die Core Runtime Library jeweils *libcoreclr.so* oder *libcoreclr.dylib*.

Unser Beispielhost prüft einige gängige Speicherorte für *CoreCLR.dll*. Wenn sie gefunden wurde, muss sie über `LoadLibrary` (oder `dlopen` unter Linux/macOS) geladen werden.

[!code-cpp[NetCoreHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#2)]

### <a name="step-3---get-an-iclrruntimehost4-instance"></a>Schritt 3: Abrufen einer ICLRRuntimeHost4-Instanz
Die `ICLRRuntimeHost4`-Hostingschnittstelle wird durch den Aufruf von `GetProcAddress` (oder `dlsym` unter Linux/macOS) für `GetCLRRuntimeHost` abgerufen, und dann wird diese Funktion aufgerufen.

[!code-cpp[NetCoreHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#3)]

### <a name="step-4---set-startup-flags-and-start-the-runtime"></a>Schritt 4: Festlegen von Startflags und Starten der Runtime
Mit `ICLRRuntimeHost4` können wir jetzt die laufzeitweiten Startflags angeben und die Laufzeit starten. Startflags bestimmen, welchen Garbage Collector (GC) Sie verwenden (gleichzeitig oder Server), ob eine einzelne oder mehrere Anwendungsdomänen verwendet werden und welche Ladeoptimierungsrichtlinie (für domänenneutrales Laden von Assemblys) verwendet werden soll.

[!code-cpp[NetCoreHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#4)]

Die Laufzeit wird durch einen Aufruf der `Start`-Funktion gestartet.

```c++
hr = runtimeHost->Start();
```

### <a name="step-5---preparing-appdomain-settings"></a>Schritt 5: Vorbereiten der Einstellungen der AppDomain
Nachdem die Laufzeit gestartet wurde, möchten wir eine AppDomain einrichten. Es gibt jedoch eine Reihe von Optionen, die beim Erstellen einer .NET AppDomain angegeben werden müssen, daher ist es erforderlich, diese zuerst vorzubereiten.

AppDomain-Flags geben das Verhalten der AppDomain im Zusammenhang mit der Sicherheit und Interoperabilität an. Ältere Silverlight-Hosts verwendeten diese Einstellungen für Sandbox-Benutzercodes, aber die meisten modernen .NET Core-Hosts führen den Benutzercode als voll vertrauenswürdig und interoperabel aus.

[!code-cpp[NetCoreHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#5)]

Nach der Entscheidung, welche der AppDomain-Flags verwendet werden, müssen die AppDomain-Eigenschaften definiert werden. Die Eigenschaften sind Schlüssel-/Wertpaare von Zeichenfolgen. Viele der Eigenschaften beziehen sich auf die Art, mit der die AppDomain Assemblys laden wird.

Allgemeine AppDomain-Eigenschaften beinhalten:

* `TRUSTED_PLATFORM_ASSEMBLIES` Dies ist eine Liste der Assemblypfade (unter Windows durch `;` und unter Linux/macOS durch `:` getrennt), die von Anwendungsdomänen bevorzugt geladen und als voll vertrauenswürdig eingestuft werden sollen (auch in teilweise vertrauenswürdigen Domänen). Diese Liste soll „Framework“-Assemblys und andere vertrauenswürdige Module, ähnlich dem GAC in .NET Framework-Szenarios, enthalten. Einige Hosts platzieren eine Bibliothek neben *coreclr.dll* in dieser Liste, andere haben andere hartcodierte Manifeste, die vertrauenswürdige Assemblys für ihre Zwecke listen.
* `APP_PATHS` Dies ist eine Liste der Pfade, in denen nach einer Assembly gesucht werden soll, wenn sie in der Liste der vertrauenswürdigen Plattformassemblys (TPA) nicht gefunden werden kann. Da der Host mehr Kontrolle darüber hat, welche Assemblys mithilfe der TPA-Liste geladen werden, wird empfohlen, für alle Hosts festzulegen, welche Assemblys diese erwarten und diese explizit aufzulisten. Über diese Eigenschaft können Sie auch die Überprüfung von Runtimes aktivieren.
* `APP_NI_PATHS` Diese Liste ist APP_PATHS sehr ähnlich, außer dass es Pfade sein sollten, in denen nach nativen Images gesucht werden sollen.
* `NATIVE_DLL_SEARCH_DIRECTORIES` Diese Eigenschaft ist eine Liste der Pfade, die das Ladeprogramm durchsuchen sollte, wenn es nach nativen DLLs sucht, die über p/invoke aufgerufen werden.
* `PLATFORM_RESOURCE_ROOTS` Diese Liste enthält die Pfade, in denen nach Assemblys der Ressourcensatelliten (in kulturspezifischen Unterverzeichnissen) gesucht wird.

In unserem [einfache Beispielhost](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithMscoree) sind diese Eigenschaften wie folgt eingerichtet:

[!code-cpp[NetCoreHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#6)]

### <a name="step-6---create-the-appdomain"></a>Schritt 6: Erstellen der AppDomain
Sobald alle Flags und Eigenschaften der AppDomain vorbereitet sind, kann `ICLRRuntimeHost4::CreateAppDomainWithManager` zum Einrichten der AppDomain verwendet werden. Diese Funktion hat optional einen vollqualifizierten Assemblynamen und Typnamen, die als AppDomain-Manager der Domäne verwendet werden. Ein AppDomain-Manager kann einem Host ermöglichen, einige Aspekte des AppDomain-Verhaltens steuern und möglicherweise Einstiegspunkte für den Start von verwaltetem Code bereitzustellen, wenn der Host den Benutzercode nicht direkt aufrufen möchte.

[!code-cpp[NetCoreHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#7)]

### <a name="step-7---run-managed-code"></a>Schritt 7: Ausführen von verwaltetem Code!
Mit einer laufenden AppDomain kann der Host jetzt verwalteten Code ausführen. Die einfachste Möglichkeit hierzu ist die Verwendung von `ICLRRuntimeHost4::ExecuteAssembly`, um die Einstiegspunktmethode für eine verwaltete Assembly aufzurufen. Beachten Sie, dass diese Funktion nur in Szenarios mit einzelnen Domänen funktioniert.

[!code-cpp[NetCoreHost#8](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#8)]

Wenn `ExecuteAssembly` nicht den Anforderungen Ihres Hosts entspricht, gibt es eine andere Option, bei der Sie `CreateDelegate` verwenden, um einen Funktionszeiger zu einer statisch verwalteten Methode zu erstellen. Dafür muss der Host die Signatur der Methode kennen, die er aufruft (um den Funktionszeigertyp zu erstellen), aber es gibt dem Host die Flexibilität, einen anderen Code als den Assemblyeingangspunkt aufzurufen. Der im zweiten Parameter angegebene Assemblyname ist der [vollständige verwaltete Assemblyname](../../standard/assembly/names.md) der zu ladenden Bibliothek.

```c++
void *pfnDelegate = NULL;
hr = runtimeHost->CreateDelegate(
    domainId,
    L"HW, Version=1.0.0.0, Culture=neutral", // Target managed assembly
    L"ConsoleApplication.Program",           // Target managed type
    L"Main",                                 // Target entry point (static method)
    (INT_PTR*)&pfnDelegate);

((MainMethodFp*)pfnDelegate)(NULL);
```

### <a name="step-8---clean-up"></a>Step 8: Bereinigen
Schließlich sollte der Host die Umgebung hinter sich bereinigen, indem er AppDomains entlädt, die Laufzeit beendet und den `ICLRRuntimeHost4`-Verweis freigibt.

[!code-cpp[NetCoreHost#9](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#9)]

CoreCLR unterstützt das Entladen nicht. Die CoreCLR-Bibliothek darf nicht entladen werden.

## <a name="conclusion"></a>Schlussbemerkung
Nachdem Ihr Host erstellt wurde, kann er getestet werden, indem er über die Befehlszeile ausgeführt wird und Argumente übergeben werden, die der Host erwartet (z. B. die verwaltete App, die für den mscoree-Beispielhost ausgeführt werden soll). Beim Angeben der .NET Core-Anwendung, die den Host ausführt, müssen Sie die DLL-Datei verwenden, die von `dotnet build` erzeugt wurde. Ausführbare Dateien (EXE-Dateien), die für eigenständige Anwendungen von `dotnet publish` erstellt wurden, stellen die Standardeinstellung des .NET Core-Hosts dar, sodass die Anwendung in Hauptszenarios direkt über die Befehlszeile gestartet werden kann. Der Benutzercode wird in eine DLL-Datei mit dem gleichen Namen kompiliert.

Wenn anfangs Funktionsstörungen auftreten, überprüfen Sie, ob *coreclr.dll* an dem Speicherort zur Verfügung steht, den der Host erwartet, ob sich alle erforderlichen Frameworkbibliotheken in der TPA-Liste befinden und ob die CoreCLR-Bitanzahl (32-Bit oder 64-Bit) der Erstellungsart des Host entspricht.

Das Hosten der Laufzeit von .NET Core ist ein erweitertes Szenario, das für viele Entwickler nicht erforderlich ist, aber für diejenigen, die verwalteten Code von einem nativen Prozess starten müssen, oder die mehr Kontrolle über das Verhalten der .NET Core-Laufzeit benötigen, kann es sehr nützlich sein.
