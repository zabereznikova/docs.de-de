---
title: Globalisierung und ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET], about globalization
- global applications, globalization
- international applications [.NET], globalization
- world-ready applications, globalization
- application development [.NET], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: ca579e837b801de237859963ede0e5a9a4bfbcbf
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439468"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="fadea-102">.NET-Globalisierung und ICU</span><span class="sxs-lookup"><span data-stu-id="fadea-102">.NET globalization and ICU</span></span>

<span data-ttu-id="fadea-103">In der Vergangenheit verwendeten die .NET-Globalisierungs-APIs verschiedene zugrunde liegende Bibliotheken auf verschiedenen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="fadea-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="fadea-104">Unter UNIX haben die APIs [International Components for Unicode (ICU)](http://site.icu-project.org/home) und unter Windows [National Language Support (NLS)](/windows/win32/intl/national-language-support) verwendet.</span><span class="sxs-lookup"><span data-stu-id="fadea-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="fadea-105">Dies führte zu einigen Verhaltensunterschieden in einigen Globalisierungs-APIs, wenn Anwendungen auf verschiedenen Plattformen ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="fadea-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="fadea-106">Verhaltensunterschiede waren in den folgenden Bereichen ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="fadea-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="fadea-107">Kulturen und Kulturdaten</span><span class="sxs-lookup"><span data-stu-id="fadea-107">Cultures and culture data</span></span>
- <span data-ttu-id="fadea-108">Groß-/Kleinschreibung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fadea-108">String casing</span></span>
- <span data-ttu-id="fadea-109">Sortieren und Suchen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fadea-109">String sorting and searching</span></span>
- <span data-ttu-id="fadea-110">Sortieren von Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="fadea-110">Sort keys</span></span>
- <span data-ttu-id="fadea-111">Zeichenfolgennormalisierung</span><span class="sxs-lookup"><span data-stu-id="fadea-111">String normalization</span></span>
- <span data-ttu-id="fadea-112">Unterstützung für internationalisierte Domänennamen (IDN)</span><span class="sxs-lookup"><span data-stu-id="fadea-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="fadea-113">Anzeigename der Zeitzone unter Linux</span><span class="sxs-lookup"><span data-stu-id="fadea-113">Time zone display name on Linux</span></span>

<span data-ttu-id="fadea-114">Ab .NET 5.0 haben Entwickler mehr Kontrolle darüber, welche zugrunde liegende Bibliothek verwendet wird. So können in Anwendungen plattformübergreifende Unterschiede vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="fadea-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="fadea-115">ICU unter Windows</span><span class="sxs-lookup"><span data-stu-id="fadea-115">ICU on Windows</span></span>

<span data-ttu-id="fadea-116">Das Windows 10-Update von Mai 2019 und höhere Versionen enthalten [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) als Teil des Betriebssystems, und .NET 5.0 und höhere Versionen verwenden standardmäßig ICU.</span><span class="sxs-lookup"><span data-stu-id="fadea-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="fadea-117">Wenn die Ausführung unter Windows erfolgt, wird ab.NET 5.0 versucht, `icu.dll` zu laden. Wenn die DLL verfügbar ist, wird sie für die Globalisierungsimplementierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fadea-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and, if it's available, use it for the globalization implementation.</span></span> <span data-ttu-id="fadea-118">Wenn die ICU-Bibliothek nicht gefunden oder geladen werden kann, z. B. bei Ausführung mit älteren Versionen von Windows, wird ab .NET 5.0 auf die NLS-basierte Implementierung zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="fadea-118">If the ICU library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="fadea-119">Selbst bei Verwendung von ICU verwenden die `CurrentCulture`-, `CurrentUICulture`- und `CurrentRegion`-Member weiterhin Windows-Betriebssystem-APIs, um Benutzereinstellungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="fadea-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="behavioral-differences"></a><span data-ttu-id="fadea-120">Verhaltensunterschiede</span><span class="sxs-lookup"><span data-stu-id="fadea-120">Behavioral differences</span></span>

<span data-ttu-id="fadea-121">Wenn Sie Ihre Anwendung auf .NET 5 aktualisieren, bemerken Sie möglicherweise Änderungen in Ihrer Anwendung, auch wenn Sie sich nicht bewusst sind, dass Sie Globalisierungsfunktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="fadea-121">If you upgrade your app to target .NET 5, you might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="fadea-122">In diesem Abschnitt finden Sie eine der Behavior Changes, die Sie möglicherweise beobachten, aber es gibt noch weitere.</span><span class="sxs-lookup"><span data-stu-id="fadea-122">This section lists one of the behavioral changes you might see, but there are others too.</span></span>

