---
title: 'Azure Functions: Serverlose Apps'
description: Azure Functions bietet serverlose Funktionen für mehrere Sprachen (C#, JavaScript, Java) und Plattformen, um ereignisgesteuerten Code für die sofortige Skalierung bereitzustellen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 7625b2a0dafb90dc1bf2fb7fe680d53b20764c09
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171805"
---
# <a name="azure-functions"></a><span data-ttu-id="243a3-103">Überprüfung auf</span><span class="sxs-lookup"><span data-stu-id="243a3-103">Azure Functions</span></span>

<span data-ttu-id="243a3-104">Azure Functions bietet eine serverlose Computeerfahrung.</span><span class="sxs-lookup"><span data-stu-id="243a3-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="243a3-105">Eine Funktion wird durch einen *Trigger* aufgerufen (z.B. den Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Codeblock oder Geschäftslogik aus.</span><span class="sxs-lookup"><span data-stu-id="243a3-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="243a3-106">Funktionen unterstützen auch spezialisierte *Bindungen*, die eine Verbindung mit Ressourcen wie Speicher und Warteschlangen herstellen.</span><span class="sxs-lookup"><span data-stu-id="243a3-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions-Logo](./media/azure-functions-logo.png)

<span data-ttu-id="243a3-108">Die aktuelle Laufzeitversion 3.0 unterstützt plattformübergreifende .NET Core 3.1-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="243a3-108">The current runtime version 3.0 supports cross-platform .NET Core 3.1 applications.</span></span> <span data-ttu-id="243a3-109">Neben C# werden weitere Sprachen wie JavaScript, F# und Java unterstützt.</span><span class="sxs-lookup"><span data-stu-id="243a3-109">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="243a3-110">Funktionen, die im Portal erstellt werden, bieten eine umfangreiche Skriptsyntax.</span><span class="sxs-lookup"><span data-stu-id="243a3-110">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="243a3-111">Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Plattformunterstützung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="243a3-111">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="243a3-112">Weitere Informationen finden Sie in der [Azure Functions-Dokumentation](/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="243a3-112">For more information, see [Azure Functions documentation](/azure/azure-functions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="243a3-113">Unterstützung für Programmiersprachen</span><span class="sxs-lookup"><span data-stu-id="243a3-113">Programming language support</span></span>

<span data-ttu-id="243a3-114">Die folgenden Sprachen werden alle in der allgemeinen Verfügbarkeit (General Availability, GA) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="243a3-114">The following languages are all supported in general availability (GA).</span></span>

|<span data-ttu-id="243a3-115">Sprache</span><span class="sxs-lookup"><span data-stu-id="243a3-115">Language</span></span>      |<span data-ttu-id="243a3-116">Unterstützte Runtimes</span><span class="sxs-lookup"><span data-stu-id="243a3-116">Supported runtimes</span></span>|
|--------------|------------------|
|<span data-ttu-id="243a3-117">**C#**</span><span class="sxs-lookup"><span data-stu-id="243a3-117">**C#**</span></span>        |<span data-ttu-id="243a3-118">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="243a3-118">.NET Core 3.1</span></span>     |
|<span data-ttu-id="243a3-119">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="243a3-119">**JavaScript**</span></span>|<span data-ttu-id="243a3-120">Node 10 & 12</span><span class="sxs-lookup"><span data-stu-id="243a3-120">Node 10 & 12</span></span>      |
|<span data-ttu-id="243a3-121">**F#**</span><span class="sxs-lookup"><span data-stu-id="243a3-121">**F#**</span></span>        |<span data-ttu-id="243a3-122">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="243a3-122">.NET Core 3.1</span></span>     |
|<span data-ttu-id="243a3-123">**Java**</span><span class="sxs-lookup"><span data-stu-id="243a3-123">**Java**</span></span>      |<span data-ttu-id="243a3-124">Java 8</span><span class="sxs-lookup"><span data-stu-id="243a3-124">Java 8</span></span>            |
|<span data-ttu-id="243a3-125">**Python**</span><span class="sxs-lookup"><span data-stu-id="243a3-125">**Python**</span></span>    |<span data-ttu-id="243a3-126">Python 3.6, 3.7, & 3.8</span><span class="sxs-lookup"><span data-stu-id="243a3-126">Python 3.6, 3.7, & 3.8</span></span>|
|<span data-ttu-id="243a3-127">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="243a3-127">**TypeScript**</span></span>|<span data-ttu-id="243a3-128">Node 10 & 12 (über JavaScript)</span><span class="sxs-lookup"><span data-stu-id="243a3-128">Node 10 & 12 (via JavaScript)</span></span>|
|<span data-ttu-id="243a3-129">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="243a3-129">**PowerShell**</span></span>|<span data-ttu-id="243a3-130">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="243a3-130">PowerShell Core 6</span></span>|

<span data-ttu-id="243a3-131">Weitere Informationen finden Sie unter [Unterstützte Sprachen](/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="243a3-131">For more information, see [Supported languages](/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="243a3-132">App Service-Pläne</span><span class="sxs-lookup"><span data-stu-id="243a3-132">App service plans</span></span>

<span data-ttu-id="243a3-133">Funktionen werden durch einen *App Service-Plan* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="243a3-133">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="243a3-134">Der Plan definiert die Ressourcen, die von der Funktions-App verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="243a3-134">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="243a3-135">Sie können einer Region Pläne zuweisen, die Größe und Anzahl der zu verwendenden virtuellen Computer bestimmen und einen Tarif auswählen.</span><span class="sxs-lookup"><span data-stu-id="243a3-135">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="243a3-136">Für einen echten serverlosen Ansatz können Funktions-Apps den **Verbrauchstarif** verwenden.</span><span class="sxs-lookup"><span data-stu-id="243a3-136">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="243a3-137">Der Verbrauchstarif skaliert das Back-End automatisch basierend auf der Auslastung.</span><span class="sxs-lookup"><span data-stu-id="243a3-137">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="243a3-138">Eine weitere Hostingoption für Funktions-Apps ist der [Premium-Plan](/azure/azure-functions/functions-premium-plan).</span><span class="sxs-lookup"><span data-stu-id="243a3-138">Another hosting option for function apps is the [Premium plan](/azure/azure-functions/functions-premium-plan).</span></span> <span data-ttu-id="243a3-139">Dieser Plan bietet eine „Always On“-Instanz zur Vermeidung von Kaltstarts, unterstützt erweiterte Features wie VNet-Konnektivität und wird auf Premiumhardware ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="243a3-139">This plan provides an "always on" instance to avoid cold start, supports advanced features like VNet connectivity, and runs on premium hardware.</span></span>

<span data-ttu-id="243a3-140">Weitere Informationen finden Sie unter [App Service-Pläne](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="243a3-140">For more information, see [App service plans](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="243a3-141">Erstellen Ihrer ersten Funktion</span><span class="sxs-lookup"><span data-stu-id="243a3-141">Create your first function</span></span>

<span data-ttu-id="243a3-142">Es gibt drei gängige Methoden, um Funktions-Apps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="243a3-142">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="243a3-143">Skriptfunktionen im Portal.</span><span class="sxs-lookup"><span data-stu-id="243a3-143">Script functions in the portal.</span></span>
- <span data-ttu-id="243a3-144">Erstellen der erforderlichen Ressourcen mithilfe der Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="243a3-144">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="243a3-145">Lokales Erstellen von Funktionen mithilfe Ihrer bevorzugten IDE und Veröffentlichen der Funktionen in Azure.</span><span class="sxs-lookup"><span data-stu-id="243a3-145">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="243a3-146">Weitere Informationen zum Erstellen einer Skriptfunktion im Portal finden Sie unter [Erstellen Ihrer ersten Funktion im Azure-Portal](/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="243a3-146">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="243a3-147">Wenn Sie den Buildvorgang mit der Azure CLI ausführen möchten, finden Sie weitere Informationen unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="243a3-147">To build from the Azure CLI, see [Create your first function using the Azure CLI](/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="243a3-148">Informationen zum Erstellen einer Funktion aus Visual Studio finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="243a3-148">To create a function from Visual Studio, see [Create your first function using Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="243a3-149">Informationen zu Triggern und Bindungen</span><span class="sxs-lookup"><span data-stu-id="243a3-149">Understand triggers and bindings</span></span>

<span data-ttu-id="243a3-150">Funktionen werden von einem *Trigger* aufgerufen und können über genau einen Trigger verfügen.</span><span class="sxs-lookup"><span data-stu-id="243a3-150">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="243a3-151">Zusätzlich zum Aufrufen der Funktion dienen bestimmte Trigger auch als Bindungen.</span><span class="sxs-lookup"><span data-stu-id="243a3-151">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="243a3-152">Zusätzlich zum Trigger können Sie auch mehrere Bindungen definieren.</span><span class="sxs-lookup"><span data-stu-id="243a3-152">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="243a3-153">*Bindungen* stellen eine deklarative Möglichkeit zum Verbinden von Daten mit Ihrem Code bereit.</span><span class="sxs-lookup"><span data-stu-id="243a3-153">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="243a3-154">Sie können übergeben werden (Eingabe) oder Daten empfangen (Ausgabe).</span><span class="sxs-lookup"><span data-stu-id="243a3-154">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="243a3-155">Trigger und Bindungen erleichtern das Arbeiten mit Funktionen.</span><span class="sxs-lookup"><span data-stu-id="243a3-155">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="243a3-156">Durch Bindungen entfällt der Mehraufwand für das manuelle Erstellen von Datenbank- oder Dateisystemverbindungen.</span><span class="sxs-lookup"><span data-stu-id="243a3-156">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="243a3-157">Alle für die Bindungen benötigten Informationen sind in einer speziellen Datei *functions.json* für Skripts enthalten oder werden mit Attributen im Code deklariert.</span><span class="sxs-lookup"><span data-stu-id="243a3-157">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="243a3-158">Einige gängige Trigger sind:</span><span class="sxs-lookup"><span data-stu-id="243a3-158">Some common triggers include:</span></span>

- <span data-ttu-id="243a3-159">Blob Storage: Rufen Sie Ihre Funktion auf, wenn eine Datei oder ein Ordner in den Speicher hochgeladen oder dort geändert wird.</span><span class="sxs-lookup"><span data-stu-id="243a3-159">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="243a3-160">HTTP: Rufen Sie Ihre Funktion wie eine REST-API auf.</span><span class="sxs-lookup"><span data-stu-id="243a3-160">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="243a3-161">Queue: Rufen Sie die Funktion auf, wenn Elemente in einer Warteschlange vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="243a3-161">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="243a3-162">Timer: Rufen Sie Ihre Funktion in einem regulären Intervall auf.</span><span class="sxs-lookup"><span data-stu-id="243a3-162">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="243a3-163">Beispiele für Bindungen sind:</span><span class="sxs-lookup"><span data-stu-id="243a3-163">Examples of bindings include:</span></span>

- <span data-ttu-id="243a3-164">CosmosDB: Stellen Sie problemlos eine Verbindung mit der Datenbank her, um Dateien zu laden oder zu speichern.</span><span class="sxs-lookup"><span data-stu-id="243a3-164">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="243a3-165">Table Storage: Arbeiten Sie mit dem Schlüssel-Wert-Speicher aus Ihrer Funktions-App.</span><span class="sxs-lookup"><span data-stu-id="243a3-165">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="243a3-166">Queue Storage: Rufen Sie problemlos Elemente aus einer Warteschlange ab, oder speichern Sie neue Elemente in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="243a3-166">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="243a3-167">In der folgenden Beispieldatei *functions.json* wird ein Trigger und eine Bindung definiert:</span><span class="sxs-lookup"><span data-stu-id="243a3-167">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="243a3-168">In diesem Beispiel wird die Funktion durch eine Änderung am Blobspeicher im `images`-Container ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="243a3-168">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="243a3-169">Die Informationen für die Datei werden übergeben, sodass der Trigger auch als Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="243a3-169">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="243a3-170">Eine weitere Bindung ist vorhanden, um Informationen in eine Warteschlange namens `images`einzufügen.</span><span class="sxs-lookup"><span data-stu-id="243a3-170">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="243a3-171">Dies ist das C#-Skript für die Funktion:</span><span class="sxs-lookup"><span data-stu-id="243a3-171">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="243a3-172">Das Beispiel ist eine einfache Funktion, die den Namen der Datei annimmt, die geändert oder in den Blobspeicher hochgeladen wurde, und sie zur späteren Verarbeitung in einer Warteschlange platziert.</span><span class="sxs-lookup"><span data-stu-id="243a3-172">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="243a3-173">Eine vollständige Liste der Trigger und Bindungen finden Sie unter [Konzepte für Azure Functions-Trigger und -Bindungen](/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="243a3-173">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](/azure/azure-functions/functions-triggers-bindings).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="243a3-174">[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="243a3-174">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
