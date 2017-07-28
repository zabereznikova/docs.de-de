---
title: Hosten von .NET Core
description: Hosten der .NET Core-Laufzeit aus nativem Code
keywords: .NET, .NET Core, Hosting, Hosting .NET Core
author: mjrousos
ms.author: mikerou
ms.date: 2/3/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13edec8b-614d-47ed-9e95-ed6d3b94ec0c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 61c321b512b1920718196319d367f467f9291b2a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="hosting-net-core"></a>Hosten von .NET Core

Wie alle verwalteten Codes werden .NET Core-Anwendungen von einem Host ausgeführt. Der Host ist verantwortlich für das Starten der Laufzeit (einschließlich Komponenten wie die JIT und Garbage Collector), das Erstellen der AppDomains und das Aufrufen von verwalteten Einstiegspunkten.

Das Hosten der Laufzeit von .NET Core ist ein erweitertes Szenario, und in den meisten Fällen brauchen sich .NET Core-Entwickler nicht darum kümmern, da die Buildprozesse von .NET Core einen Standardhost bereitstellen, der die .NET Core-Anwendungen ausführt. Unter speziellen Umständen kann es jedoch hilfreich sein, die .NET Core-Laufzeit explizit zu hosten, entweder als Mittel zum Aufrufen von verwalteten Codes in einem nativen Prozess oder um mehr Kontrolle über die Funktionsweise der Laufzeit zu erhalten.

Dieser Artikel bietet einen Überblick über die erforderlichen Schritte zum Starten der .NET Core-Laufzeit aus nativem Code, Erstellen einer ersten Anwendungsdomäne (<xref:System.AppDomain>), und Ausführen von darin enthaltenem, verwalteten Code.

## <a name="prerequisites"></a>Erforderliche Komponenten