##### <a name="stringindexof"></a><span data-ttu-id="fadea-123">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="fadea-123">String.IndexOf</span></span>

<span data-ttu-id="fadea-124">Betrachten Sie den folgenden Code, der <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> aufruft, um den Index des Zeilenvorschubzeichens in einer Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="fadea-124">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="fadea-125">In früheren Versionen von .NET unter Windows gibt der Ausschnitt `6` aus.</span><span class="sxs-lookup"><span data-stu-id="fadea-125">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="fadea-126">Ab .NET 5.0 unter Windows 10 (Update vom 10. Mai 2019) und höheren Versionen gibt der Ausschnitt `-1` aus.</span><span class="sxs-lookup"><span data-stu-id="fadea-126">In .NET 5.0 and later versions on Windows 10 May 2019 Update and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="fadea-127">Um diesen Code durch eine ordinale Suche anstelle einer kulturabhängigen Suche zu korrigieren, rufen Sie die Überladung <xref:System.String.IndexOf(System.String,System.StringComparison)> auf, an die Sie <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="fadea-127">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="fadea-128">Sie können Codeanalyseregeln entsprechend [CA1307: Angeben von StringComparison für mehr Klarheit](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) und [CA1309: Verwenden eines ordinalen StringComparison](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) ausführen, um diese Aufrufstellen in Ihrem Code zu finden.</span><span class="sxs-lookup"><span data-stu-id="fadea-128">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="fadea-129">Weitere Informationen finden Sie unter [Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5](../base-types/string-comparison-net-5-plus.md).</span><span class="sxs-lookup"><span data-stu-id="fadea-129">For more information, see [Behavior changes when comparing strings on .NET 5+](../base-types/string-comparison-net-5-plus.md).</span></span>

### <a name="use-nls-instead-of-icu"></a><span data-ttu-id="fadea-130">Verwenden von NLS anstelle von ICU</span><span class="sxs-lookup"><span data-stu-id="fadea-130">Use NLS instead of ICU</span></span>

<span data-ttu-id="fadea-131">Die Verwendung von ICU anstelle von NLS kann zu Verhaltensunterschieden bei einigen globalisierungsbezogenen Vorgängen führen.</span><span class="sxs-lookup"><span data-stu-id="fadea-131">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="fadea-132">Um wieder NLS zu verwenden, kann ein Entwickler die ICU-Implementierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fadea-132">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="fadea-133">Anwendungen können den NLS-Modus auf eine der folgenden Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="fadea-133">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="fadea-134">In der Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="fadea-134">In the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="fadea-135">In der Datei `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="fadea-135">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.UseNls": true
        }
    }
  }
  ```

- <span data-ttu-id="fadea-136">Durch Festlegen der Umgebungsvariablen `DOTNET_SYSTEM_GLOBALIZATION_USENLS` auf den Wert `true` oder `1`.</span><span class="sxs-lookup"><span data-stu-id="fadea-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="fadea-137">Ein im Projekt oder in der Datei `runtimeconfig.json` festgelegter Wert hat Vorrang vor der Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="fadea-137">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="fadea-138">Weitere Informationen finden Sie unter [Laufzeitkonfigurationseinstellungen](../../core/run-time-config/globalization.md#nls).</span><span class="sxs-lookup"><span data-stu-id="fadea-138">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="fadea-139">App-lokale ICU</span><span class="sxs-lookup"><span data-stu-id="fadea-139">App-local ICU</span></span>

<span data-ttu-id="fadea-140">Jedes Release von ICU kann Fehlerbehebungen sowie aktualisierte CLDR-Daten (Common Locale Data Repository) enthalten, die die Sprachen der Welt beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fadea-140">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="fadea-141">Der Wechsel zwischen ICU-Versionen kann das Verhalten von Apps subtil beeinflussen, wenn es um globalisierungsbezogene Vorgänge geht.</span><span class="sxs-lookup"><span data-stu-id="fadea-141">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span> <span data-ttu-id="fadea-142">Damit Anwendungsentwickler Konsistenz über alle Bereitstellungen hinweg sicherstellen können, ermöglichen .NET 5.0 und höhere Versionen Apps unter Windows und UNIX das Einbinden und Verwenden ihrer eigenen Kopie von ICU.</span><span class="sxs-lookup"><span data-stu-id="fadea-142">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="fadea-143">Anwendungen können einen App-lokalen ICU-Implementierungsmodus auf eine der folgenden Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="fadea-143">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="fadea-144">In der Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="fadea-144">In  the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
  </ItemGroup>
  ```

- <span data-ttu-id="fadea-145">In der Datei `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="fadea-145">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
       }
    }
  }
  ```

