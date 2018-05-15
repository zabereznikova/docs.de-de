---
title: .NET Core-CLI-Tools-Telemetrie
description: Entdecken Sie die Telemetriefunktionen der .NET Core-Tools, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden und wie sie deaktiviert werden.
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.openlocfilehash: 4c04867f5db512ef53c23ec41ea66db570a82021
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="2d32f-103">.NET Core-CLI-Tools-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="2d32f-103">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="2d32f-104">Das [.NET Core-SDK](index.md) beinhaltet eine [Telemetriefunktion](https://github.com/dotnet/cli/pull/2145), die Benutzerinformationen sammelt.</span><span class="sxs-lookup"><span data-stu-id="2d32f-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="2d32f-105">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="2d32f-105">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="2d32f-106">Weitere Informationen finden Sie unter [What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core SDK Telemetrie gelernt haben)](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="2d32f-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="2d32f-107">Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von der Community veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="2d32f-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="2d32f-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="2d32f-108">Scope</span></span>

<span data-ttu-id="2d32f-109">Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-CLI verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d32f-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="2d32f-110">Der `dotnet`-Befehl selbst sammelt keine Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="2d32f-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="2d32f-111">Die .NET Core-CLI-Befehle, die vom Befehl `dotnet` ausgeführt werden, sammeln die Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="2d32f-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="2d32f-112">Die Telemetrie wird durch die Verwendung des Befehls `dotnet` allein *nicht aktiviert*, wenn kein Befehl angefügt ist:</span><span class="sxs-lookup"><span data-stu-id="2d32f-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="2d32f-113">Die Telemetrie wird *aktiviert*, wenn Sie die [.NET Core-CLI-Befehle](index.md) verwenden, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2d32f-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a><span data-ttu-id="2d32f-114">Verhalten</span><span class="sxs-lookup"><span data-stu-id="2d32f-114">Behavior</span></span>

<span data-ttu-id="2d32f-115">Die Telemetriefunktion der .NET Core-CLI ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2d32f-115">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="2d32f-116">Deaktivieren Sie die Telemetriefunktion, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2d32f-116">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="2d32f-117">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="2d32f-117">Data points</span></span>

<span data-ttu-id="2d32f-118">Die Funktion sammelt die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="2d32f-118">The feature collects the following data:</span></span>

- <span data-ttu-id="2d32f-119">Den Zeitstempel des Aufrufs&#8224;</span><span class="sxs-lookup"><span data-stu-id="2d32f-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="2d32f-120">Den aufgerufenen Befehl (zum Beispiel „build“)&#8224;</span><span class="sxs-lookup"><span data-stu-id="2d32f-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="2d32f-121">Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="2d32f-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="2d32f-122">`ExitCode` des Befehls</span><span class="sxs-lookup"><span data-stu-id="2d32f-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="2d32f-123">Test Runner (für Testprojekte)</span><span class="sxs-lookup"><span data-stu-id="2d32f-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="2d32f-124">Betriebssystem und Version&#8224;</span><span class="sxs-lookup"><span data-stu-id="2d32f-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="2d32f-125">Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="2d32f-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="2d32f-126">Die .NET Core SDK-Version&#8224;</span><span class="sxs-lookup"><span data-stu-id="2d32f-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="2d32f-127">&#8224;Diese Metrik wird veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="2d32f-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="2d32f-128">Ab dem .NET Core SDK 2.0 werden neue Datenpunkte gesammelt:</span><span class="sxs-lookup"><span data-stu-id="2d32f-128">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="2d32f-129">Argumente und Optionen des Befehls `dotnet`: nur bekannte Argumente und Optionen werden gesammelt (keine beliebigen Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="2d32f-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="2d32f-130">Ob das SDK in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d32f-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="2d32f-131">Zielframeworks.</span><span class="sxs-lookup"><span data-stu-id="2d32f-131">Target frameworks.</span></span>
- <span data-ttu-id="2d32f-132">MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d32f-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="2d32f-133">Diese Metrik wird nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="2d32f-133">This metric is not published.</span></span>
- <span data-ttu-id="2d32f-134">Das derzeitige Arbeitsverzeichnis mit Hash.</span><span class="sxs-lookup"><span data-stu-id="2d32f-134">Hashed current working directory.</span></span>

<span data-ttu-id="2d32f-135">Die Funktion sammelt keine Daten wie z.B. Benutzernamen oder E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="2d32f-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="2d32f-136">Es scannt Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene, zum Beispiel Name, Repository oder Autor.</span><span class="sxs-lookup"><span data-stu-id="2d32f-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="2d32f-137">Die Daten werden mithilfe der Technologie [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="2d32f-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="2d32f-138">Wir würden gern wissen, wie die Tools verwendet werden und ob sie gut funktionieren, nicht was Sie mit den Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d32f-138">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="2d32f-139">Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten gesammelt werden oder wir die Daten nicht sicher oder ordnungsgemäß behandeln, [file an issue in the dotnet/cli repo issues (melden Sie ein Problem in den dotnet- oder CLI-Repository-Problemen)](https://github.com/dotnet/cli/issues) zur Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="2d32f-139">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="2d32f-140">Veröffentlichte Daten</span><span class="sxs-lookup"><span data-stu-id="2d32f-140">Published data</span></span>

<span data-ttu-id="2d32f-141">Veröffentlichte Daten sind vierteljährlich verfügbar und werden unter [.NET Core SDK Usage Data (.NET Core SDK Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2d32f-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="2d32f-142">Die Spalten der Datendatei sind:</span><span class="sxs-lookup"><span data-stu-id="2d32f-142">The columns of a data file are:</span></span>
- <span data-ttu-id="2d32f-143">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="2d32f-143">Timestamp</span></span>
- <span data-ttu-id="2d32f-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="2d32f-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="2d32f-145">Befehl</span><span class="sxs-lookup"><span data-stu-id="2d32f-145">Command</span></span>
- <span data-ttu-id="2d32f-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="2d32f-146">Geography&#8225;</span></span>
- <span data-ttu-id="2d32f-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="2d32f-147">OSFamily</span></span>
- <span data-ttu-id="2d32f-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="2d32f-148">RuntimeID</span></span>
- <span data-ttu-id="2d32f-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="2d32f-149">OSVersion</span></span>
- <span data-ttu-id="2d32f-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="2d32f-150">SDKVersion</span></span>

<span data-ttu-id="2d32f-151">Die Spalte *Occurences* zeigt die Gesamtanzahl der Verwendung dieses Befehls für die Metriken dieser Reihe an diesem Tag an.</span><span class="sxs-lookup"><span data-stu-id="2d32f-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="2d32f-152">Die Spalte *Geography* zeigt normalerweise den Namen eines Landes an.</span><span class="sxs-lookup"><span data-stu-id="2d32f-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="2d32f-153">In einigen Fällen wird der Kontinent Antarktis in dieser Spalte angezeigt. Dies geschieht entweder, weil Experten .NET Core in der Antarktis verwenden oder wegen falschen Standortdaten.</span><span class="sxs-lookup"><span data-stu-id="2d32f-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="2d32f-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d32f-154">Example</span></span>

| <span data-ttu-id="2d32f-155">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="2d32f-155">Timestamp</span></span>      | <span data-ttu-id="2d32f-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="2d32f-156">Occurrences</span></span> | <span data-ttu-id="2d32f-157">Befehl</span><span class="sxs-lookup"><span data-stu-id="2d32f-157">Command</span></span> | <span data-ttu-id="2d32f-158">Geography</span><span class="sxs-lookup"><span data-stu-id="2d32f-158">Geography</span></span> | <span data-ttu-id="2d32f-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="2d32f-159">OSFamily</span></span> | <span data-ttu-id="2d32f-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="2d32f-160">RuntimeID</span></span>     | <span data-ttu-id="2d32f-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="2d32f-161">OSVersion</span></span> | <span data-ttu-id="2d32f-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="2d32f-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="2d32f-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="2d32f-163">4/16/2017 0:00</span></span> | <span data-ttu-id="2d32f-164">8</span><span class="sxs-lookup"><span data-stu-id="2d32f-164">8</span></span>           | <span data-ttu-id="2d32f-165">Ausführung</span><span class="sxs-lookup"><span data-stu-id="2d32f-165">run</span></span>     | <span data-ttu-id="2d32f-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="2d32f-166">Uganda</span></span>    | <span data-ttu-id="2d32f-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="2d32f-167">Darwin</span></span>   | <span data-ttu-id="2d32f-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="2d32f-168">osx.10.12-x64</span></span> | <span data-ttu-id="2d32f-169">10.12</span><span class="sxs-lookup"><span data-stu-id="2d32f-169">10.12</span></span>     | <span data-ttu-id="2d32f-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="2d32f-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="2d32f-171">Datasets</span><span class="sxs-lookup"><span data-stu-id="2d32f-171">Datasets</span></span>

[<span data-ttu-id="2d32f-172">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="2d32f-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="2d32f-173">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="2d32f-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="2d32f-174">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="2d32f-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="2d32f-175">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="2d32f-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="2d32f-176">Zusätzliche Datasets werden mithilfe des Standardformat für URLs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2d32f-176">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="2d32f-177">Ersetzen Sie `<YEAR>` durch das Jahr und `<QUARTER>` durch das Quartal des Jahrs (verwenden Sie `1`, `2`, `3` oder `4`).</span><span class="sxs-lookup"><span data-stu-id="2d32f-177">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="2d32f-178">Die Dateien befinden sich im Format einer durch Tabstopp getrennten Datei (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="2d32f-178">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="2d32f-179">Lizenz</span><span class="sxs-lookup"><span data-stu-id="2d32f-179">License</span></span>

<span data-ttu-id="2d32f-180">Die Microsoft-Verteilung von .NET Core ist lizenziert mit den [Lizenzbedingungen der Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="2d32f-180">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="2d32f-181">Diese Lizenz enthält den Abschnitt „DATA“ (Daten) zum Aktivieren von Telemetrie (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="2d32f-181">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="2d32f-182">[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope)).</span><span class="sxs-lookup"><span data-stu-id="2d32f-182">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="2d32f-183">Daten</span><span class="sxs-lookup"><span data-stu-id="2d32f-183">DATA.</span></span> <span data-ttu-id="2d32f-184">Die Software sammelt möglicherweise Daten zum Benutzer und zur Nutzung der Software und übermittelt diese an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d32f-184">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="2d32f-185">Microsoft kann diese Informationen verwenden, um seine Produkte und -Dienste zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2d32f-185">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="2d32f-186">Weitere Informationen zur Datenerfassung und -verwendung finden Sie in der Hilfedokumentation und in den Datenschutzbestimmungen unter http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="2d32f-186">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="2d32f-187">Ihre Verwendung der Software gilt als Zustimmung zu diesen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="2d32f-187">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="2d32f-188">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="2d32f-188">Disclosure</span></span>

<span data-ttu-id="2d32f-189">In den .NET Core-CLI-Tools wird beim ersten Ausführen einer der Befehle (z.B. `dotnet restore`) der folgende Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d32f-189">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="2d32f-190">Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="2d32f-190">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="2d32f-191">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="2d32f-191">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a><span data-ttu-id="2d32f-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d32f-192">See also</span></span>

[<span data-ttu-id="2d32f-193">What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core-SDK-Telemetrie gelernt haben)</span><span class="sxs-lookup"><span data-stu-id="2d32f-193">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
<span data-ttu-id="2d32f-194">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch) (Verweisquelle der Telemetrie (dotnet-/CLI-Repository, Version 2.0.0 Branch)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span><span class="sxs-lookup"><span data-stu-id="2d32f-194">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span></span>  
[<span data-ttu-id="2d32f-195">.NET Core SDK Usage Data (.NET Core SDK-Nutzungsdaten)</span><span class="sxs-lookup"><span data-stu-id="2d32f-195">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
