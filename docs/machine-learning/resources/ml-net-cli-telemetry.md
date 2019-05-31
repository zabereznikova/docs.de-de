---
title: Erfassen von Telemetriedaten durch die ML.NET-CLI
description: Erfahren Sie mehr über die die Telemetriefeatures der ML.NET-CLI, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie auch, wie Sie diese Features deaktivieren können. Außerdem finden Sie hier Links zur .NET-Lizenzvereinbarung und Informationen zur Einhaltung der DSGVO durch Microsoft.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065543"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="b7ccd-104">Erfassen von Telemetriedaten durch die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="b7ccd-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="b7ccd-105">Die [ML.NET-CLI](http://aka.ms/mlnet-cli) beinhaltet ein Telemetriefeature, das anonyme Nutzungsdaten sammelt, die für die Verwendung durch Microsoft zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-105">The [ML.NET CLI](http://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="b7ccd-106">So verwendet Microsoft die Daten</span><span class="sxs-lookup"><span data-stu-id="b7ccd-106">How Microsoft uses the data</span></span>

<span data-ttu-id="b7ccd-107">Das Produktteam verwendet die Telemetriedaten der ML.NET-CLI, um zu verstehen, wie die Tools verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="b7ccd-108">Wenn Kunden beispielsweise eine bestimmte Machine Learning-Aufgabe selten nutzen, untersucht das Produktteam, warum dies der Fall ist, und verwendet die Ergebnisse, um die Entwicklung von Features zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="b7ccd-109">Telemetriedaten der ML.NET-CLI unterstützen auch das Debugging von Problemen wie Abstürze und Codeanomalien.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span> 

<span data-ttu-id="b7ccd-110">Das Produktteam schätzt diese Erkenntnis, aber wir wissen auch, dass nicht jeder diese Daten weitergeben möchte.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="b7ccd-111">Erfahren Sie, wie Sie die Telemetriedaten deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="b7ccd-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="b7ccd-112">Scope</span></span>

<span data-ttu-id="b7ccd-113">Der Befehl `mlnet` startet die ML.NET-CLI, aber die Befehl selbst sammelt noch keine Telemetriedaten.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="b7ccd-114">Die Telemetrie wird durch die Ausführung des Befehls `mlnet` *nicht aktiviert*, wenn kein Befehl angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="b7ccd-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7ccd-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="b7ccd-116">Die Telemetrie *wird aktiviert*, wenn Sie einen [ML.NET-CLI-Befehl](../reference/ml-net-cli-reference.md) ausführen, wie `mlnet auto-train`.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="b7ccd-117">Ablehnen der Datensammlung</span><span class="sxs-lookup"><span data-stu-id="b7ccd-117">Opt out of data collection</span></span>

<span data-ttu-id="b7ccd-118">Die Telemetriefeature der ML.NET-CLI ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="b7ccd-119">Deaktivieren Sie die Telemetriefeature, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-119">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="b7ccd-120">Diese Umgebungsvariable gilt global für das .NET CLI-Tool.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-120">This environment variable applies globally to the .NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="b7ccd-121">Gesammelte Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="b7ccd-121">Data points collected</span></span>

<span data-ttu-id="b7ccd-122">Die Funktion sammelt die folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="b7ccd-122">The feature collects the following data:</span></span>

- <span data-ttu-id="b7ccd-123">Welche Befehle aufgerufen werden, z.B. `auto-train`</span><span class="sxs-lookup"><span data-stu-id="b7ccd-123">Which commands are invoked, such as `auto-train`</span></span>
- <span data-ttu-id="b7ccd-124">MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer</span><span class="sxs-lookup"><span data-stu-id="b7ccd-124">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="b7ccd-125">Zeitstempel eines Aufrufs</span><span class="sxs-lookup"><span data-stu-id="b7ccd-125">Timestamp of an invocation</span></span>
- <span data-ttu-id="b7ccd-126">Die aus drei Oktetten bestehende IP-Adresse, die nur zur Bestimmung des geografischen Standorts verwendet wird</span><span class="sxs-lookup"><span data-stu-id="b7ccd-126">Three octet IP address used only to determine geographical location</span></span>
- <span data-ttu-id="b7ccd-127">Die Namen aller verwendeter Argumente/Parameter</span><span class="sxs-lookup"><span data-stu-id="b7ccd-127">Name of all arguments/parameters used.</span></span> <span data-ttu-id="b7ccd-128">Nicht die Kundenwerte, z.B. Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b7ccd-128">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="b7ccd-129">Betriebssystem und Version</span><span class="sxs-lookup"><span data-stu-id="b7ccd-129">Operating system and version</span></span>
- <span data-ttu-id="b7ccd-130">Wert des ml-Task-Parameters: Kategoriewerte, z. B. `regression`, `binary-classification` und `multiclass-classification`</span><span class="sxs-lookup"><span data-stu-id="b7ccd-130">Value of --ml-task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="b7ccd-131">Größe der [logarithmisch gerundeten](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) Datasetdatei (nächste Potenz von 2)</span><span class="sxs-lookup"><span data-stu-id="b7ccd-131">[Logarithmic rounded](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) dataset file size (nearest power of 2)</span></span>
- <span data-ttu-id="b7ccd-132">`ExitCode` des Befehls</span><span class="sxs-lookup"><span data-stu-id="b7ccd-132">`ExitCode` of the command</span></span>

<span data-ttu-id="b7ccd-133">Die Daten werden mithilfe der Technologie [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-133">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="b7ccd-134">Nicht gesammelte Datenpunkte</span><span class="sxs-lookup"><span data-stu-id="b7ccd-134">Data points not collected</span></span>
<span data-ttu-id="b7ccd-135">Das Telemetriefeature sammelt *nicht*:</span><span class="sxs-lookup"><span data-stu-id="b7ccd-135">The telemetry feature *doesn't* collect:</span></span>
- <span data-ttu-id="b7ccd-136">persönliche Daten, z.B. Benutzernamen</span><span class="sxs-lookup"><span data-stu-id="b7ccd-136">personal data, such as usernames</span></span>
- <span data-ttu-id="b7ccd-137">Namen der Datasetdateien</span><span class="sxs-lookup"><span data-stu-id="b7ccd-137">dataset filenames</span></span>
- <span data-ttu-id="b7ccd-138">Daten aus den Datasetdateien</span><span class="sxs-lookup"><span data-stu-id="b7ccd-138">data from dataset files</span></span>

<span data-ttu-id="b7ccd-139">Wenn Sie vermuten, dass durch die ML.NET-CLI-Telemetrie vertrauliche Daten gesammelt oder die Daten nicht sicher oder ordnungsgemäß behandelt werden, melden Sie ein Problem mit dem [ML.NET](https://github.com/dotnet/machinelearning)-Repository, damit dieses untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-139">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="b7ccd-140">Lizenz</span><span class="sxs-lookup"><span data-stu-id="b7ccd-140">License</span></span>

<span data-ttu-id="b7ccd-141">Die Microsoft-Verteilung der ML.NET-CLI ist gemäß den [Microsoft-Softwarelizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula) lizenziert.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-141">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="b7ccd-142">Ausführlichere Informationen zur Datensammlung und -verarbeitung finden Sie im Abschnitt „Daten“.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-142">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="b7ccd-143">Offenlegung</span><span class="sxs-lookup"><span data-stu-id="b7ccd-143">Disclosure</span></span>

<span data-ttu-id="b7ccd-144">Wenn Sie zum ersten Mal einen [ML.NET-CLI-Befehl](../reference/ml-net-cli-reference.md) wie `mlnet auto-train` ausführen, zeigt das ML.NET-CLI-Tool einen Text an, der Ihnen erklärt, wie Sie die Telemetrie deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-144">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="b7ccd-145">Der Text kann abhängig von der von Ihnen ausgeführten Version der CLI leicht variieren.</span><span class="sxs-lookup"><span data-stu-id="b7ccd-145">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7ccd-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7ccd-146">See also</span></span>
- [<span data-ttu-id="b7ccd-147">ML.NET-CLI-Referenz</span><span class="sxs-lookup"><span data-stu-id="b7ccd-147">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="b7ccd-148">Microsoft-Software-Lizenzbedingungen: Microsoft .NET-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="b7ccd-148">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="b7ccd-149">Datenschutz bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7ccd-149">Privacy at Microsoft</span></span>](https://www.microsoft.com/en-us/trustcenter/privacy/)
- [<span data-ttu-id="b7ccd-150">Datenschutzerklärung von Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7ccd-150">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/en-us/privacystatement)