- <span data-ttu-id="fadea-146">Durch Festlegen der Umgebungsvariablen `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` auf den Wert `<suffix>:<version>` oder `<version>`.</span><span class="sxs-lookup"><span data-stu-id="fadea-146">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

  <span data-ttu-id="fadea-147">`<suffix>`: Optionales Suffix mit weniger als 36 Zeichen gemäß den öffentlichen ICU-Paketkonventionen.</span><span class="sxs-lookup"><span data-stu-id="fadea-147">`<suffix>`: Optional suffix of fewer than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="fadea-148">Wenn Sie eine benutzerdefinierte ICU-Bibliothek erstellt haben, können Sie diese so anpassen, dass die Bibliotheksnamen und exportierten Symbolnamen mit einem Suffix erstellt werden, z. B. `libicuucmyapp`, wobei `myapp` das Suffix ist.</span><span class="sxs-lookup"><span data-stu-id="fadea-148">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

  <span data-ttu-id="fadea-149">`<version>`: Eine gültige ICU-Version, z. B. 67.1.</span><span class="sxs-lookup"><span data-stu-id="fadea-149">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="fadea-150">Diese Version wird zum Laden der Binärdateien und zum Abrufen der exportierten Symbole verwendet.</span><span class="sxs-lookup"><span data-stu-id="fadea-150">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="fadea-151">Wenn Sie ICU laden möchten, wenn der App-lokale Switch festgelegt ist, verwendet .NET die <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>-Methode, die mehrere Pfade überprüft.</span><span class="sxs-lookup"><span data-stu-id="fadea-151">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="fadea-152">Die Methode versucht zuerst, die Bibliothek in der `NATIVE_DLL_SEARCH_DIRECTORIES`-Eigenschaft zu finden, die vom dotnet-Host basierend auf der Datei `deps.json` für die App erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fadea-152">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="fadea-153">Weitere Informationen finden Sie unter [Standardüberprüfung](../../core/dependency-loading/default-probing.md).</span><span class="sxs-lookup"><span data-stu-id="fadea-153">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="fadea-154">Für eigenständige Apps sind keine besonderen Aktionen durch den Benutzer erforderlich. Es muss nur sichergestellt werden, dass sich die ICU-Bibliothek im App-Verzeichnis befindet (für eigenständige Apps ist das Arbeitsverzeichnis standardmäßig `NATIVE_DLL_SEARCH_DIRECTORIES`).</span><span class="sxs-lookup"><span data-stu-id="fadea-154">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="fadea-155">Wenn Sie ICU mithilfe eines NuGet-Pakets nutzen, funktioniert dies in frameworkabhängigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fadea-155">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="fadea-156">NuGet löst die nativen Ressourcen auf und bindet sie in die Datei `deps.json` sowie in das Ausgabeverzeichnis für die Anwendung im Verzeichnis `runtimes`.</span><span class="sxs-lookup"><span data-stu-id="fadea-156">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="fadea-157">.NET lädt Sie von dort.</span><span class="sxs-lookup"><span data-stu-id="fadea-157">.NET loads it from there.</span></span>

