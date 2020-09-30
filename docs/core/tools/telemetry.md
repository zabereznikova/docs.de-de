---
title: .NET Core SDK-Telemetrie
description: Entdecken Sie die Telemetriefeatures des .NET Core SDK, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie außerdem, wie Sie diese Features deaktivieren können.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: bad6de138b9c35bcd8c5556df82103f959508b52
ms.sourcegitcommit: d04388f94dbcd756ffd608536c869aee3242cdb0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91206353"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="4e762-103">.NET Core SDK-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="4e762-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="4e762-104">Das [.NET Core SDK](index.md) umfasst ein Telemetriefeature, das Daten zur Nutzung und zu Ausnahmen erfasst, wenn die .NET Core-CLI abstürzt.</span><span class="sxs-lookup"><span data-stu-id="4e762-104">The [.NET Core SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET Core CLI crashes.</span></span> <span data-ttu-id="4e762-105">Die .NET Core-CLI umfasst das .NET Core SDK und besteht aus mehreren Verben, die es Ihnen ermöglichen, Ihre .NET Core-Apps zu erstellen, zu testen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4e762-105">The .NET Core CLI comes with the .NET Core SDK and is the set of verbs that enable you to build, test, and publish your .NET Core apps.</span></span> <span data-ttu-id="4e762-106">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit diese verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="4e762-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="4e762-107">Informationen zu Fehlern helfen dem Team, Probleme und Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4e762-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="4e762-108">Die erfassten Daten werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4e762-108">The collected data is published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="4e762-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="4e762-109">Scope</span></span>

<span data-ttu-id="4e762-110">`dotnet` hat zwei Funktionen: das Ausführen von Apps und das Ausführen von CLI-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="4e762-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="4e762-111">Es werden *keine Telemetriedaten erfasst*, wenn `dotnet` zum Starten einer Anwendung im folgenden Format verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="4e762-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="4e762-112">Es werden *Telemetrie erfasst*, wenn einer der [.NET Core-CLI-Befehle](index.md) verwendet wird, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e762-112">Telemetry *is collected* when using any of the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="4e762-113">Deaktivierung der Telemetriefunktion</span><span class="sxs-lookup"><span data-stu-id="4e762-113">How to opt out</span></span>

<span data-ttu-id="4e762-114">Die Telemetriefeature des .NET Core SDK ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4e762-114">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="4e762-115">Sie können das Telemetriefeature deaktivieren, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="4e762-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="4e762-116">Ebenfalls wird ein einzelner Telemetrieeintrag auch vom .NET Core SDK-Installer gesendet, wenn eine Installation erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4e762-116">A single telemetry entry is also sent by the .NET Core SDK installer when a successful installation happens.</span></span> <span data-ttu-id="4e762-117">Sie können zur Deaktivierung die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` festlegen, bevor Sie das .NET Core SDK installieren.</span><span class="sxs-lookup"><span data-stu-id="4e762-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET Core SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="4e762-118">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="4e762-118">Disclosure</span></span>

<span data-ttu-id="4e762-119">Das .NET Core SDK zeigt beim ersten Ausführen eines der [.NET Core-CLI-Befehle](index.md) (z.B. `dotnet build`) den folgenden Text an.</span><span class="sxs-lookup"><span data-stu-id="4e762-119">The .NET Core SDK displays text similar to the following when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="4e762-120">Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="4e762-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="4e762-121">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="4e762-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="4e762-122">Um diese Meldung und die .NET Core-Willkommensmeldung zu deaktivieren, legen Sie die Umgebungsvariable `DOTNET_NOLOGO` auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="4e762-122">To disable this message and the .NET Core welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="4e762-123">Beachten Sie, dass mit dieser Variable nicht die Übertragung von Telemetriedaten deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4e762-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="4e762-124">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="4e762-124">Data points</span></span>

<span data-ttu-id="4e762-125">Das Telemetriefeature erfasst keine personenbezogenen Daten wie Benutzernamen oder E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="4e762-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="4e762-126">Es überprüft Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene wie den Namen, das Repository oder den Autor.</span><span class="sxs-lookup"><span data-stu-id="4e762-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="4e762-127">Die Daten werden mithilfe von [Azure Monitor](https://azure.microsoft.com/services/monitor/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4e762-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="4e762-128">Der Schutz Ihrer Privatsphäre ist uns wichtig.</span><span class="sxs-lookup"><span data-stu-id="4e762-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="4e762-129">Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten erfasst oder die Daten nicht sicher oder ordnungsgemäß verarbeitet werden, melden Sie ein Problem mit dem [dotnet/sdk](https://github.com/dotnet/sdk/issues)-Repository, oder senden Sie eine E-Mail an [dotnet@microsoft.com](mailto:dotnet@microsoft.com), damit dies überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="4e762-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/sdk](https://github.com/dotnet/sdk/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="4e762-130">Das Telemetriefeature erfasst die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="4e762-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="4e762-131">SDK-Versionen</span><span class="sxs-lookup"><span data-stu-id="4e762-131">SDK versions</span></span> | <span data-ttu-id="4e762-132">Daten</span><span class="sxs-lookup"><span data-stu-id="4e762-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="4e762-133">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-133">All</span></span>          | <span data-ttu-id="4e762-134">Den Zeitstempel des Aufrufs</span><span class="sxs-lookup"><span data-stu-id="4e762-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="4e762-135">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-135">All</span></span>          | <span data-ttu-id="4e762-136">Den aufgerufenen Befehl (zum Beispiel „build“), ab Version 2.1 gehasht</span><span class="sxs-lookup"><span data-stu-id="4e762-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="4e762-137">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-137">All</span></span>          | <span data-ttu-id="4e762-138">Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="4e762-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="4e762-139">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-139">All</span></span>          | <span data-ttu-id="4e762-140">Betriebssystem und Version</span><span class="sxs-lookup"><span data-stu-id="4e762-140">Operating system and version.</span></span> |
| <span data-ttu-id="4e762-141">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-141">All</span></span>          | <span data-ttu-id="4e762-142">Die Runtime-ID (RID), auf der das SDK ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="4e762-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="4e762-143">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-143">All</span></span>          | <span data-ttu-id="4e762-144">Die Version des .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="4e762-144">.NET Core SDK version.</span></span> |
| <span data-ttu-id="4e762-145">Alle</span><span class="sxs-lookup"><span data-stu-id="4e762-145">All</span></span>          | <span data-ttu-id="4e762-146">Telemetrieprofil: ein optionaler Wert, der nur bei der expliziten Benutzeranmeldung und intern bei Microsoft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e762-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="4e762-147">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4e762-147">>=2.0</span></span>        | <span data-ttu-id="4e762-148">Befehlsargumente und -optionen: Es werden mehrere Argumente und Optionen erfasst (keine beliebigen Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="4e762-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="4e762-149">Weitere Informationen finden Sie unter [Gesammelte Optionen](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="4e762-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="4e762-150">Ab Version 2.1.300 gehasht</span><span class="sxs-lookup"><span data-stu-id="4e762-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="4e762-151">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4e762-151">>=2.0</span></span>         | <span data-ttu-id="4e762-152">Ob das SDK in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e762-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="4e762-153">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4e762-153">>=2.0</span></span>         | <span data-ttu-id="4e762-154">Zielframeworks (aus dem Ereignis `TargetFramework`), ab Version 2.1 gehasht</span><span class="sxs-lookup"><span data-stu-id="4e762-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="4e762-155">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4e762-155">>=2.0</span></span>         | <span data-ttu-id="4e762-156">MAC-Adresse (Media Access Control) mit Hashwert (SHA256).</span><span class="sxs-lookup"><span data-stu-id="4e762-156">Hashed Media Access Control (MAC) address (SHA256).</span></span> |
| <span data-ttu-id="4e762-157">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4e762-157">>=2.0</span></span>         | <span data-ttu-id="4e762-158">Das derzeitige Arbeitsverzeichnis mit Hash.</span><span class="sxs-lookup"><span data-stu-id="4e762-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="4e762-159">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4e762-159">>=2.0</span></span>         | <span data-ttu-id="4e762-160">Erfolgsbericht zur Installation mit gehashtem EXE-Dateinamen</span><span class="sxs-lookup"><span data-stu-id="4e762-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="4e762-161">Mindestens Version 2.1.300</span><span class="sxs-lookup"><span data-stu-id="4e762-161">>=2.1.300</span></span>     | <span data-ttu-id="4e762-162">Kernelversion</span><span class="sxs-lookup"><span data-stu-id="4e762-162">Kernel version.</span></span> |
| <span data-ttu-id="4e762-163">Mindestens Version 2.1.300</span><span class="sxs-lookup"><span data-stu-id="4e762-163">>=2.1.300</span></span>     | <span data-ttu-id="4e762-164">Libc-Version</span><span class="sxs-lookup"><span data-stu-id="4e762-164">Libc release/version.</span></span> |
| <span data-ttu-id="4e762-165">Mindestens Version 3.0.100</span><span class="sxs-lookup"><span data-stu-id="4e762-165">>=3.0.100</span></span>     | <span data-ttu-id="4e762-166">Gibt an, ob die Ausgabe umgeleitet wurde (TRUE oder FALSE)</span><span class="sxs-lookup"><span data-stu-id="4e762-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="4e762-167">Mindestens Version 3.0.100</span><span class="sxs-lookup"><span data-stu-id="4e762-167">>=3.0.100</span></span>     | <span data-ttu-id="4e762-168">Bei einem CLI- bzw. SDK-Absturz der Ausnahmetyp und seine Stapelüberwachung (es ist nur CLI- bzw. SDK-Code in der gesendeten Stapelüberwachung enthalten)</span><span class="sxs-lookup"><span data-stu-id="4e762-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="4e762-169">Weitere Informationen finden Sie unter [Gesammelte Telemetrie zu einer .NET Core-CLI- bzw. -SDK-Ausnahme](#net-core-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="4e762-169">For more information, see [.NET Core CLI/SDK crash exception telemetry collected](#net-core-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="4e762-170">Gesammelte Optionen</span><span class="sxs-lookup"><span data-stu-id="4e762-170">Collected options</span></span>

<span data-ttu-id="4e762-171">Bestimmte Befehle senden zusätzliche Daten.</span><span class="sxs-lookup"><span data-stu-id="4e762-171">Certain commands send additional data.</span></span> <span data-ttu-id="4e762-172">Eine Teilmenge der Befehle sendet das erste Argument:</span><span class="sxs-lookup"><span data-stu-id="4e762-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="4e762-173">Befehl</span><span class="sxs-lookup"><span data-stu-id="4e762-173">Command</span></span>               | <span data-ttu-id="4e762-174">Erste Argumentdaten gesendet</span><span class="sxs-lookup"><span data-stu-id="4e762-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="4e762-175">Die Hilfe für den Befehl wird abgefragt.</span><span class="sxs-lookup"><span data-stu-id="4e762-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="4e762-176">Der Name der Vorlage (gehasht)</span><span class="sxs-lookup"><span data-stu-id="4e762-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="4e762-177">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="4e762-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="4e762-178">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="4e762-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="4e762-179">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="4e762-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="4e762-180">Die Wörter `add`, `list` oder `remove`</span><span class="sxs-lookup"><span data-stu-id="4e762-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="4e762-181">Die Wörter `delete`, `locals` oder `push`</span><span class="sxs-lookup"><span data-stu-id="4e762-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="4e762-182">Eine Teilmenge der Befehle sendet die ausgewählten Optionen, wenn diese zusammen mit ihren Werten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4e762-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="4e762-183">Option</span><span class="sxs-lookup"><span data-stu-id="4e762-183">Option</span></span>                  | <span data-ttu-id="4e762-184">Befehle</span><span class="sxs-lookup"><span data-stu-id="4e762-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="4e762-185">Alle Befehle</span><span class="sxs-lookup"><span data-stu-id="4e762-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="4e762-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="4e762-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="4e762-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="4e762-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="4e762-188">`dotnet build`, `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="4e762-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="4e762-189">Mit Ausnahme von `--verbosity` und `--sdk-package-version` werden alle anderen Werte ab dem .NET Core SDK, Version 2.1.100 gehasht.</span><span class="sxs-lookup"><span data-stu-id="4e762-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="4e762-190">Gesammelte Telemetrie zu einer .NET Core-CLI- bzw. -SDK-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="4e762-190">.NET Core CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="4e762-191">Wenn die .NET Core-CLI bzw. das -SDK abstürzt, sammelt es den Namen der Ausnahme und die Stapelüberwachung des CLI- bzw. SDK-Codes.</span><span class="sxs-lookup"><span data-stu-id="4e762-191">If the .NET Core CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="4e762-192">Diese Informationen werden gesammelt, um Probleme zu bewerten und die Qualität des .NET Core SDK und der -CLI zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4e762-192">This information is collected to assess problems and improve the quality of the .NET Core SDK and CLI.</span></span> <span data-ttu-id="4e762-193">Dieser Artikel enthält Informationen zu den von uns erfassten Daten.</span><span class="sxs-lookup"><span data-stu-id="4e762-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="4e762-194">Außerdem erhalten Sie Tipps dazu, wie Benutzer, die ihre eigene Version des .NET Core SDK die unbeabsichtigte Offenlegung von personenbezogenen und vertraulichen Informationen vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="4e762-194">It also provides tips on how users building their own version of the .NET Core SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="4e762-195">Gesammelte Datentypen</span><span class="sxs-lookup"><span data-stu-id="4e762-195">Types of collected data</span></span>

<span data-ttu-id="4e762-196">Die .NET Core-CLI erfasst nur Informationen zu CLI- bzw. SDK-Ausnahmen und nicht zu Ausnahmen in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4e762-196">.NET Core CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="4e762-197">Die erfassten Daten enthalten den Namen der Ausnahme und die Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="4e762-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="4e762-198">Diese Stapelüberwachung besteht aus CLI- bzw. SDK-Code.</span><span class="sxs-lookup"><span data-stu-id="4e762-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="4e762-199">Im folgenden Beispiel sehen Sie, welche Art von Daten erfasst wird:</span><span class="sxs-lookup"><span data-stu-id="4e762-199">The following example shows the kind of data that is collected:</span></span>

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

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="4e762-200">Vermeiden der unbeabsichtigten Offenlegung von Informationen</span><span class="sxs-lookup"><span data-stu-id="4e762-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="4e762-201">.NET Core-Mitwirkende und jeder andere, der eine Version des .NET Core SDK ausführt, die Sie selbst erstellt haben, sollte den Pfad zu Ihrem SDK-Quellcode berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="4e762-201">.NET Core contributors and anyone else running a version of the .NET Core SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="4e762-202">Wenn ein Absturz bei der Verwendung eines .NET Core SDK auftritt, bei dem es sich um einen benutzerdefinierten Debugbuild handelt oder der mit benutzerdefinierten Buildsymboldateien konfiguriert ist, wird der Pfad der SDK-Quelldatei auf dem Buildcomputer als Teil der Stapelüberwachung zwar erfasst, aber nicht gehasht.</span><span class="sxs-lookup"><span data-stu-id="4e762-202">If a crash occurs while using a .NET Core SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="4e762-203">Aus diesem Grund sollten benutzerdefinierte Builds des .NET Core SDK nicht in Verzeichnissen gespeichert werden, deren Pfadnamen persönliche oder vertrauliche Informationen offenlegen.</span><span class="sxs-lookup"><span data-stu-id="4e762-203">Because of this, custom builds of the .NET Core SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e762-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e762-204">See also</span></span>

- [<span data-ttu-id="4e762-205">Telemetriedaten der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="4e762-205">.NET Core CLI Telemetry Data</span></span>](https://dotnet.microsoft.com/platform/telemetry)
- [<span data-ttu-id="4e762-206">Telemetrieverweisquelle (dotnet/sdk-Repository)</span><span class="sxs-lookup"><span data-stu-id="4e762-206">Telemetry reference source (dotnet/sdk repository)</span></span>](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
