---
title: Globalisierung und ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: 6ea848d4a60069e6702b9d60fd90a55f572fb043
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842512"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="08b8f-102">.NET-Globalisierung und ICU</span><span class="sxs-lookup"><span data-stu-id="08b8f-102">.NET globalization and ICU</span></span>

<span data-ttu-id="08b8f-103">In der Vergangenheit verwendeten die .NET-Globalisierungs-APIs verschiedene zugrunde liegende Bibliotheken auf verschiedenen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="08b8f-104">Unter UNIX haben die APIs [International Components for Unicode (ICU)](http://site.icu-project.org/home) und unter Windows [National Language Support (NLS)](/windows/win32/intl/national-language-support) verwendet.</span><span class="sxs-lookup"><span data-stu-id="08b8f-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="08b8f-105">Dies führte zu einigen Verhaltensunterschieden in einigen Globalisierungs-APIs, wenn Anwendungen auf verschiedenen Plattformen ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="08b8f-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="08b8f-106">Verhaltensunterschiede waren in den folgenden Bereichen ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="08b8f-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="08b8f-107">Kulturen und Kulturdaten</span><span class="sxs-lookup"><span data-stu-id="08b8f-107">Cultures and culture data</span></span>
- <span data-ttu-id="08b8f-108">Groß-/Kleinschreibung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="08b8f-108">String casing</span></span>
- <span data-ttu-id="08b8f-109">Sortieren und Suchen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="08b8f-109">String sorting and searching</span></span>
- <span data-ttu-id="08b8f-110">Sortieren von Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="08b8f-110">Sort keys</span></span>
- <span data-ttu-id="08b8f-111">Zeichenfolgennormalisierung</span><span class="sxs-lookup"><span data-stu-id="08b8f-111">String normalization</span></span>
- <span data-ttu-id="08b8f-112">Unterstützung für internationalisierte Domänennamen (IDN)</span><span class="sxs-lookup"><span data-stu-id="08b8f-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="08b8f-113">Anzeigename der Zeitzone unter Linux</span><span class="sxs-lookup"><span data-stu-id="08b8f-113">Time zone display name on Linux</span></span>

<span data-ttu-id="08b8f-114">Ab .NET 5.0 haben Entwickler mehr Kontrolle darüber, welche zugrunde liegende Bibliothek verwendet wird. So können in Anwendungen plattformübergreifende Unterschiede vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="08b8f-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="08b8f-115">ICU unter Windows</span><span class="sxs-lookup"><span data-stu-id="08b8f-115">ICU on Windows</span></span>

<span data-ttu-id="08b8f-116">Das Windows 10-Update von Mai 2019 und höhere Versionen enthalten [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) als Teil des Betriebssystems, und .NET 5.0 und höhere Versionen verwenden standardmäßig ICU.</span><span class="sxs-lookup"><span data-stu-id="08b8f-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="08b8f-117">Wenn die Ausführung unter Windows erfolgt, versuchen .NET 5.0 und höhere Versionen, `icu.dll` zu laden. Wenn die DLL verfügbar ist, wird sie für die Globalisierungsimplementierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="08b8f-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and if it's available, uses it for the globalization implementation.</span></span>  <span data-ttu-id="08b8f-118">Wenn diese Bibliothek nicht gefunden oder geladen werden kann, z. B. bei Ausführung mit älteren Versionen von Windows, greifen .NET 5.0 und höhere Versionen auf die NLS-basierte Implementierung zurück.</span><span class="sxs-lookup"><span data-stu-id="08b8f-118">If that library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="08b8f-119">Selbst bei Verwendung von ICU verwenden die `CurrentCulture`-, `CurrentUICulture`- und `CurrentRegion`-Member weiterhin Windows-Betriebssystem-APIs, um Benutzereinstellungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="using-nls-instead-of-icu"></a><span data-ttu-id="08b8f-120">Verwenden von NLS anstelle von ICU</span><span class="sxs-lookup"><span data-stu-id="08b8f-120">Using NLS instead of ICU</span></span>

<span data-ttu-id="08b8f-121">Die Verwendung von ICU anstelle von NLS kann zu Verhaltensunterschieden bei einigen globalisierungsbezogenen Vorgängen führen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-121">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="08b8f-122">Um wieder NLS zu verwenden, kann ein Entwickler die ICU-Implementierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="08b8f-122">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="08b8f-123">Anwendungen können den NLS-Modus auf eine der folgenden Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08b8f-123">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="08b8f-124">In der Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="08b8f-124">In the project file:</span></span>

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
</ItemGroup>
```

- <span data-ttu-id="08b8f-125">In der Datei `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="08b8f-125">In the `runtimeconfig.json` file:</span></span>

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.UseNls": true
      }
  }
}
```

- <span data-ttu-id="08b8f-126">Durch Festlegen der Umgebungsvariablen `DOTNET_SYSTEM_GLOBALIZATION_USENLS` auf den Wert `true` oder `1`.</span><span class="sxs-lookup"><span data-stu-id="08b8f-126">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="08b8f-127">Ein im Projekt oder in der Datei `runtimeconfig.json` festgelegter Wert hat Vorrang vor der Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-127">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="08b8f-128">Weitere Informationen finden Sie unter [Laufzeitkonfigurationseinstellungen](../../core/run-time-config/globalization.md#nls).</span><span class="sxs-lookup"><span data-stu-id="08b8f-128">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="08b8f-129">App-lokale ICU</span><span class="sxs-lookup"><span data-stu-id="08b8f-129">App-local ICU</span></span>

<span data-ttu-id="08b8f-130">Jedes Release von ICU kann Fehlerbehebungen sowie aktualisierte CLDR-Daten (Common Locale Data Repository) enthalten, die die Sprachen der Welt beschreiben.</span><span class="sxs-lookup"><span data-stu-id="08b8f-130">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="08b8f-131">Der Wechsel zwischen ICU-Versionen kann das Verhalten von Apps subtil beeinflussen, wenn es um globalisierungsbezogene Vorgänge geht.</span><span class="sxs-lookup"><span data-stu-id="08b8f-131">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span>  <span data-ttu-id="08b8f-132">Damit Anwendungsentwickler Konsistenz über alle Bereitstellungen hinweg sicherstellen können, ermöglichen .NET 5.0 und höhere Versionen Apps unter Windows und UNIX das Einbinden und Verwenden ihrer eigenen Kopie von ICU.</span><span class="sxs-lookup"><span data-stu-id="08b8f-132">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="08b8f-133">Anwendungen können einen App-lokalen ICU-Implementierungsmodus auf eine der folgenden Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="08b8f-133">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="08b8f-134">In der Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="08b8f-134">In  the project file:</span></span>

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
</ItemGroup>
```

