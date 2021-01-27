---
title: .NET SDK-Telemetrie
description: In diesem Artikel lernen Sie die Telemetriefeatures des .NET SDK kennen, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Sie erfahren außerdem, wie Sie diese Features deaktivieren können.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 137b703dc9369f09fb535af40edf057e4e02117a
ms.sourcegitcommit: 2b878d7011306b215dbf3d5dc9c1e78355a6dcd5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "98757836"
---
# <a name="net-sdk-telemetry"></a><span data-ttu-id="4a697-103">.NET SDK-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="4a697-103">.NET SDK telemetry</span></span>

<span data-ttu-id="4a697-104">Das [.NET SDK](index.md) umfasst ein Telemetriefeature, das Daten zur Nutzung und zu Ausnahmen erfasst, wenn die .NET-CLI abstürzt.</span><span class="sxs-lookup"><span data-stu-id="4a697-104">The [.NET SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET CLI crashes.</span></span> <span data-ttu-id="4a697-105">Die .NET-CLI umfasst das .NET SDK und besteht aus mehreren Verben, die es Ihnen ermöglichen, Ihre .NET-Apps zu erstellen, zu testen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4a697-105">The .NET CLI comes with the .NET SDK and is the set of verbs that enable you to build, test, and publish your .NET apps.</span></span> <span data-ttu-id="4a697-106">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit diese verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="4a697-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="4a697-107">Informationen zu Fehlern helfen dem Team, Probleme und Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4a697-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="4a697-108">Die erfassten Daten werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4a697-108">The collected data is published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="4a697-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="4a697-109">Scope</span></span>

<span data-ttu-id="4a697-110">`dotnet` hat zwei Funktionen: das Ausführen von Apps und das Ausführen von CLI-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="4a697-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="4a697-111">Es werden *keine Telemetriedaten erfasst*, wenn `dotnet` zum Starten einer Anwendung im folgenden Format verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="4a697-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="4a697-112">Es werden *Telemetriedaten erfasst*, wenn einer der [.NET-CLI-Befehle](index.md) verwendet wird, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4a697-112">Telemetry *is collected* when using any of the [.NET CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="4a697-113">Deaktivierung der Telemetriefunktion</span><span class="sxs-lookup"><span data-stu-id="4a697-113">How to opt out</span></span>

<span data-ttu-id="4a697-114">Das Telemetriefeature des .NET SDK ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4a697-114">The .NET SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="4a697-115">Sie können das Telemetriefeature deaktivieren, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="4a697-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="4a697-116">Außerdem wird ein einzelner Telemetrieeintrag vom .NET SDK-Installationsprogramm gesendet, wenn eine Installation erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4a697-116">A single telemetry entry is also sent by the .NET SDK installer when a successful installation happens.</span></span> <span data-ttu-id="4a697-117">Sie können zur Deaktivierung die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` festlegen, bevor Sie das .NET SDK installieren.</span><span class="sxs-lookup"><span data-stu-id="4a697-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET SDK.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a697-118">Wenn Sie die Deaktivierung durchführen möchten, nachdem Sie das Installationsprogramm gestartet haben, schließen Sie das Installationsprogramm, legen Sie die Umgebungsvariable fest, und führen Sie das Installationsprogramm dann noch mal mit diesen Werten aus.</span><span class="sxs-lookup"><span data-stu-id="4a697-118">To opt out after you started the installer: close the installer, set the environment variable, and then run the installer again with that value set.</span></span>

## <a name="disclosure"></a><span data-ttu-id="4a697-119">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="4a697-119">Disclosure</span></span>

<span data-ttu-id="4a697-120">Das .NET SDK zeigt beim ersten Ausführen eines der [.NET-CLI-Befehle](index.md) (z. B. `dotnet build`) den folgenden Text an.</span><span class="sxs-lookup"><span data-stu-id="4a697-120">The .NET SDK displays text similar to the following when you first run one of the [.NET CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="4a697-121">Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="4a697-121">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="4a697-122">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="4a697-122">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="4a697-123">Legen Sie die Umgebungsvariable `DOTNET_NOLOGO` auf `true` fest, um diese Meldung und die .NET-Willkommensmeldung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a697-123">To disable this message and the .NET welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="4a697-124">Beachten Sie, dass mit dieser Variable nicht die Übertragung von Telemetriedaten deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4a697-124">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="4a697-125">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="4a697-125">Data points</span></span>

<span data-ttu-id="4a697-126">Das Telemetriefeature erfasst keine personenbezogenen Daten wie Benutzernamen oder E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="4a697-126">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="4a697-127">Es überprüft Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene wie den Namen, das Repository oder den Autor.</span><span class="sxs-lookup"><span data-stu-id="4a697-127">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="4a697-128">Die Daten werden mithilfe von [Azure Monitor](https://azure.microsoft.com/services/monitor/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4a697-128">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="4a697-129">Der Schutz Ihrer Privatsphäre ist uns wichtig.</span><span class="sxs-lookup"><span data-stu-id="4a697-129">Protecting your privacy is important to us.</span></span> <span data-ttu-id="4a697-130">Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten erfasst oder die Daten nicht sicher oder ordnungsgemäß verarbeitet werden, melden Sie ein Problem mit dem [dotnet/sdk](https://github.com/dotnet/sdk/issues)-Repository, oder senden Sie eine E-Mail an [dotnet@microsoft.com](mailto:dotnet@microsoft.com), damit dies überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="4a697-130">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/sdk](https://github.com/dotnet/sdk/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="4a697-131">Das Telemetriefeature erfasst die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="4a697-131">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="4a697-132">SDK-Versionen</span><span class="sxs-lookup"><span data-stu-id="4a697-132">SDK versions</span></span> | <span data-ttu-id="4a697-133">Daten</span><span class="sxs-lookup"><span data-stu-id="4a697-133">Data</span></span> |
|--------------|------|
| <span data-ttu-id="4a697-134">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-134">All</span></span>          | <span data-ttu-id="4a697-135">Den Zeitstempel des Aufrufs</span><span class="sxs-lookup"><span data-stu-id="4a697-135">Timestamp of invocation.</span></span> |
| <span data-ttu-id="4a697-136">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-136">All</span></span>          | <span data-ttu-id="4a697-137">Den aufgerufenen Befehl (zum Beispiel „build“), ab Version 2.1 gehasht</span><span class="sxs-lookup"><span data-stu-id="4a697-137">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="4a697-138">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-138">All</span></span>          | <span data-ttu-id="4a697-139">Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="4a697-139">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="4a697-140">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-140">All</span></span>          | <span data-ttu-id="4a697-141">Betriebssystem und Version</span><span class="sxs-lookup"><span data-stu-id="4a697-141">Operating system and version.</span></span> |
| <span data-ttu-id="4a697-142">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-142">All</span></span>          | <span data-ttu-id="4a697-143">Die Runtime-ID (RID), auf der das SDK ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="4a697-143">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="4a697-144">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-144">All</span></span>          | <span data-ttu-id="4a697-145">Version des .NET SDK</span><span class="sxs-lookup"><span data-stu-id="4a697-145">.NET SDK version.</span></span> |
| <span data-ttu-id="4a697-146">Alle</span><span class="sxs-lookup"><span data-stu-id="4a697-146">All</span></span>          | <span data-ttu-id="4a697-147">Telemetrieprofil: ein optionaler Wert, der nur bei der expliziten Benutzeranmeldung und intern bei Microsoft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4a697-147">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="4a697-148">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4a697-148">>=2.0</span></span>        | <span data-ttu-id="4a697-149">Befehlsargumente und -optionen: Es werden mehrere Argumente und Optionen erfasst (keine beliebigen Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="4a697-149">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="4a697-150">Weitere Informationen finden Sie unter [Gesammelte Optionen](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="4a697-150">See [collected options](#collected-options).</span></span> <span data-ttu-id="4a697-151">Ab Version 2.1.300 gehasht</span><span class="sxs-lookup"><span data-stu-id="4a697-151">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="4a697-152">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4a697-152">>=2.0</span></span>         | <span data-ttu-id="4a697-153">Ob das SDK in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4a697-153">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="4a697-154">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4a697-154">>=2.0</span></span>         | <span data-ttu-id="4a697-155">Zielframeworks (aus dem Ereignis `TargetFramework`), ab Version 2.1 gehasht</span><span class="sxs-lookup"><span data-stu-id="4a697-155">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="4a697-156">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4a697-156">>=2.0</span></span>         | <span data-ttu-id="4a697-157">MAC-Adresse (Media Access Control) mit Hashwert (SHA256).</span><span class="sxs-lookup"><span data-stu-id="4a697-157">Hashed Media Access Control (MAC) address (SHA256).</span></span> |
| <span data-ttu-id="4a697-158">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4a697-158">>=2.0</span></span>         | <span data-ttu-id="4a697-159">Das derzeitige Arbeitsverzeichnis mit Hash.</span><span class="sxs-lookup"><span data-stu-id="4a697-159">Hashed current working directory.</span></span> |
| <span data-ttu-id="4a697-160">Mindestens Version 2.0</span><span class="sxs-lookup"><span data-stu-id="4a697-160">>=2.0</span></span>         | <span data-ttu-id="4a697-161">Erfolgsbericht zur Installation mit gehashtem EXE-Dateinamen</span><span class="sxs-lookup"><span data-stu-id="4a697-161">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="4a697-162">Mindestens Version 2.1.300</span><span class="sxs-lookup"><span data-stu-id="4a697-162">>=2.1.300</span></span>     | <span data-ttu-id="4a697-163">Kernelversion</span><span class="sxs-lookup"><span data-stu-id="4a697-163">Kernel version.</span></span> |
| <span data-ttu-id="4a697-164">Mindestens Version 2.1.300</span><span class="sxs-lookup"><span data-stu-id="4a697-164">>=2.1.300</span></span>     | <span data-ttu-id="4a697-165">Libc-Version</span><span class="sxs-lookup"><span data-stu-id="4a697-165">Libc release/version.</span></span> |
| <span data-ttu-id="4a697-166">Mindestens Version 3.0.100</span><span class="sxs-lookup"><span data-stu-id="4a697-166">>=3.0.100</span></span>     | <span data-ttu-id="4a697-167">Gibt an, ob die Ausgabe umgeleitet wurde (TRUE oder FALSE)</span><span class="sxs-lookup"><span data-stu-id="4a697-167">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="4a697-168">Mindestens Version 3.0.100</span><span class="sxs-lookup"><span data-stu-id="4a697-168">>=3.0.100</span></span>     | <span data-ttu-id="4a697-169">Bei einem CLI- bzw. SDK-Absturz der Ausnahmetyp und seine Stapelüberwachung (es ist nur CLI- bzw. SDK-Code in der gesendeten Stapelüberwachung enthalten)</span><span class="sxs-lookup"><span data-stu-id="4a697-169">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="4a697-170">Weitere Informationen finden Sie unter [Gesammelte Telemetrie zu einer .NET-CLI- bzw. SDK-Ausnahme](#net-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="4a697-170">For more information, see [.NET CLI/SDK crash exception telemetry collected](#net-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="4a697-171">Gesammelte Optionen</span><span class="sxs-lookup"><span data-stu-id="4a697-171">Collected options</span></span>

<span data-ttu-id="4a697-172">Bestimmte Befehle senden zusätzliche Daten.</span><span class="sxs-lookup"><span data-stu-id="4a697-172">Certain commands send additional data.</span></span> <span data-ttu-id="4a697-173">Eine Teilmenge der Befehle sendet das erste Argument:</span><span class="sxs-lookup"><span data-stu-id="4a697-173">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="4a697-174">Befehl</span><span class="sxs-lookup"><span data-stu-id="4a697-174">Command</span></span>               | <span data-ttu-id="4a697-175">Erste Argumentdaten gesendet</span><span class="sxs-lookup"><span data-stu-id="4a697-175">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="4a697-176">Die Hilfe für den Befehl wird abgefragt.</span><span class="sxs-lookup"><span data-stu-id="4a697-176">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="4a697-177">Der Name der Vorlage (gehasht)</span><span class="sxs-lookup"><span data-stu-id="4a697-177">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="4a697-178">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="4a697-178">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="4a697-179">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="4a697-179">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="4a697-180">Die Wörter `package` oder `reference`</span><span class="sxs-lookup"><span data-stu-id="4a697-180">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="4a697-181">Die Wörter `add`, `list` oder `remove`</span><span class="sxs-lookup"><span data-stu-id="4a697-181">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="4a697-182">Die Wörter `delete`, `locals` oder `push`</span><span class="sxs-lookup"><span data-stu-id="4a697-182">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="4a697-183">Eine Teilmenge der Befehle sendet die ausgewählten Optionen, wenn diese zusammen mit ihren Werten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4a697-183">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="4a697-184">Option</span><span class="sxs-lookup"><span data-stu-id="4a697-184">Option</span></span>                  | <span data-ttu-id="4a697-185">Befehle</span><span class="sxs-lookup"><span data-stu-id="4a697-185">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="4a697-186">Alle Befehle</span><span class="sxs-lookup"><span data-stu-id="4a697-186">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="4a697-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="4a697-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="4a697-188">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="4a697-188">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="4a697-189">`dotnet build`,  `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="4a697-189">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="4a697-190">Mit Ausnahme von `--verbosity` und `--sdk-package-version` werden alle anderen Werte ab dem .NET Core SDK, Version 2.1.100 gehasht.</span><span class="sxs-lookup"><span data-stu-id="4a697-190">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="4a697-191">Gesammelte Telemetrie zu einer .NET-CLI- bzw. SDK-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="4a697-191">.NET CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="4a697-192">Wenn die .NET-CLI bzw. das SDK abstürzt, sammelt es den Namen der Ausnahme und die Stapelüberwachung des CLI- bzw. SDK-Codes.</span><span class="sxs-lookup"><span data-stu-id="4a697-192">If the .NET CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="4a697-193">Diese Informationen werden gesammelt, um Probleme zu bewerten und die Qualität des .NET SDK und der .NET-CLI zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4a697-193">This information is collected to assess problems and improve the quality of the .NET SDK and CLI.</span></span> <span data-ttu-id="4a697-194">Dieser Artikel enthält Informationen zu den von uns erfassten Daten.</span><span class="sxs-lookup"><span data-stu-id="4a697-194">This article provides information about the data we collect.</span></span> <span data-ttu-id="4a697-195">Außerdem erhalten Sie Tipps dazu, wie Benutzer, die ihre eigene Version des .NET SDK erstellen, die unbeabsichtigte Offenlegung von personenbezogenen und vertraulichen Informationen vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="4a697-195">It also provides tips on how users building their own version of the .NET SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="4a697-196">Gesammelte Datentypen</span><span class="sxs-lookup"><span data-stu-id="4a697-196">Types of collected data</span></span>

<span data-ttu-id="4a697-197">Die .NET-CLI erfasst nur Informationen zu CLI- bzw. SDK-Ausnahmen und nicht zu Ausnahmen in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4a697-197">.NET CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="4a697-198">Die erfassten Daten enthalten den Namen der Ausnahme und die Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="4a697-198">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="4a697-199">Diese Stapelüberwachung besteht aus CLI- bzw. SDK-Code.</span><span class="sxs-lookup"><span data-stu-id="4a697-199">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="4a697-200">Im folgenden Beispiel sehen Sie, welche Art von Daten erfasst wird:</span><span class="sxs-lookup"><span data-stu-id="4a697-200">The following example shows the kind of data that is collected:</span></span>

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

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="4a697-201">Vermeiden der unbeabsichtigten Offenlegung von Informationen</span><span class="sxs-lookup"><span data-stu-id="4a697-201">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="4a697-202">.NET-Mitwirkende und jeder andere, der eine Version des .NET SDK ausführt, die selbst erstellt wurde, sollte den Pfad zum SDK-Quellcode berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="4a697-202">.NET contributors and anyone else running a version of the .NET SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="4a697-203">Wenn ein Absturz bei der Verwendung eines .NET SDK auftritt, bei dem es sich um einen benutzerdefinierten Debugbuild handelt oder der mit benutzerdefinierten Buildsymboldateien konfiguriert ist, wird der Pfad der SDK-Quelldatei auf dem Buildcomputer als Teil der Stapelüberwachung zwar erfasst, aber nicht gehasht.</span><span class="sxs-lookup"><span data-stu-id="4a697-203">If a crash occurs while using a .NET SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="4a697-204">Aus diesem Grund sollten benutzerdefinierte Builds des .NET SDK nicht in Verzeichnissen gespeichert werden, deren Pfadnamen persönliche oder vertrauliche Informationen offenlegen.</span><span class="sxs-lookup"><span data-stu-id="4a697-204">Because of this, custom builds of the .NET SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a697-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a697-205">See also</span></span>

- [<span data-ttu-id="4a697-206">.NET-CLI-Telemetriedaten</span><span class="sxs-lookup"><span data-stu-id="4a697-206">.NET CLI Telemetry Data</span></span>](https://dotnet.microsoft.com/platform/telemetry)
- [<span data-ttu-id="4a697-207">Telemetrieverweisquelle (dotnet/sdk-Repository)</span><span class="sxs-lookup"><span data-stu-id="4a697-207">Telemetry reference source (dotnet/sdk repository)</span></span>](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
