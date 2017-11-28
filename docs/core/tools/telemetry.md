---
title: .NET Core-CLI-Tools-Telemetrie
description: "Entdecken Sie die Telemetriefunktionen der .NET Core-Tools, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden und wie sie deaktiviert werden."
keywords: .NET, .NET Core, telemetrie
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.openlocfilehash: 34183792a235391f66fbec211ff00f06f85134fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="c5c6e-104">.NET Core-CLI-Tools-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="c5c6e-104">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="c5c6e-105">Das [.NET Core-SDK](index.md) beinhaltet eine [Telemetriefunktion](https://github.com/dotnet/cli/pull/2145), die Benutzerinformationen sammelt.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-105">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="c5c6e-106">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-106">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="c5c6e-107">Weitere Informationen finden Sie unter [What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core SDK Telemetrie gelernt haben)](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-107">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="c5c6e-108">Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von der Community veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-108">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="c5c6e-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="c5c6e-109">Scope</span></span>

<span data-ttu-id="c5c6e-110">Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-CLI verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-110">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="c5c6e-111">Der `dotnet`-Befehl selbst sammelt keine Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-111">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="c5c6e-112">Die .NET Core-CLI-Befehle, die vom Befehl `dotnet` ausgeführt werden, sammeln die Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-112">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="c5c6e-113">Die Telemetrie wird durch die Verwendung des Befehls `dotnet` allein *nicht aktiviert*, wenn kein Befehl angefügt ist:</span><span class="sxs-lookup"><span data-stu-id="c5c6e-113">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="c5c6e-114">Die Telemetrie wird *aktiviert*, wenn Sie die [.NET Core-CLI-Befehle](index.md) verwenden, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c5c6e-114">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a><span data-ttu-id="c5c6e-115">Verhalten</span><span class="sxs-lookup"><span data-stu-id="c5c6e-115">Behavior</span></span>

<span data-ttu-id="c5c6e-116">Die Telemetriefunktion der .NET Core-CLI ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-116">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="c5c6e-117">Deaktivieren Sie die Telemetriefunktion, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-117">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="c5c6e-118">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="c5c6e-118">Data points</span></span>

<span data-ttu-id="c5c6e-119">Die Funktion sammelt die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="c5c6e-119">The feature collects the following data:</span></span>

- <span data-ttu-id="c5c6e-120">Den Zeitstempel des Aufrufs&#8224;</span><span class="sxs-lookup"><span data-stu-id="c5c6e-120">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="c5c6e-121">Den aufgerufenen Befehl (zum Beispiel „build“)&#8224;</span><span class="sxs-lookup"><span data-stu-id="c5c6e-121">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="c5c6e-122">Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c5c6e-122">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="c5c6e-123">`ExitCode` des Befehls</span><span class="sxs-lookup"><span data-stu-id="c5c6e-123">`ExitCode` of the command</span></span>
- <span data-ttu-id="c5c6e-124">Test Runner (für Testprojekte)</span><span class="sxs-lookup"><span data-stu-id="c5c6e-124">Test runner (for test projects)</span></span>
- <span data-ttu-id="c5c6e-125">Betriebssystem und Version&#8224;</span><span class="sxs-lookup"><span data-stu-id="c5c6e-125">Operating system and version&#8224;</span></span>
- <span data-ttu-id="c5c6e-126">Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="c5c6e-126">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="c5c6e-127">Die .NET Core SDK-Version&#8224;</span><span class="sxs-lookup"><span data-stu-id="c5c6e-127">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="c5c6e-128">&#8224;Diese Metrik wird veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-128">&#8224;This metric is published.</span></span>

<span data-ttu-id="c5c6e-129">Ab dem .NET Core SDK 2.0 werden neue Datenpunkte gesammelt:</span><span class="sxs-lookup"><span data-stu-id="c5c6e-129">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="c5c6e-130">Argumente und Optionen des Befehls `dotnet`: nur bekannte Argumente und Optionen werden gesammelt (keine beliebigen Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-130">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="c5c6e-131">Ob das SDK in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-131">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="c5c6e-132">Zielframeworks.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-132">Target frameworks.</span></span>
- <span data-ttu-id="c5c6e-133">MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-133">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="c5c6e-134">Diese Metrik wird nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-134">This metric is not published.</span></span>
- <span data-ttu-id="c5c6e-135">Das derzeitige Arbeitsverzeichnis mit Hash.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-135">Hashed current working directory.</span></span>

<span data-ttu-id="c5c6e-136">Die Funktion sammelt keine Daten wie z.B. Benutzernamen oder E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-136">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="c5c6e-137">Es scannt Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene, zum Beispiel Name, Repository oder Autor.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-137">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="c5c6e-138">Die Daten werden mithilfe der Technologie [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-138">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="c5c6e-139">Wir würden gern wissen, wie die Tools verwendet werden und ob sie gut funktionieren, nicht was Sie mit den Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-139">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="c5c6e-140">Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten gesammelt werden oder wir die Daten nicht sicher oder ordnungsgemäß behandeln, [file an issue in the dotnet/cli repo issues (melden Sie ein Problem in den dotnet- oder CLI-Repository-Problemen)](https://github.com/dotnet/cli/issues) zur Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-140">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="c5c6e-141">Veröffentlichte Daten</span><span class="sxs-lookup"><span data-stu-id="c5c6e-141">Published data</span></span>

<span data-ttu-id="c5c6e-142">Veröffentlichte Daten sind vierteljährlich verfügbar und werden unter [.NET Core SDK Usage Data (.NET Core SDK Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-142">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="c5c6e-143">Die Spalten der Datendatei sind:</span><span class="sxs-lookup"><span data-stu-id="c5c6e-143">The columns of a data file are:</span></span>
- <span data-ttu-id="c5c6e-144">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c5c6e-144">Timestamp</span></span>
- <span data-ttu-id="c5c6e-145">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="c5c6e-145">Occurrences&#8224;</span></span>
- <span data-ttu-id="c5c6e-146">Befehl</span><span class="sxs-lookup"><span data-stu-id="c5c6e-146">Command</span></span>
- <span data-ttu-id="c5c6e-147">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="c5c6e-147">Geography&#8225;</span></span>
- <span data-ttu-id="c5c6e-148">OSFamily</span><span class="sxs-lookup"><span data-stu-id="c5c6e-148">OSFamily</span></span>
- <span data-ttu-id="c5c6e-149">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="c5c6e-149">RuntimeID</span></span>
- <span data-ttu-id="c5c6e-150">OSVersion</span><span class="sxs-lookup"><span data-stu-id="c5c6e-150">OSVersion</span></span>
- <span data-ttu-id="c5c6e-151">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="c5c6e-151">SDKVersion</span></span>

<span data-ttu-id="c5c6e-152">Die Spalte *Occurences* zeigt die Gesamtanzahl der Verwendung dieses Befehls für die Metriken dieser Reihe an diesem Tag an.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-152">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="c5c6e-153">Die Spalte *Geography* zeigt normalerweise den Namen eines Landes an.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-153">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="c5c6e-154">In einigen Fällen wird der Kontinent Antarktis in dieser Spalte angezeigt. Dies geschieht entweder, weil Experten .NET Core in der Antarktis verwenden oder wegen falschen Standortdaten.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-154">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="c5c6e-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5c6e-155">Example</span></span>

| <span data-ttu-id="c5c6e-156">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c5c6e-156">Timestamp</span></span>      | <span data-ttu-id="c5c6e-157">Occurrences</span><span class="sxs-lookup"><span data-stu-id="c5c6e-157">Occurrences</span></span> | <span data-ttu-id="c5c6e-158">Befehl</span><span class="sxs-lookup"><span data-stu-id="c5c6e-158">Command</span></span> | <span data-ttu-id="c5c6e-159">Geography</span><span class="sxs-lookup"><span data-stu-id="c5c6e-159">Geography</span></span> | <span data-ttu-id="c5c6e-160">OSFamily</span><span class="sxs-lookup"><span data-stu-id="c5c6e-160">OSFamily</span></span> | <span data-ttu-id="c5c6e-161">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="c5c6e-161">RuntimeID</span></span>     | <span data-ttu-id="c5c6e-162">OSVersion</span><span class="sxs-lookup"><span data-stu-id="c5c6e-162">OSVersion</span></span> | <span data-ttu-id="c5c6e-163">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="c5c6e-163">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="c5c6e-164">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="c5c6e-164">4/16/2017 0:00</span></span> | <span data-ttu-id="c5c6e-165">8</span><span class="sxs-lookup"><span data-stu-id="c5c6e-165">8</span></span>           | <span data-ttu-id="c5c6e-166">Ausführung</span><span class="sxs-lookup"><span data-stu-id="c5c6e-166">run</span></span>     | <span data-ttu-id="c5c6e-167">Uganda</span><span class="sxs-lookup"><span data-stu-id="c5c6e-167">Uganda</span></span>    | <span data-ttu-id="c5c6e-168">Darwin</span><span class="sxs-lookup"><span data-stu-id="c5c6e-168">Darwin</span></span>   | <span data-ttu-id="c5c6e-169">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="c5c6e-169">osx.10.12-x64</span></span> | <span data-ttu-id="c5c6e-170">10.12</span><span class="sxs-lookup"><span data-stu-id="c5c6e-170">10.12</span></span>     | <span data-ttu-id="c5c6e-171">1.0.1</span><span class="sxs-lookup"><span data-stu-id="c5c6e-171">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="c5c6e-172">Datasets</span><span class="sxs-lookup"><span data-stu-id="c5c6e-172">Datasets</span></span>

[<span data-ttu-id="c5c6e-173">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="c5c6e-173">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="c5c6e-174">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="c5c6e-174">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="c5c6e-175">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="c5c6e-175">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="c5c6e-176">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="c5c6e-176">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="c5c6e-177">Zusätzliche Datasets werden mithilfe des Standardformat für URLs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-177">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="c5c6e-178">Ersetzen Sie `<YEAR>` durch das Jahr und `<QUARTER>` durch das Quartal des Jahrs (verwenden Sie `1`, `2`, `3` oder `4`).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-178">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="c5c6e-179">Die Dateien befinden sich im Format einer durch Tabstopp getrennten Datei (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-179">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="c5c6e-180">Lizenz</span><span class="sxs-lookup"><span data-stu-id="c5c6e-180">License</span></span>

<span data-ttu-id="c5c6e-181">Die Microsoft-Verteilung von .NET Core ist lizenziert mit den [Lizenzbedingungen der Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-181">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="c5c6e-182">Diese Lizenz enthält den Abschnitt „DATA“ (Daten) zum Aktivieren von Telemetrie (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-182">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="c5c6e-183">[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope)).</span><span class="sxs-lookup"><span data-stu-id="c5c6e-183">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="c5c6e-184">Daten</span><span class="sxs-lookup"><span data-stu-id="c5c6e-184">DATA.</span></span> <span data-ttu-id="c5c6e-185">Die Software sammelt möglicherweise Daten zum Benutzer und zur Nutzung der Software und übermittelt diese an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-185">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="c5c6e-186">Microsoft kann diese Informationen verwenden, um seine Produkte und -Dienste zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-186">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="c5c6e-187">Weitere Informationen zur Datenerfassung und -verwendung finden Sie in der Hilfedokumentation und in den Datenschutzbestimmungen unter http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-187">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="c5c6e-188">Ihre Verwendung der Software gilt als Zustimmung zu diesen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-188">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="c5c6e-189">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="c5c6e-189">Disclosure</span></span>

<span data-ttu-id="c5c6e-190">In den .NET Core-CLI-Tools wird beim ersten Ausführen einer der Befehle (z.B. `dotnet restore`) der folgende Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-190">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="c5c6e-191">Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-191">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="c5c6e-192">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="c5c6e-192">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c5c6e-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5c6e-193">See also</span></span>

[<span data-ttu-id="c5c6e-194">What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core-SDK-Telemetrie gelernt haben)</span><span class="sxs-lookup"><span data-stu-id="c5c6e-194">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
<span data-ttu-id="c5c6e-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch) (Verweisquelle der Telemetrie (dotnet-/CLI-Repository, Version 2.0.0 Branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) </span><span class="sxs-lookup"><span data-stu-id="c5c6e-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) </span></span>  
[<span data-ttu-id="c5c6e-196">.NET Core SDK Usage Data (.NET Core SDK-Nutzungsdaten)</span><span class="sxs-lookup"><span data-stu-id="c5c6e-196">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