Da Hosts native Anwendungen sind, wird in diesem Lernprogramm das Erstellen einer C++-Anwendung zum Hosten auf .NET Core behandelt. Sie benötigen eine C++-Entwicklungsumgebung (z.B. von [Visual Studio](https://www.visualstudio.com/downloads/)).

Sie sollten außerdem über eine einfache .NET Core-Anwendung zum Testen des Hosts verfügen, daher sollten Sie die [.NET Core SDK](https://www.microsoft.com/net/core) installieren und [eine kleine .NET Core-Testanwendung erstellen](../../csharp/getting-started/with-visual-studio.md) (z.B. die Anwendung „Hello World“). Die „Hello World“-Anwendung, die von der neuen Projektvorlage der .NET Core-Konsole erstellt wird, ist ausreichend.

In diesem Tutorial und dem zugehörigen Beispiel wird ein Windows-Host erstellt, jedoch finden Sie in den Hinweisen am Ende dieses Artikels Informationen zum Hosten unter Unix.

## <a name="creating-the-host"></a>Erstellen des Hosts

Ein [Beispielhost](https://github.com/dotnet/docs/tree/master/samples/core/hosting) zur Veranschaulichung der Schritte in diesem Artikel steht in unserem Repository „dotnet/docs“ auf GitHub. Kommentare in der Beispieldatei *host.cpp* ordnen die nummerierten Schritte in diesem Tutorial ihrer Position im Beispiel deutlich zu. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Bedenken Sie, dass der Beispielhost zu Lernzwecken gedacht und somit bei der Fehlerüberprüfung nachsichtig ist und bessere Lesbarkeit über Effizienz stellt. Weitere echte Hostbeispiele finden Sie in der Repository [dotnet/coreclr](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts). Vor allem der [CoreRun-Host](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts/corerun) ist ein guter allgemeiner Host, den Sie nach den einfacheren Beispielen studieren können.

### <a name="a-note-about-mscoreeh"></a>Ein Hinweis zur mscoree.h
Die primäre .NET Core-Hostingschnittstelle (`ICLRRuntimeHost2`) ist in [MSCOREE. IDL](https://github.com/dotnet/coreclr/blob/master/src/inc/MSCOREE.IDL) definiert. MIDL erzeugt eine Headerversion dieser Datei (mscoree.h), auf die Ihr Host verweisen muss, wenn die [.NET Core-Laufzeit](https://github.com/dotnet/coreclr/) erstellt wird. Wenn Sie die .NET Core-Laufzeit nicht erstellen möchten, steht mscoree.h auch als [vorgefertigter Header](https://github.com/dotnet/coreclr/tree/master/src/pal/prebuilt/inc) im Repository Dotnet/Coreclr zur Verfügung. [Hinweise zum Erstellen der .NET Core-Laufzeit](https://github.com/dotnet/coreclr#building-the-repository) finden Sie in der GitHub-Repository. 

### <a name="step-1---identify-the-managed-entry-point"></a>Schritt 1: Ermitteln des verwalteten Einstiegspunkts
Nach Verweisen auf die erforderlichen Header (z.B. [mscoree.h](https://github.com/dotnet/coreclr/tree/master/src/pal/prebuilt/inc/mscoree.h) und stdio.h), muss ein .NET Core-Host als eine der ersten Aktionen den verwalteten Einstiegspunkt suchen, den er verwenden wird. In unserem Beispielhost wird nur das erste Befehlszeilenargument als Pfad zu einer verwalteten Binärdatei verwendet, deren `main`-Methode ausgeführt wird.

[!code-cpp[NetCoreHost#1](../../../samples/core/hosting/host.cpp#1)]

### <a name="step-2---find-and-load-coreclrdll"></a>Schritt 2: Suchen und Laden von CoreCLR.dll
Die .NET Core Runtime-APIs befinden sich in *CoreCLR.dll* (unter Windows). Um unsere Hostingschnittstelle (`ICLRRuntimeHost2`) abzurufen, ist es erforderlich, *CoreCLR.dll* zu suchen und zu laden. Es obliegt dem Host, eine Konvention für das Auffinden von *CoreCLR.dll* zu definieren. Einige Hosts erwarten, dass die Datei in einem bekannten, computerweiten Speicherort (z.B. %programfiles%\dotnet\shared\Microsoft.NETCore.App\1.1.0) vorhanden ist. Andere erwarten, dass *CoreCLR.dll* von einem anderen Speicherort neben dem Host selbst oder der zu hostenden Anwendung geladen wird. Noch andere konsultieren möglicherweise eine Umgebungsvariable, um die Bibliothek zu finden.

Unter Linux oder Mac ist die Core Runtime Library jeweils *libcoreclr.so* oder *libcoreclr.dylib*.

Unser Beispielhost prüft einige gängige Speicherorte für *CoreCLR.dll*. Wenn er gefunden wird, muss er geladen werden, über `LoadLibrary` (oder `dlopen` auf Linux/Mac).

[!code-cpp[NetCoreHost#2](../../../samples/core/hosting/host.cpp#2)]

### <a name="step-3---get-an-iclrruntimehost2-instance"></a>Schritt 3: Abrufen einer ICLRRuntimeHost2-Instanz
Die `ICLRRuntimeHost2`-Hostingschnittstelle wird durch den Aufruf von `GetProcAddress` (oder `dlsym` auf Linux/Mac) auf `GetCLRRuntimeHost` abgerufen, und dann wird diese Funktion aufgerufen. 

[!code-cpp[NetCoreHost#3](../../../samples/core/hosting/host.cpp#3)]

### <a name="step-4---setting-startup-flags-and-starting-the-runtime"></a>Schritt 4: Festlegen von Startflags und Starten der Laufzeit
Mit `ICLRRuntimeHost2` können wir jetzt die laufzeitweiten Startflags angeben und die Laufzeit starten. Startflags bestimmen, welchen Garbage Collector (GC) Sie verwenden (gleichzeitig oder Server), ob wir eine einzelne AppDomain oder mehrere verwenden, und welche Ladeoptimierungsrichtlinie (für domänenneutrales Laden von Assemblys) wir verwenden.

[!code-cpp[NetCoreHost#4](../../../samples/core/hosting/host.cpp#4)]

Die Laufzeit wird durch einen Aufruf der `Start`-Funktion gestartet.

```C++
hr = runtimeHost->Start();
```

### <a name="step-5---preparing-appdomain-settings"></a>Schritt 5: Vorbereiten der Einstellungen der AppDomain
Nachdem die Laufzeit gestartet wurde, möchten wir eine AppDomain einrichten. Es gibt jedoch eine Reihe von Optionen, die beim Erstellen einer .NET AppDomain angegeben werden müssen, daher ist es erforderlich, diese zuerst vorzubereiten.

AppDomain-Flags geben das Verhalten der AppDomain im Zusammenhang mit der Sicherheit und Interoperabilität an. Ältere Silverlight-Hosts verwendeten diese Einstellungen für Sandbox-Benutzercodes, aber die meisten modernen .NET Core-Hosts führen den Benutzercode als voll vertrauenswürdig und interoperabel aus.

[!code-cpp[NetCoreHost#5](../../../samples/core/hosting/host.cpp#5)]

Nach der Entscheidung, welche der AppDomain-Flags verwendet werden, müssen die AppDomain-Eigenschaften definiert werden. Die Eigenschaften sind Schlüssel-/Wertpaare von Zeichenfolgen. Viele der Eigenschaften beziehen sich auf die Art, mit der die AppDomain Assemblys laden wird.

Allgemeine AppDomain-Eigenschaften beinhalten:

* `TRUSTED_PLATFORM_ASSEMBLIES` Dies ist eine Liste von Assemblypfaden (getrennt durch „;“ unter Windows und „:“ unter Unix), die AppDomains laden sollten und denen sie komplett vertrauen (auch in teilweise vertrauenswürdigen Domänen). Diese Liste soll „Framework“-Assemblys und andere vertrauenswürdige Module, ähnlich dem GAC in .NET Framework-Szenarios, enthalten. Einige Hosts platzieren eine Bibliothek neben *coreclr.dll* in dieser Liste, andere haben andere hartcodierte Manifeste, die vertrauenswürdige Assemblys für ihre Zwecke listen.
* `APP_PATHS` Dies ist eine Liste der Pfade, in denen nach einer Assembly gesucht werden soll, wenn sie in der Liste der vertrauenswürdigen Plattformassemblys (TPA) nicht gefunden werden kann. Diese Pfade sollen die Speicherorte sein, in denen die Assemblys der Benutzer gefunden werden können. In einer Sandbox-AppDomain erhalten Assemblys von diesen Pfaden nur teilweise Vertrauenswürdigkeit. Allgemeine APP_PATH-Pfade enthalten den Pfad, von dem die Zielanwendung geladen wurde oder andere Speicherorte, in denen Benutzerressourcen vorhanden sind.
*  `APP_NI_PATHS` Diese Liste ist APP_PATHS sehr ähnlich, außer dass es Pfade sein sollten, in denen nach nativen Images gesucht werden sollen.
*  `NATIVE_DLL_SEARCH_DIRECTORIES` Diese Eigenschaft ist eine Liste der Pfade, die das Ladeprogramm durchsuchen sollte, wenn es nach nativen DLLs sucht, die über p/invoke aufgerufen werden.
*  `PLATFORM_RESOURCE_ROOTS` Diese Liste enthält die Pfade, in denen nach Assemblys der Ressourcensatelliten (in kulturspezifischen Unterverzeichnissen) gesucht wird.
*  `AppDomainCompatSwitch` Diese Zeichenfolge gibt an, welche Kompatibilitätsquirks für Assemblys ohne eine explizite Zielframeworkmoniker (ein Attribut auf Assemblyebene, das angibt, welches Framework eine Assembly ausführen soll) verwendet werden sollen. Dies sollte in der Regel auf `"UseLatestBehaviorWhenTFMNotSpecified"` festgelegt werden, aber einige Hosts möchten stattdessen ältere Silverlight- oder Windows Phone-Kompatibilitätsquirks abrufen.

In unserem [einfache Beispielhost](https://github.com/dotnet/docs/tree/master/samples/core/hosting) sind diese Eigenschaften wie folgt eingerichtet:

[!code-cpp[NetCoreHost#6](../../../samples/core/hosting/host.cpp#6)]

### <a name="step-6---create-the-appdomain"></a>Schritt 6: Erstellen der AppDomain
Sobald alle Flags und Eigenschaften der AppDomain vorbereitet sind, kann `ICLRRuntimeHost2::CreateAppDomainWithManager` zum Einrichten der AppDomain verwendet werden. Diese Funktion hat optional einen vollqualifizierten Assemblynamen und Typnamen, die als AppDomain-Manager der Domäne verwendet werden. Ein AppDomain-Manager kann einem Host ermöglichen, einige Aspekte des AppDomain-Verhaltens steuern und möglicherweise Einstiegspunkte für den Start von verwaltetem Code bereitzustellen, wenn der Host den Benutzercode nicht direkt aufrufen möchte.   

[!code-cpp[NetCoreHost#7](../../../samples/core/hosting/host.cpp#7)]

### <a name="step-7---run-managed-code"></a>Schritt 7: Ausführen von verwaltetem Code!
Mit einer laufenden AppDomain kann der Host jetzt verwalteten Code ausführen. Die einfachste Möglichkeit hierzu ist die Verwendung von `ICLRRuntimeHost2::ExecuteAssembly`, um die Einstiegspunktmethode für eine verwaltete Assembly aufzurufen. Beachten Sie, dass diese Funktion nur in Szenarios mit einzelnen Domänen funktioniert.

[!code-cpp[NetCoreHost#8](../../../samples/core/hosting/host.cpp#8)]

Wenn `ExecuteAssembly` nicht den Anforderungen Ihres Hosts entspricht, gibt es eine andere Option, bei der Sie `CreateDelegate` verwenden, um einen Funktionszeiger zu einer statisch verwalteten Methode zu erstellen. Dafür muss der Host die Signatur der Methode kennen, die er aufruft (um den Funktionszeigertyp zu erstellen), aber es gibt dem Host die Flexibilität, einen anderen Code als den Assemblyeingangspunkt aufzurufen.

```C++
void *pfnDelegate = NULL;
hr = runtimeHost->CreateDelegate(
  domainId,
  L"HW, Version=1.0.0.0, Culture=neutral",  // Target managed assembly
  L"ConsoleApplication.Program",            // Target managed type
  L"Main",                                  // Target entry point (static method)
  (INT_PTR*)&pfnDelegate);

((MainMethodFp*)pfnDelegate)(NULL);
```

### <a name="step-8---clean-up"></a>Step 8: Bereinigen
Schließlich sollte der Host die Umgebung hinter sich bereinigen, indem er AppDomains entlädt, die Laufzeit beendet und den `ICLRRuntimeHost2`-Verweis freigibt.

[!code-cpp[NetCoreHost#9](../../../samples/core/hosting/host.cpp#9)]

## <a name="about-hosting-net-core-on-unix"></a>Zum Hosten von .NET Core unter Unix
.NET Core ist ein plattformübergreifendes Produkt, das auf Windows, Linux und Macintosh-Betriebssystemen ausgeführt wird. Als native Anwendungen werden Hosts für verschiedene Plattformen jedoch einige Unterschiede aufweisen. Der oben beschriebene Vorgang zur Verwendung von `ICLRRuntimeHost2`, womit die Laufzeit gestartet, eine AppDomain erstellt und verwalteter Code ausgeführt wird, sollte auf allen beliebigen unterstützten Betriebssystemen funktionieren. Allerdings kann es umständlich sein, mit den Schnittstellen auf Unix-Plattformen zu arbeiten, die in mscoree.h definiert sind, da bei Mscoree von vielen Win32-Annahmen ausgegangen wird.

Um das Hosten auf Unix-Plattformen einfacher zu gestalten, stehen weitere plattformneutrale Hosting-API-Wrapper in [coreclrhost.h](https://github.com/dotnet/coreclr/blob/master/src/coreclr/hosts/inc/coreclrhost.h) zur Verfügung.

Ein Beispiel zur Verwendung von coreclrhost.h (statt direkt mscoree.h) sehen Sie in [UnixCoreRun-Host](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts). Die Schritte zur Verwendung der APIs aus coreclrhost.h als Laufzeithost ähneln den Schritten bei der Verwendung von mscoree.h:

1. Identifizieren Sie den auszuführenden verwalteten Code (z.B. aus den Befehlszeilenparametern). 
2. Laden der CoreCLR-Bibliothek.
    1. `dlopen("./libcoreclr.so", RTLD_NOW | RTLD_LOCAL);` 
3. Rufen Sie Funktionszeiger für CoreCLRs Funktionen `coreclr_initialize`, `coreclr_create_delegate`, `coreclr_execute_assembly` und `coreclr_shutdown` mithilfe von `dlsym` auf.
    1. `coreclr_initialize_ptr coreclr_initialize = (coreclr_initialize_ptr)dlsym(coreclrLib, "coreclr_initialize");`
4. Einrichten von AppDomain-Eigenschaften (z.B. die TPA-Liste). Dies ist identisch mit Schritt 5 aus dem mscoree-Workflow oben.
5. Verwenden Sie `coreclr_initialize`, um die Laufzeit zu starten und eine AppDomain zu erstellen. Dadurch wird auch ein `hostHandle`-Zeiger erstellt, der in Zukunft für das Hosten von Aufrufen verwendet wird.
    1. Beachten Sie, dass diese Funktion die beiden Schritte 4 und 6 aus dem vorherigen Workflow ausführt. 
6. Verwenden Sie entweder `coreclr_execute_assembly` oder `coreclr_create_delegate`, um verwalteten Code auszuführen. Diese Funktionen sind analog zu den `ExecuteAssembly`- und `CreateDelegate`-Funktionen von Mscoree aus Schritt 7 des vorherigen Workflows.
7. Verwenden Sie `coreclr_shutdown`, um die AppDomain zu entladen und die Laufzeit herunterzufahren. 

## <a name="conclusion"></a>Schlussfolgerung
Nachdem Ihr Host erstellt wurde, kann er getestet werden, indem er von der Befehlszeile aus ausgeführt wird und Argumente (z.B. die auszuführende verwaltete Anwendung) übergeben werden, die der Host erwartet. Beim Angeben der .NET Core-Anwendung, die den Host ausführt, müssen Sie die DLL-Datei verwenden, die von `dotnet build` erzeugt wurde. Ausführbare Dateien, die für eigenständige Anwendungen von `dotnet publish` erstellt wurden, sind tatsächlich die Standardeinstellung des .NET Core-Host (sodass die Anwendung direkt über die Befehlszeile in Hauptszenarios gestartet werden kann); der Benutzercode wird in einer DLL mit dem gleichen Namen kompiliert. 

Wenn anfangs Funktionsstörungen auftreten, überprüfen Sie, dass *coreclr.dll* in dem Speicherort zur Verfügung steht, den der Host erwartet, dass sich alle erforderlichen Framework-Bibliotheken in der TPA-Liste befinden, und dass die CoreCLR-Bitanzahl (32 oder 64 Bit) der Erstellungsart des Host entspricht.

Das Hosten der Laufzeit von .NET Core ist ein erweitertes Szenario, das für viele Entwickler nicht erforderlich ist, aber für diejenigen, die verwalteten Code von einem nativen Prozess starten müssen, oder die mehr Kontrolle über das Verhalten der .NET Core-Laufzeit benötigen, kann es sehr nützlich sein. Da .NET Core Seite-an-Seite mit sich selbst ausgeführt werden kann, ist es sogar möglich, Hosts zu erstellen, die mehrere Versionen der Laufzeit von .NET Core initialisieren und starten und im selben Prozess Anwendungen auf allen ausführen. 