- <span data-ttu-id="08b8f-135">In der Datei `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="08b8f-135">In the `runtimeconfig.json` file:</span></span>

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
      }
  }
}
```

- <span data-ttu-id="08b8f-136">Durch Festlegen der Umgebungsvariablen `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` auf den Wert `<suffix>:<version>` oder `<version>`.</span><span class="sxs-lookup"><span data-stu-id="08b8f-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

<span data-ttu-id="08b8f-137">`<suffix>`: Optionales Suffix mit weniger als 36 Zeichen gemäß den öffentlichen ICU-Paketkonventionen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-137">`<suffix>`: Optional suffix of less than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="08b8f-138">Wenn Sie eine benutzerdefinierte ICU-Bibliothek erstellt haben, können Sie diese so anpassen, dass die Bibliotheksnamen und exportierten Symbolnamen mit einem Suffix erstellt werden, z. B. `libicuucmyapp`, wobei `myapp` das Suffix ist.</span><span class="sxs-lookup"><span data-stu-id="08b8f-138">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

<span data-ttu-id="08b8f-139">`<version>`: Eine gültige ICU-Version, z. B. 67.1.</span><span class="sxs-lookup"><span data-stu-id="08b8f-139">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="08b8f-140">Diese Version wird zum Laden der Binärdateien und zum Abrufen der exportierten Symbole verwendet.</span><span class="sxs-lookup"><span data-stu-id="08b8f-140">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="08b8f-141">Wenn Sie ICU laden möchten, wenn der App-lokale Switch festgelegt ist, verwendet .NET die <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>-Methode, die mehrere Pfade überprüft.</span><span class="sxs-lookup"><span data-stu-id="08b8f-141">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="08b8f-142">Die Methode versucht zuerst, die Bibliothek in der `NATIVE_DLL_SEARCH_DIRECTORIES`-Eigenschaft zu finden, die vom dotnet-Host basierend auf der Datei `deps.json` für die App erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="08b8f-142">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="08b8f-143">Weitere Informationen finden Sie unter [Standardüberprüfung](../../core/dependency-loading/default-probing.md).</span><span class="sxs-lookup"><span data-stu-id="08b8f-143">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="08b8f-144">Für eigenständige Apps sind keine besonderen Aktionen durch den Benutzer erforderlich. Es muss nur sichergestellt werden, dass sich die ICU-Bibliothek im App-Verzeichnis befindet (für eigenständige Apps ist das Arbeitsverzeichnis standardmäßig `NATIVE_DLL_SEARCH_DIRECTORIES`).</span><span class="sxs-lookup"><span data-stu-id="08b8f-144">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="08b8f-145">Wenn Sie ICU mithilfe eines NuGet-Pakets nutzen, funktioniert dies in frameworkabhängigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-145">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="08b8f-146">NuGet löst die nativen Ressourcen auf und bindet sie in die Datei `deps.json` sowie in das Ausgabeverzeichnis für die Anwendung im Verzeichnis `runtimes`.</span><span class="sxs-lookup"><span data-stu-id="08b8f-146">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="08b8f-147">.NET lädt Sie von dort.</span><span class="sxs-lookup"><span data-stu-id="08b8f-147">.NET loads it from there.</span></span>