<span data-ttu-id="fadea-158">Für frameworkabhängige Apps (nicht eigenständig), in denen ICU aus einem lokalen Build genutzt wird, müssen Sie zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="fadea-158">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="fadea-159">Das .NET SDK verfügt noch nicht über eine Funktion, die „lose“ native Binärdateien in `deps.json` integriert (weitere Informationen dazu finden Sie in [diesem SDK-Problem](https://github.com/dotnet/sdk/issues/11373)).</span><span class="sxs-lookup"><span data-stu-id="fadea-159">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="fadea-160">Stattdessen können Sie dies aktivieren, indem Sie der Projektdatei der Anwendung zusätzliche Informationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fadea-160">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="fadea-161">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fadea-161">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="fadea-162">Dies muss für alle ICU-Binärdateien für die unterstützten Laufzeiten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fadea-162">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="fadea-163">Außerdem müssen die `NuGetPackageId`-Metadaten in der `RuntimeTargetsCopyLocalItems`-Elementgruppe mit einem NuGet-Paket übereinstimmen, auf das das Projekt tatsächlich verweist.</span><span class="sxs-lookup"><span data-stu-id="fadea-163">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="fadea-164">macOS-Verhalten</span><span class="sxs-lookup"><span data-stu-id="fadea-164">macOS behavior</span></span>

<span data-ttu-id="fadea-165">`macOS` weist ein anderes Verhalten zum Auflösen abhängiger dynamischer Bibliotheken aus den in der `match-o`-Datei angegebenen Ladebefehlen als das Linux-Lademodul auf.</span><span class="sxs-lookup"><span data-stu-id="fadea-165">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="fadea-166">Im Linux-Lademodul kann .NET versuchen, `libicudata`, `libicuuc` und `libicui18n` (in dieser Reihenfolge) zu verwenden, um das ICU-Abhängigkeitsdiagramm zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fadea-166">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="fadea-167">Unter macOS funktioniert dies jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="fadea-167">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="fadea-168">Wenn Sie ICU unter macOS erstellen, erhalten Sie standardmäßig eine dynamische Bibliothek mit diesen Ladebefehlen in `libicuuc`.</span><span class="sxs-lookup"><span data-stu-id="fadea-168">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="fadea-169">Der folgende Ausschnitt zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fadea-169">The following snippet shows an example.</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="fadea-170">Diese Befehle verweisen nur auf den Namen der abhängigen Bibliotheken für die anderen Komponenten von ICU.</span><span class="sxs-lookup"><span data-stu-id="fadea-170">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="fadea-171">Das Lademodul führt die Suche nach den `dlopen`-Konventionen durch, wobei diese Bibliotheken in den Systemverzeichnissen enthalten sind oder die `LD_LIBRARY_PATH`-Umgebungsvariablen festgelegt werden oder sich ICU im Verzeichnis auf App-Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="fadea-171">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="fadea-172">Wenn Sie `LD_LIBRARY_PATH` nicht festlegen oder sicherstellen können, dass sich die ICU-Binärdateien im Verzeichnis auf App-Ebene befinden, müssen Sie zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="fadea-172">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="fadea-173">Es gibt einige Direktiven für das Ladeprogramm (z. B. `@loader_path`), die das Ladeprogramm anweisen, diese Abhängigkeit im gleichen Verzeichnis wie die Binärdatei mit diesem Ladebefehl zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fadea-173">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="fadea-174">Es gibt zwei Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="fadea-174">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="fadea-175">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="fadea-175">Run the following commands:</span></span>

  ```bash
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
  install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
  ```

- <span data-ttu-id="fadea-176">Patchen von ICU zum Generieren der Installationsnamen mit `@loader_path`</span><span class="sxs-lookup"><span data-stu-id="fadea-176">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="fadea-177">Ändern Sie vor dem Ausführen der automatischen Konfiguration (`./runConfigureICU`) [diese Zeilen](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fadea-177">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

  ```
  LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
  ```

## <a name="icu-on-webassembly"></a><span data-ttu-id="fadea-178">ICU für WebAssembly</span><span class="sxs-lookup"><span data-stu-id="fadea-178">ICU on WebAssembly</span></span>

<span data-ttu-id="fadea-179">Eine Version von ICU ist verfügbar, die speziell für WebAssembly-Workloads gilt.</span><span class="sxs-lookup"><span data-stu-id="fadea-179">A version of ICU is available that's specifically for WebAssembly workloads.</span></span> <span data-ttu-id="fadea-180">Diese Version bietet Globalisierungskompatibilität mit Desktopprofilen.</span><span class="sxs-lookup"><span data-stu-id="fadea-180">This version provides globalization compatibility with desktop profiles.</span></span> <span data-ttu-id="fadea-181">Um die ICU-Datendateigröße von 24 MB auf 1,4 MB zu reduzieren (oder etwa 0,3 MB bei Komprimierung mit Brotli), weist diese Workload einige Einschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="fadea-181">To reduce the ICU data file size from 24 MB to 1.4 MB (or ~0.3 MB if compressed with Brotli), this workload has a handful of limitations.</span></span>

<span data-ttu-id="fadea-182">Folgende APIs werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="fadea-182">The following APIs are not supported:</span></span>

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

<span data-ttu-id="fadea-183">Die folgenden APIs werden mit Einschränkungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="fadea-183">The following APIs are supported with limitations:</span></span>

- <span data-ttu-id="fadea-184"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> und <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> unterstützen die selten verwendeten <xref:System.Text.NormalizationForm.FormKC>- und <xref:System.Text.NormalizationForm.FormKD>-Formulare nicht.</span><span class="sxs-lookup"><span data-stu-id="fadea-184"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> and <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> don't support the rarely used <xref:System.Text.NormalizationForm.FormKC> and <xref:System.Text.NormalizationForm.FormKD> forms.</span></span>
- <span data-ttu-id="fadea-185"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> gibt denselben Wert zurück wie <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fadea-185"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> returns the same value as <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="fadea-186">Außerdem finden Sie eine Liste der unterstützten Gebietsschemas im [dotnet/icu-Repository](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span><span class="sxs-lookup"><span data-stu-id="fadea-186">In addition, a list of supported locales can be found on the [dotnet/icu repo](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span></span>
