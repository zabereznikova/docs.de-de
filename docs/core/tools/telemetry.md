---
title: .NET Core-Tools-Telemetrie
description: "Entdecken Sie die Telemetriefunktionen der .NET Core-Tools, die Informationen zur Verwendung für die Analyse erfassen."
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1816b9fbad1f671820c9f970674c8af2147a230e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-tools-telemetry"></a><span data-ttu-id="20b2a-104">.NET Core-Tools-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="20b2a-104">.NET Core Tools Telemetry</span></span>

<span data-ttu-id="20b2a-105">Die .NET Core-Tools beinhalten eine [Telemetriefunktion](https://github.com/dotnet/cli/pull/2145), die Benutzerinformationen sammelt.</span><span class="sxs-lookup"><span data-stu-id="20b2a-105">The .NET Core Tools include a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="20b2a-106">Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="20b2a-106">It’s important that the .NET Team understands how the tools are being used so that we can improve them.</span></span>

<span data-ttu-id="20b2a-107">Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von Community-Entwicklern veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="20b2a-107">The data collected is anonymous and will be published in an aggregated form for use by both Microsoft and community engineers under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="20b2a-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="20b2a-108">Scope</span></span>

<span data-ttu-id="20b2a-109">Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-Tools verwendet.</span><span class="sxs-lookup"><span data-stu-id="20b2a-109">The `dotnet` command is used to launch both apps and the .NET Core Tools.</span></span> <span data-ttu-id="20b2a-110">Der `dotnet`-Befehl selbst sammelt keine Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="20b2a-110">The `dotnet` command itself does not collect telemetry.</span></span> <span data-ttu-id="20b2a-111">Es sind die .NET Core-Tools, die über den `dotnet`-Befehl ausgeführt werden, der Telemetrie sammelt.</span><span class="sxs-lookup"><span data-stu-id="20b2a-111">It is the .NET Core Tools that are run via the `dotnet` command that collect telemetry.</span></span>

<span data-ttu-id="20b2a-112">.NET Core-Befehle (Telemetrie ist nicht aktiviert):</span><span class="sxs-lookup"><span data-stu-id="20b2a-112">.NET Core commands (telemetry is not enabled):</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="20b2a-113">.NET Core-Tools-[Befehle](index.md) (Telemetrie ist aktiviert), wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="20b2a-113">.NET Core Tools [commands](index.md) (telemetry is enabled), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="behavior"></a><span data-ttu-id="20b2a-114">Verhalten</span><span class="sxs-lookup"><span data-stu-id="20b2a-114">Behavior</span></span>

<span data-ttu-id="20b2a-115">Die Telemetriefunktion der .NET Core-Tools ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="20b2a-115">The .NET Core Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="20b2a-116">Sie können die Telemetriefunktion deaktivieren, indem Sie eine Umgebungsvariable DOTNET_CLI_TELEMETRY_OPTOUT (z.B. `export` unter Mac OS/Linux, `set` unter Windows) auf TRUE festlegen (z.B. „TRUE“, 1).</span><span class="sxs-lookup"><span data-stu-id="20b2a-116">You can opt-out of the telemetry feature by setting an environment variable DOTNET_CLI_TELEMETRY_OPTOUT (for example, `export` on macOS/Linux, `set` on Windows) to true (for example, "true", 1).</span></span>

## <a name="data-points"></a><span data-ttu-id="20b2a-117">Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="20b2a-117">Data Points</span></span>

<span data-ttu-id="20b2a-118">Die Funktion sammelt die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="20b2a-118">The feature collects the following pieces of data:</span></span>

- <span data-ttu-id="20b2a-119">Der Befehl, der verwendet wird (z.B. „build“, „restore“)</span><span class="sxs-lookup"><span data-stu-id="20b2a-119">The command being used (for example, "build", "restore")</span></span>
- <span data-ttu-id="20b2a-120">Der ExitCode des Befehls</span><span class="sxs-lookup"><span data-stu-id="20b2a-120">The ExitCode of the command</span></span>
- <span data-ttu-id="20b2a-121">Der für Testprojekte verwendete Test Runner</span><span class="sxs-lookup"><span data-stu-id="20b2a-121">For test projects, the test runner being used</span></span>
- <span data-ttu-id="20b2a-122">Der Zeitstempel des Aufrufs</span><span class="sxs-lookup"><span data-stu-id="20b2a-122">The timestamp of invocation</span></span>
- <span data-ttu-id="20b2a-123">Das verwendete Framework</span><span class="sxs-lookup"><span data-stu-id="20b2a-123">The framework used</span></span>
- <span data-ttu-id="20b2a-124">Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="20b2a-124">Whether runtime IDs are present in the "runtimes" node</span></span>
- <span data-ttu-id="20b2a-125">Die verwendete CLI-Version</span><span class="sxs-lookup"><span data-stu-id="20b2a-125">The CLI version being used</span></span>

<span data-ttu-id="20b2a-126">Die Funktion sammelt keine personenbezogenen Daten wie z.B. Benutzernamen oder E-Mails.</span><span class="sxs-lookup"><span data-stu-id="20b2a-126">The feature will not collect any personal data, such as usernames or emails.</span></span> <span data-ttu-id="20b2a-127">Sie scannt Ihren Code nicht und extrahiert auch keine Daten auf Projektebene, die als sensibel gelten können, wie z.B. Name, Repository oder Autor (wenn Sie diese in Ihrer „project.json“-Datei festlegen).</span><span class="sxs-lookup"><span data-stu-id="20b2a-127">It will not scan your code and not extract any project-level data that can be considered sensitive, such as name, repo or author (if you set those in your project.json).</span></span> <span data-ttu-id="20b2a-128">Wir würden gern wissen, wie die Tools verwendet werden, nicht was Sie mit den Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="20b2a-128">We want to know how the tools are used, not what you are building with the tools.</span></span> <span data-ttu-id="20b2a-129">Wenn Sie bemerken, dass sensible Daten gesammelt werden, handelt es sich dabei um einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="20b2a-129">If you find sensitive data being collected, that’s a bug.</span></span> <span data-ttu-id="20b2a-130">Bitte [melden Sie ein Problem](https://github.com/dotnet/cli/issues), und der Fehler wird behoben.</span><span class="sxs-lookup"><span data-stu-id="20b2a-130">Please [file an issue](https://github.com/dotnet/cli/issues) and it will be fixed.</span></span>

## <a name="license"></a><span data-ttu-id="20b2a-131">Lizenz</span><span class="sxs-lookup"><span data-stu-id="20b2a-131">License</span></span>

<span data-ttu-id="20b2a-132">Die Microsoft-Verteilung von .NET Core ist lizenziert mit den [Lizenzbedingungen der Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="20b2a-132">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="20b2a-133">Dies umfasst den Abschnitt „Data“ (Daten), der nachstehend abgebildet ist, um die Telemetrie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="20b2a-133">This includes the "DATA" section re-printed below, to enable telemetry.</span></span>

<span data-ttu-id="20b2a-134">[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope) weiter oben).</span><span class="sxs-lookup"><span data-stu-id="20b2a-134">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use this same license but do not enable telemetry (see [Scope](#scope) above).</span></span>

> 2. <span data-ttu-id="20b2a-135">Daten</span><span class="sxs-lookup"><span data-stu-id="20b2a-135">DATA.</span></span> <span data-ttu-id="20b2a-136">Die Software sammelt möglicherweise Daten zum Benutzer und zur Nutzung der Software und übermittelt diese an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20b2a-136">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="20b2a-137">Microsoft kann diese Informationen verwenden, um seine Produkte und -Dienste zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="20b2a-137">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="20b2a-138">Weitere Informationen zur Datenerfassung und -verwendung finden Sie in der Hilfedokumentation und in den Datenschutzbestimmungen unter http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="20b2a-138">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="20b2a-139">Ihre Verwendung der Software gilt als Zustimmung zu diesen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="20b2a-139">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="20b2a-140">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="20b2a-140">Disclosure</span></span>

<span data-ttu-id="20b2a-141">In den .NET Core-Tools wird beim ersten Ausführen einer der Befehle (z.B. `dotnet restore`) der folgende Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20b2a-141">The .NET Core Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="20b2a-142">Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="20b2a-142">This "first run" experience is how Microsoft notifies you about data collection.</span></span> <span data-ttu-id="20b2a-143">Bei dieser Aktion wird außerdem Ihr NuGet-Cache mit den Bibliotheken im .NET Core SDK gefüllt, und Anfragen an NuGet.org (oder ein anderes NuGet-Feed) für diese Bibliotheken werden vermieden.</span><span class="sxs-lookup"><span data-stu-id="20b2a-143">This same experience also initially populates your NuGet cache with the libraries in the .NET Core SDK, avoiding requests to NuGet.org (or other NuGet feed) for these libraries.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to improve restore speed and enable offline access. This command will take up to a minute to complete and will only happen once.
```