<span data-ttu-id="08b8f-148">Für frameworkabhängige Apps (nicht eigenständig), in denen ICU aus einem lokalen Build genutzt wird, müssen Sie zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-148">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="08b8f-149">Das .NET SDK verfügt noch nicht über eine Funktion, die „lose“ native Binärdateien in `deps.json` integriert (weitere Informationen dazu finden Sie in [diesem SDK-Problem](https://github.com/dotnet/sdk/issues/11373)).</span><span class="sxs-lookup"><span data-stu-id="08b8f-149">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="08b8f-150">Stattdessen können Sie dies aktivieren, indem Sie der Projektdatei der Anwendung zusätzliche Informationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-150">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="08b8f-151">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="08b8f-151">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="08b8f-152">Dies muss für alle ICU-Binärdateien für die unterstützten Laufzeiten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08b8f-152">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="08b8f-153">Außerdem müssen die `NuGetPackageId`-Metadaten in der `RuntimeTargetsCopyLocalItems`-Elementgruppe mit einem NuGet-Paket übereinstimmen, auf das das Projekt tatsächlich verweist.</span><span class="sxs-lookup"><span data-stu-id="08b8f-153">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="08b8f-154">macOS-Verhalten</span><span class="sxs-lookup"><span data-stu-id="08b8f-154">macOS behavior</span></span>

<span data-ttu-id="08b8f-155">`macOS` weist ein anderes Verhalten zum Auflösen abhängiger dynamischer Bibliotheken aus den in der `match-o`-Datei angegebenen Ladebefehlen als das Linux-Lademodul auf.</span><span class="sxs-lookup"><span data-stu-id="08b8f-155">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="08b8f-156">Im Linux-Lademodul kann .NET versuchen, `libicudata`, `libicuuc` und `libicui18n` (in dieser Reihenfolge) zu verwenden, um das ICU-Abhängigkeitsdiagramm zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-156">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="08b8f-157">Unter macOS funktioniert dies jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="08b8f-157">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="08b8f-158">Wenn Sie ICU unter macOS erstellen, erhalten Sie standardmäßig eine dynamische Bibliothek mit diesen Ladebefehlen in `libicuuc`.</span><span class="sxs-lookup"><span data-stu-id="08b8f-158">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="08b8f-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="08b8f-159">For example.:</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="08b8f-160">Diese Befehle verweisen nur auf den Namen der abhängigen Bibliotheken für die anderen Komponenten von ICU.</span><span class="sxs-lookup"><span data-stu-id="08b8f-160">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="08b8f-161">Das Lademodul führt die Suche nach den `dlopen`-Konventionen durch, wobei diese Bibliotheken in den Systemverzeichnissen enthalten sind oder die `LD_LIBRARY_PATH`-Umgebungsvariablen festgelegt werden oder sich ICU im Verzeichnis auf App-Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="08b8f-161">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="08b8f-162">Wenn Sie `LD_LIBRARY_PATH` nicht festlegen oder sicherstellen können, dass sich die ICU-Binärdateien im Verzeichnis auf App-Ebene befinden, müssen Sie zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-162">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="08b8f-163">Es gibt einige Direktiven für das Ladeprogramm (z. B. `@loader_path`), die das Ladeprogramm anweisen, diese Abhängigkeit im gleichen Verzeichnis wie die Binärdatei mit diesem Ladebefehl zu suchen.</span><span class="sxs-lookup"><span data-stu-id="08b8f-163">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="08b8f-164">Es gibt zwei Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="08b8f-164">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="08b8f-165">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="08b8f-165">Run the following commands:</span></span>

```bash
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
```

- <span data-ttu-id="08b8f-166">Patchen von ICU zum Generieren der Installationsnamen mit `@loader_path`</span><span class="sxs-lookup"><span data-stu-id="08b8f-166">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="08b8f-167">Ändern Sie vor dem Ausführen der automatischen Konfiguration (`./runConfigureICU`) [diese Zeilen](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="08b8f-167">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

```
LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
```
