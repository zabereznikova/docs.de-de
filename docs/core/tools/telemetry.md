---
title: .NET Core SDK-Telemetrie
description: Entdecken Sie die Telemetriefunktionen des .NET Core SDK, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie auch, wie Sie diese Features deaktivieren können.
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 40d9f3f698f513306e087753b4c33d09e8df0046
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397755"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="c62e2-103">.NET Core SDK-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="c62e2-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="c62e2-104">Das [.NET Core-SDK](index.md) beinhaltet eine [Telemetriefunktion](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry), die Benutzerinformationen sammelt.</span><span class="sxs-lookup"><span data-stu-id="c62e2-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="c62e2-105">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="c62e2-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="c62e2-106">Weitere Informationen finden Sie unter [What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core SDK Telemetrie gelernt haben)](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="c62e2-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="c62e2-107">Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von der Community veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c62e2-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="c62e2-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="c62e2-108">Scope</span></span>

<span data-ttu-id="c62e2-109">Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-CLI verwendet.</span><span class="sxs-lookup"><span data-stu-id="c62e2-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="c62e2-110">Der `dotnet`-Befehl selbst sammelt keine Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="c62e2-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="c62e2-111">Die .NET Core-CLI-Befehle, die vom Befehl `dotnet` ausgeführt werden, sammeln die Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="c62e2-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="c62e2-112">Die Telemetrie wird durch die Verwendung des Befehls `dotnet` allein *nicht aktiviert*, wenn kein Befehl angefügt ist:</span><span class="sxs-lookup"><span data-stu-id="c62e2-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="c62e2-113">Die Telemetrie wird *aktiviert*, wenn Sie die [.NET Core-CLI-Befehle](index.md) verwenden, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c62e2-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="c62e2-114">Deaktivierung der Telemetriefunktion</span><span class="sxs-lookup"><span data-stu-id="c62e2-114">How to opt out</span></span>

<span data-ttu-id="c62e2-115">Die Telemetriefeature des .NET Core SDK ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c62e2-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="c62e2-116">Deaktivieren Sie die Telemetriefeature, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="c62e2-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="c62e2-117">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="c62e2-117">Data points</span></span>

<span data-ttu-id="c62e2-118">Die Funktion sammelt die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="c62e2-118">The feature collects the following data:</span></span>

- <span data-ttu-id="c62e2-119">Den Zeitstempel des Aufrufs&#8224;</span><span class="sxs-lookup"><span data-stu-id="c62e2-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="c62e2-120">Den aufgerufenen Befehl (zum Beispiel „build“)&#8224;</span><span class="sxs-lookup"><span data-stu-id="c62e2-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="c62e2-121">Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c62e2-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="c62e2-122">`ExitCode` des Befehls</span><span class="sxs-lookup"><span data-stu-id="c62e2-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="c62e2-123">Test Runner (für Testprojekte)</span><span class="sxs-lookup"><span data-stu-id="c62e2-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="c62e2-124">Betriebssystem und Version&#8224;</span><span class="sxs-lookup"><span data-stu-id="c62e2-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="c62e2-125">Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="c62e2-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="c62e2-126">Die .NET Core SDK-Version&#8224;</span><span class="sxs-lookup"><span data-stu-id="c62e2-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="c62e2-127">&#8224;Diese Metrik wird veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c62e2-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="c62e2-128">Ab dem .NET Core 2.0 SDK werden neue Datenpunkte gesammelt:</span><span class="sxs-lookup"><span data-stu-id="c62e2-128">Starting with .NET Core 2.0 SDK, new data points are collected:</span></span>

- <span data-ttu-id="c62e2-129">Argumente und Optionen des Befehls `dotnet`: nur bekannte Argumente und Optionen werden gesammelt (keine beliebigen Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="c62e2-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="c62e2-130">Ob das SDK in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c62e2-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="c62e2-131">Zielframeworks.</span><span class="sxs-lookup"><span data-stu-id="c62e2-131">Target frameworks.</span></span>
- <span data-ttu-id="c62e2-132">MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer.</span><span class="sxs-lookup"><span data-stu-id="c62e2-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="c62e2-133">Diese Metrik wird nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c62e2-133">This metric isn't published.</span></span>
- <span data-ttu-id="c62e2-134">Das derzeitige Arbeitsverzeichnis mit Hash.</span><span class="sxs-lookup"><span data-stu-id="c62e2-134">Hashed current working directory.</span></span>

<span data-ttu-id="c62e2-135">Die Funktion sammelt keine Daten wie z.B. Benutzernamen oder E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="c62e2-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="c62e2-136">Es scannt Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene, zum Beispiel Name, Repository oder Autor.</span><span class="sxs-lookup"><span data-stu-id="c62e2-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="c62e2-137">Die Daten werden mithilfe der Technologie [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c62e2-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="c62e2-138">Das .NET-Team ist daran interessiert, wie die Tools verwendet werden und ob sie gut funktionieren, nicht was Sie mit den Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="c62e2-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="c62e2-139">Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten gesammelt oder die Daten nicht sicher oder ordnungsgemäß behandelt werden, melden Sie ein Problem mit dem [dotnet/cli](https://github.com/dotnet/cli/issues)-Repository, damit dieses untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="c62e2-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="c62e2-140">Veröffentlichte Daten</span><span class="sxs-lookup"><span data-stu-id="c62e2-140">Published data</span></span>

<span data-ttu-id="c62e2-141">Veröffentlichte Daten sind vierteljährlich verfügbar und werden unter [.NET Core SDK Usage Data (.NET Core SDK Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c62e2-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="c62e2-142">Die Spalten der Datendatei sind:</span><span class="sxs-lookup"><span data-stu-id="c62e2-142">The columns of a data file are:</span></span>

- <span data-ttu-id="c62e2-143">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c62e2-143">Timestamp</span></span>
- <span data-ttu-id="c62e2-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="c62e2-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="c62e2-145">Befehl</span><span class="sxs-lookup"><span data-stu-id="c62e2-145">Command</span></span>
- <span data-ttu-id="c62e2-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="c62e2-146">Geography&#8225;</span></span>
- <span data-ttu-id="c62e2-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="c62e2-147">OSFamily</span></span>
- <span data-ttu-id="c62e2-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="c62e2-148">RuntimeID</span></span>
- <span data-ttu-id="c62e2-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="c62e2-149">OSVersion</span></span>
- <span data-ttu-id="c62e2-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="c62e2-150">SDKVersion</span></span>

<span data-ttu-id="c62e2-151">Die Spalte *Occurences* zeigt die Gesamtanzahl der Verwendung dieses Befehls für die Metriken dieser Reihe an diesem Tag an.</span><span class="sxs-lookup"><span data-stu-id="c62e2-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="c62e2-152">&#8225;Die Spalte *Geography* zeigt normalerweise den Namen eines Landes oder einer Region an.</span><span class="sxs-lookup"><span data-stu-id="c62e2-152">&#8225;Typically, the *Geography* column displays the name of a country/region.</span></span> <span data-ttu-id="c62e2-153">In einigen Fällen wird der Kontinent Antarktis in dieser Spalte angezeigt. Dies geschieht entweder, weil Experten .NET Core in der Antarktis verwenden oder wegen falschen Standortdaten.</span><span class="sxs-lookup"><span data-stu-id="c62e2-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="c62e2-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c62e2-154">Example</span></span>

| <span data-ttu-id="c62e2-155">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c62e2-155">Timestamp</span></span>      | <span data-ttu-id="c62e2-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="c62e2-156">Occurrences</span></span> | <span data-ttu-id="c62e2-157">Befehl</span><span class="sxs-lookup"><span data-stu-id="c62e2-157">Command</span></span> | <span data-ttu-id="c62e2-158">Geography</span><span class="sxs-lookup"><span data-stu-id="c62e2-158">Geography</span></span> | <span data-ttu-id="c62e2-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="c62e2-159">OSFamily</span></span> | <span data-ttu-id="c62e2-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="c62e2-160">RuntimeID</span></span>     | <span data-ttu-id="c62e2-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="c62e2-161">OSVersion</span></span> | <span data-ttu-id="c62e2-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="c62e2-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="c62e2-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="c62e2-163">4/16/2017 0:00</span></span> | <span data-ttu-id="c62e2-164">8</span><span class="sxs-lookup"><span data-stu-id="c62e2-164">8</span></span>           | <span data-ttu-id="c62e2-165">Ausführung</span><span class="sxs-lookup"><span data-stu-id="c62e2-165">run</span></span>     | <span data-ttu-id="c62e2-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="c62e2-166">Uganda</span></span>    | <span data-ttu-id="c62e2-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="c62e2-167">Darwin</span></span>   | <span data-ttu-id="c62e2-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="c62e2-168">osx.10.12-x64</span></span> | <span data-ttu-id="c62e2-169">10.12</span><span class="sxs-lookup"><span data-stu-id="c62e2-169">10.12</span></span>     | <span data-ttu-id="c62e2-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="c62e2-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="c62e2-171">Datasets</span><span class="sxs-lookup"><span data-stu-id="c62e2-171">Datasets</span></span>

- [<span data-ttu-id="c62e2-172">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="c62e2-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)
- [<span data-ttu-id="c62e2-173">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="c62e2-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)
- [<span data-ttu-id="c62e2-174">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="c62e2-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)
- [<span data-ttu-id="c62e2-175">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="c62e2-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)
- [<span data-ttu-id="c62e2-176">2017 – Q3</span><span class="sxs-lookup"><span data-stu-id="c62e2-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)
- [<span data-ttu-id="c62e2-177">2017 – Q4</span><span class="sxs-lookup"><span data-stu-id="c62e2-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)

<span data-ttu-id="c62e2-178">Zusätzliche Datasets werden mithilfe des Standardformat für URLs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c62e2-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="c62e2-179">Ersetzen Sie `<YEAR>` durch das Jahr und `<QUARTER>` durch das Quartal des Jahrs (verwenden Sie `1`, `2`, `3` oder `4`).</span><span class="sxs-lookup"><span data-stu-id="c62e2-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="c62e2-180">Die Dateien befinden sich im Format einer durch Tabstopp getrennten Datei (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="c62e2-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="c62e2-181">Lizenz</span><span class="sxs-lookup"><span data-stu-id="c62e2-181">License</span></span>

<span data-ttu-id="c62e2-182">Die Microsoft-Verteilung von .NET Core ist lizenziert gemäß den [Microsoft-Softwarelizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula) lizenziert.</span><span class="sxs-lookup"><span data-stu-id="c62e2-182">The Microsoft distribution of .NET Core is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="c62e2-183">Ausführlichere Informationen zur Datensammlung und -verarbeitung finden Sie im Abschnitt „Daten“.</span><span class="sxs-lookup"><span data-stu-id="c62e2-183">For details on data collection and processing, see the section entitled "Data."</span></span>

<span data-ttu-id="c62e2-184">[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope)).</span><span class="sxs-lookup"><span data-stu-id="c62e2-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

## <a name="disclosure"></a><span data-ttu-id="c62e2-185">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="c62e2-185">Disclosure</span></span>

<span data-ttu-id="c62e2-186">Im .NET Core SDK wird beim ersten Ausführen eines der [.NET Core-CLI-Befehle](index.md) (z.B. `dotnet restore`) der folgende Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c62e2-186">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="c62e2-187">Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="c62e2-187">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="c62e2-188">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="c62e2-188">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a><span data-ttu-id="c62e2-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c62e2-189">See also</span></span>

- [<span data-ttu-id="c62e2-190">What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core-SDK-Telemetrie gelernt haben)</span><span class="sxs-lookup"><span data-stu-id="c62e2-190">What we've learned from .NET Core SDK Telemetry</span></span>](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)
- [<span data-ttu-id="c62e2-191">Telemetrieverweisquelle (dotnet/cli-Repository)</span><span class="sxs-lookup"><span data-stu-id="c62e2-191">Telemetry reference source (dotnet/cli repo)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [<span data-ttu-id="c62e2-192">.NET Core SDK Usage Data (.NET Core SDK-Nutzungsdaten)</span><span class="sxs-lookup"><span data-stu-id="c62e2-192">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
