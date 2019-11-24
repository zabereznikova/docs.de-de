---
title: .NET Core SDK-Telemetrie
description: Entdecken Sie die Telemetriefeatures des .NET Core SDK, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie außerdem, wie Sie diese Features deaktivieren können.
author: KathleenDollard
ms.date: 08/27/2019
ms.custom: seodec18
ms.openlocfilehash: ecb8dbed036a04726867d004dbadf6205c1fa09f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281773"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="b193e-103">.NET Core SDK-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="b193e-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="b193e-104">Das [.NET Core SDK](index.md) umfasst ein Telemetriefeature, das Daten zur Nutzung und zu Ausnahmen erfasst, wenn die .NET Core-CLI abstürzt.</span><span class="sxs-lookup"><span data-stu-id="b193e-104">The [.NET Core SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET Core CLI crashes.</span></span> <span data-ttu-id="b193e-105">Die .NET Core-CLI umfasst das .NET Core SDK und besteht aus mehreren Verben, die es Ihnen ermöglichen, Ihre .NET Core-Apps zu erstellen, zu testen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b193e-105">The .NET Core CLI comes with the .NET Core SDK and is the set of verbs that enable you to build, test, and publish your .NET Core apps.</span></span> <span data-ttu-id="b193e-106">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit diese verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="b193e-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="b193e-107">Informationen zu Fehlern helfen dem Team, Probleme und Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b193e-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="b193e-108">Die erfassten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="b193e-108">The collected data is anonymous and published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="b193e-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="b193e-109">Scope</span></span>

<span data-ttu-id="b193e-110">`dotnet` hat zwei Funktionen: das Ausführen von Apps und das Ausführen von CLI-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="b193e-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="b193e-111">Es werden *keine Telemetriedaten erfasst*, wenn `dotnet` zum Starten einer Anwendung im folgenden Format verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="b193e-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="b193e-112">Es werden *Telemetrie erfasst*, wenn einer der [.NET Core-CLI-Befehle](index.md) verwendet wird, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b193e-112">Telemetry *is collected* when using any of the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="b193e-113">Deaktivierung der Telemetriefunktion</span><span class="sxs-lookup"><span data-stu-id="b193e-113">How to opt out</span></span>

<span data-ttu-id="b193e-114">Die Telemetriefeature des .NET Core SDK ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b193e-114">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="b193e-115">Sie können das Telemetriefeature deaktivieren, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="b193e-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> 

<span data-ttu-id="b193e-116">Ebenfalls wird ein einzelner Telemetrieeintrag auch vom .NET Core SDK-Installer gesendet, wenn eine Installation erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b193e-116">A single telemetry entry is also sent by the .NET Core SDK installer when a successful installation happens.</span></span> <span data-ttu-id="b193e-117">Sie können zur Deaktivierung die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` festlegen, bevor Sie das .NET Core SDK installieren.</span><span class="sxs-lookup"><span data-stu-id="b193e-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET Core SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="b193e-118">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="b193e-118">Disclosure</span></span>

<span data-ttu-id="b193e-119">Das .NET Core SDK zeigt beim ersten Ausführen eines der [.NET Core-CLI-Befehle](index.md) (z.B. `dotnet build`) den folgenden Text an.</span><span class="sxs-lookup"><span data-stu-id="b193e-119">The .NET Core SDK displays text similar to the following when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="b193e-120">Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="b193e-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="b193e-121">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="b193e-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="data-points"></a><span data-ttu-id="b193e-122">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="b193e-122">Data points</span></span>

<span data-ttu-id="b193e-123">Das Telemetriefeature erfasst keine personenbezogenen Daten wie Benutzernamen oder E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="b193e-123">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="b193e-124">Es überprüft Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene wie den Namen, das Repository oder den Autor.</span><span class="sxs-lookup"><span data-stu-id="b193e-124">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="b193e-125">Die Daten werden mithilfe von [Azure Monitor](https://azure.microsoft.com/services/monitor/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="b193e-125">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="b193e-126">Der Schutz Ihrer Privatsphäre ist uns wichtig.</span><span class="sxs-lookup"><span data-stu-id="b193e-126">Protecting your privacy is important to us.</span></span> <span data-ttu-id="b193e-127">Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten erfasst oder die Daten nicht sicher oder ordnungsgemäß verarbeitet werden, melden Sie ein Problem mit dem [dotnet/cli](https://github.com/dotnet/cli/issues)-Repository, oder senden Sie eine E-Mail an [dotnet@microsoft.com](mailto:dotnet@microsoft.com), damit dies überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="b193e-127">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="b193e-128">Das Telemetriefeature erfasst die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="b193e-128">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="b193e-129">SDK-Versionen</span><span class="sxs-lookup"><span data-stu-id="b193e-129">SDK versions</span></span> | <span data-ttu-id="b193e-130">Daten</span><span class="sxs-lookup"><span data-stu-id="b193e-130">Data</span></span> |
|--------------|------|
| <span data-ttu-id="b193e-131">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-131">All</span></span>          | <span data-ttu-id="b193e-132">Den Zeitstempel des Aufrufs</span><span class="sxs-lookup"><span data-stu-id="b193e-132">Timestamp of invocation.</span></span> |
| <span data-ttu-id="b193e-133">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-133">All</span></span>          | <span data-ttu-id="b193e-134">Den aufgerufenen Befehl (zum Beispiel „build“), ab Version 2.1 gehasht</span><span class="sxs-lookup"><span data-stu-id="b193e-134">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="b193e-135">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-135">All</span></span>          | <span data-ttu-id="b193e-136">Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="b193e-136">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="b193e-137">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-137">All</span></span>          | <span data-ttu-id="b193e-138">Betriebssystem und Version</span><span class="sxs-lookup"><span data-stu-id="b193e-138">Operating system and version.</span></span> |
| <span data-ttu-id="b193e-139">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-139">All</span></span>          | <span data-ttu-id="b193e-140">Die Runtime-ID (RID), auf der das SDK ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b193e-140">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="b193e-141">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-141">All</span></span>          | <span data-ttu-id="b193e-142">Die Version des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="b193e-142">.NET Core SDK version.</span></span> |
| <span data-ttu-id="b193e-143">Alle</span><span class="sxs-lookup"><span data-stu-id="b193e-143">All</span></span>          | <span data-ttu-id="b193e-144">Telemetrieprofil: ein optionaler Wert, der nur bei der expliziten Benutzeranmeldung und intern bei Microsoft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b193e-144">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="b193e-145">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="b193e-145">>=2.0</span></span>        | <span data-ttu-id="b193e-146">Befehlsargumente und -optionen: Es werden mehrere Argumente und Optionen erfasst (keine beliebigen Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="b193e-146">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="b193e-147">Weitere Informationen finden Sie unter [Gesammelte Optionen](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="b193e-147">See [collected options](#collected-options).</span></span> <span data-ttu-id="b193e-148">Ab Version 2.1.300 gehasht</span><span class="sxs-lookup"><span data-stu-id="b193e-148">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="b193e-149">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="b193e-149">>=2.0</span></span>         | <span data-ttu-id="b193e-150">Ob das SDK in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b193e-150">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="b193e-151">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="b193e-151">>=2.0</span></span>         | <span data-ttu-id="b193e-152">Zielframeworks (aus dem Ereignis `TargetFramework`), ab Version 2.1 gehasht</span><span class="sxs-lookup"><span data-stu-id="b193e-152">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="b193e-153">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="b193e-153">>=2.0</span></span>         | <span data-ttu-id="b193e-154">Gehashte Media Access Control-Adresse: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer</span><span class="sxs-lookup"><span data-stu-id="b193e-154">Hashed Media Access Control (MAC) address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> |
| <span data-ttu-id="b193e-155">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="b193e-155">>=2.0</span></span>         | <span data-ttu-id="b193e-156">Das derzeitige Arbeitsverzeichnis mit Hash.</span><span class="sxs-lookup"><span data-stu-id="b193e-156">Hashed current working directory.</span></span> |
| <span data-ttu-id="b193e-157">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="b193e-157">>=2.0</span></span>         | <span data-ttu-id="b193e-158">Erfolgsbericht zur Installation mit gehashtem EXE-Dateinamen</span><span class="sxs-lookup"><span data-stu-id="b193e-158">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="b193e-159">Mindestens Version 2.1.300</span><span class="sxs-lookup"><span data-stu-id="b193e-159">>=2.1.300</span></span>     | <span data-ttu-id="b193e-160">Kernelversion</span><span class="sxs-lookup"><span data-stu-id="b193e-160">Kernel version.</span></span> |
| <span data-ttu-id="b193e-161">Mindestens Version 2.1.300</span><span class="sxs-lookup"><span data-stu-id="b193e-161">>=2.1.300</span></span>     | <span data-ttu-id="b193e-162">Libc-Version</span><span class="sxs-lookup"><span data-stu-id="b193e-162">Libc release/version.</span></span> |
| <span data-ttu-id="b193e-163">Mindestens Version 3.0.100</span><span class="sxs-lookup"><span data-stu-id="b193e-163">>=3.0.100</span></span>     | <span data-ttu-id="b193e-164">Gibt an, ob die Ausgabe umgeleitet wurde (TRUE oder FALSE)</span><span class="sxs-lookup"><span data-stu-id="b193e-164">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="b193e-165">Mindestens Version 3.0.100</span><span class="sxs-lookup"><span data-stu-id="b193e-165">>=3.0.100</span></span>     | <span data-ttu-id="b193e-166">Bei einem CLI- bzw. SDK-Absturz der Ausnahmetyp und seine Stapelüberwachung (es ist nur CLI- bzw. SDK-Code in der gesendeten Stapelüberwachung enthalten)</span><span class="sxs-lookup"><span data-stu-id="b193e-166">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="b193e-167">Weitere Informationen finden Sie unter [Gesammelte Telemetrie zu einer .NET Core-CLI- bzw. -SDK-Ausnahme](#net-core-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="b193e-167">For more information, see [.NET Core CLI/SDK crash exception telemetry collected](#net-core-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="b193e-168">Gesammelte Optionen</span><span class="sxs-lookup"><span data-stu-id="b193e-168">Collected options</span></span>

<span data-ttu-id="b193e-169">Bestimmte Befehle senden zusätzliche Daten.</span><span class="sxs-lookup"><span data-stu-id="b193e-169">Certain commands send additional data.</span></span> <span data-ttu-id="b193e-170">Eine Teilmenge der Befehle sendet das erste Argument:</span><span class="sxs-lookup"><span data-stu-id="b193e-170">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="b193e-171">Befehl</span><span class="sxs-lookup"><span data-stu-id="b193e-171">Command</span></span>               | <span data-ttu-id="b193e-172">Erste Argumentdaten gesendet</span><span class="sxs-lookup"><span data-stu-id="b193e-172">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="b193e-173">Die Hilfe für den Befehl wird abgefragt.</span><span class="sxs-lookup"><span data-stu-id="b193e-173">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="b193e-174">Der Name der Vorlage (gehasht)</span><span class="sxs-lookup"><span data-stu-id="b193e-174">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="b193e-175">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="b193e-175">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="b193e-176">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="b193e-176">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="b193e-177">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="b193e-177">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="b193e-178">Die Wörter `add`, `list` oder `remove`</span><span class="sxs-lookup"><span data-stu-id="b193e-178">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="b193e-179">Die Wörter `delete`, `locals` oder `push`</span><span class="sxs-lookup"><span data-stu-id="b193e-179">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="b193e-180">Eine Teilmenge der Befehle sendet die ausgewählten Optionen, wenn diese zusammen mit ihren Werten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b193e-180">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="b193e-181">Option</span><span class="sxs-lookup"><span data-stu-id="b193e-181">Option</span></span>                  | <span data-ttu-id="b193e-182">Befehle</span><span class="sxs-lookup"><span data-stu-id="b193e-182">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="b193e-183">Alle Befehle</span><span class="sxs-lookup"><span data-stu-id="b193e-183">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="b193e-184">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="b193e-184">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="b193e-185">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="b193e-185">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="b193e-186">`dotnet build`, `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="b193e-186">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="b193e-187">Mit Ausnahme von `--verbosity` und `--sdk-package-version` werden alle anderen Werte ab dem .NET Core SDK, Version 2.1.100 gehasht.</span><span class="sxs-lookup"><span data-stu-id="b193e-187">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="b193e-188">Gesammelte Telemetrie zu einer .NET Core-CLI- bzw. -SDK-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="b193e-188">.NET Core CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="b193e-189">Wenn die .NET Core-CLI bzw. das -SDK abstürzt, sammelt es den Namen der Ausnahme und die Stapelüberwachung des CLI- bzw. SDK-Codes.</span><span class="sxs-lookup"><span data-stu-id="b193e-189">If the .NET Core CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="b193e-190">Diese Informationen werden gesammelt, um Probleme zu bewerten und die Qualität des .NET Core SDK und der -CLI zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b193e-190">This information is collected to assess problems and improve the quality of the .NET Core SDK and CLI.</span></span> <span data-ttu-id="b193e-191">Dieser Artikel enthält Informationen zu den von uns erfassten Daten.</span><span class="sxs-lookup"><span data-stu-id="b193e-191">This article provides information about the data we collect.</span></span> <span data-ttu-id="b193e-192">Außerdem erhalten Sie Tipps dazu, wie Benutzer, die ihre eigene Version des .NET Core SDK die unbeabsichtigte Offenlegung von personenbezogenen und vertraulichen Informationen vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="b193e-192">It also provides tips on how users building their own version of the .NET Core SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="b193e-193">Gesammelte Datentypen</span><span class="sxs-lookup"><span data-stu-id="b193e-193">Types of collected data</span></span>

<span data-ttu-id="b193e-194">Die .NET Core-CLI erfasst nur Informationen zu CLI- bzw. SDK-Ausnahmen und nicht zu Ausnahmen in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b193e-194">.NET Core CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="b193e-195">Die erfassten Daten enthalten den Namen der Ausnahme und die Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="b193e-195">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="b193e-196">Diese Stapelüberwachung besteht aus CLI- bzw. SDK-Code.</span><span class="sxs-lookup"><span data-stu-id="b193e-196">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="b193e-197">Im folgenden Beispiel sehen Sie, welche Art von Daten erfasst wird:</span><span class="sxs-lookup"><span data-stu-id="b193e-197">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-information"></a><span data-ttu-id="b193e-198">Vermeiden der unbeabsichtigten Offenlegung von Informationen</span><span class="sxs-lookup"><span data-stu-id="b193e-198">Avoid inadvertent disclosure information</span></span>

<span data-ttu-id="b193e-199">.NET Core-Mitwirkende und jeder andere, der eine Version des .NET Core SDK ausführt, die Sie selbst erstellt haben, sollte den Pfad zu Ihrem SDK-Quellcode berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b193e-199">.NET Core contributors and anyone else running a version of the .NET Core SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="b193e-200">Wenn ein Absturz bei der Verwendung eines .NET Core SDK auftritt, bei dem es sich um einen benutzerdefinierten Debugbuild handelt oder der mit benutzerdefinierten Buildsymboldateien konfiguriert ist, wird der Pfad der SDK-Quelldatei auf dem Buildcomputer als Teil der Stapelüberwachung zwar erfasst, aber nicht gehasht.</span><span class="sxs-lookup"><span data-stu-id="b193e-200">If a crash occurs while using a .NET Core SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="b193e-201">Aus diesem Grund sollten benutzerdefinierte Builds des .NET Core SDK nicht in Verzeichnissen gespeichert werden, deren Pfadnamen persönliche oder vertrauliche Informationen offenlegen.</span><span class="sxs-lookup"><span data-stu-id="b193e-201">Because of this, custom builds of the .NET Core SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span> 

## <a name="see-also"></a><span data-ttu-id="b193e-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b193e-202">See also</span></span>

- [<span data-ttu-id="b193e-203">Telemetrie zur .NET Core-CLI: Daten zum 2. Quartal 2019</span><span class="sxs-lookup"><span data-stu-id="b193e-203">.NET Core CLI Telemetry - 2019 Q2 Data</span></span>](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2)
- [<span data-ttu-id="b193e-204">Telemetrieverweisquelle (dotnet- bzw. cli-Repository)</span><span class="sxs-lookup"><span data-stu-id="b193e-204">Telemetry reference source (dotnet/cli repository)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
