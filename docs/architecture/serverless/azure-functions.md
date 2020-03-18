---
title: 'Azure Functions: Serverlose Apps'
description: Azure Functions bietet serverlose Funktionen für mehrere Sprachen (C#, JavaScript, Java) und Plattformen, um ereignisgesteuerten Code für die sofortige Skalierung bereitzustellen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401484"
---
# <a name="azure-functions"></a><span data-ttu-id="8b33c-103">Überprüfung auf</span><span class="sxs-lookup"><span data-stu-id="8b33c-103">Azure Functions</span></span>

<span data-ttu-id="8b33c-104">Azure Functions bietet eine serverlose Computeerfahrung.</span><span class="sxs-lookup"><span data-stu-id="8b33c-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="8b33c-105">Eine Funktion wird durch einen *Trigger* aufgerufen (z.B. den Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Codeblock oder Geschäftslogik aus.</span><span class="sxs-lookup"><span data-stu-id="8b33c-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="8b33c-106">Funktionen unterstützen auch spezialisierte *Bindungen*, die eine Verbindung mit Ressourcen wie Speicher und Warteschlangen herstellen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions-Logo](./media/azure-functions-logo.png)

<span data-ttu-id="8b33c-108">Es gibt zwei Versionen des Azure Functions-Frameworks.</span><span class="sxs-lookup"><span data-stu-id="8b33c-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="8b33c-109">Die Legacyversion unterstützt die vollständige Version von .NET Framework, und die neue Runtime unterstützt plattformübergreifende .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="8b33c-110">Neben C# werden weitere Sprachen wie JavaScript, F# und Java unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b33c-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="8b33c-111">Funktionen, die im Portal erstellt werden, bieten eine umfangreiche Skriptsyntax.</span><span class="sxs-lookup"><span data-stu-id="8b33c-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="8b33c-112">Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Plattformunterstützung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8b33c-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="8b33c-113">Weitere Informationen finden Sie in der [Azure Functions-Dokumentation](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="8b33c-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="8b33c-114">Functions v1 im Vergleich zu v2</span><span class="sxs-lookup"><span data-stu-id="8b33c-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="8b33c-115">Es gibt zwei Versionen der Azure Functions-Runtime: 1.x und 2.x.</span><span class="sxs-lookup"><span data-stu-id="8b33c-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="8b33c-116">Version 1.x ist allgemein verfügbar (GA).</span><span class="sxs-lookup"><span data-stu-id="8b33c-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="8b33c-117">Sie unterstützt die .NET-Entwicklung im Portal oder auf Windows-Computern und verwendet .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b33c-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="8b33c-118">1.x unterstützt C#, JavaScript und F# und bietet experimentelle Unterstützung für Python, PHP, TypeScript, Batch, Bash und PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b33c-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="8b33c-119">[Version 2.x ist jetzt ebenfalls allgemein verfügbar](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="8b33c-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="8b33c-120">Sie nutzt .NET Core und unterstützt plattformübergreifende Entwicklung auf Windows-, macOS- und Linux-Computern.</span><span class="sxs-lookup"><span data-stu-id="8b33c-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="8b33c-121">2.x bietet erstklassige Unterstützung für Java, aber noch keine direkte Unterstützung für die experimentellen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="8b33c-122">Version 2.x verwendet ein neues Modell für die Bindungserweiterbarkeit, das Erweiterungen von Drittanbietern für die Plattform, unabhängige Versionsverwaltung von Bindungen und eine optimierte Ausführungsumgebung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8b33c-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="8b33c-123">**In 1.x gibt es ein bekanntes Problem mit [Bindungsumleitungsunterstützung](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="8b33c-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="8b33c-124">Das Problem ist spezifisch für die .NET-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="8b33c-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="8b33c-125">Projekte mit Abhängigkeiten von Bibliotheken, die eine andere Version als die Bibliotheken aufweisen, die in der Runtime enthalten sind, sind betroffen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="8b33c-126">Das Functions-Team hat sich zum Ziel gesetzt, konkrete Fortschritte bei der Lösung des Problems zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="8b33c-127">Das Team wird sich mit Bindungsumleitungen in Version 2.x befassen, bevor die allgemeine Verfügbarkeit bekanntgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8b33c-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="8b33c-128">Die offizielle Teamaussage mit den empfohlenen Korrekturen und Problemumgehungen finden Sie hier: [Assemblyauflösung in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="8b33c-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="8b33c-129">Weitere Informationen finden Sie unter [Vergleich von 1.x und 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="8b33c-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="8b33c-130">Unterstützung für Programmiersprachen</span><span class="sxs-lookup"><span data-stu-id="8b33c-130">Programming language support</span></span>

<span data-ttu-id="8b33c-131">Die folgenden Sprachen werden in Versionen mit allgemeiner Verfügbarkeit (GA), als Vorschau oder als experimentelles Feature unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b33c-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="8b33c-132">Sprache</span><span class="sxs-lookup"><span data-stu-id="8b33c-132">Language</span></span>      |<span data-ttu-id="8b33c-133">1.x</span><span class="sxs-lookup"><span data-stu-id="8b33c-133">1.x</span></span>         |<span data-ttu-id="8b33c-134">2.x</span><span class="sxs-lookup"><span data-stu-id="8b33c-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="8b33c-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="8b33c-135">**C#**</span></span>        |<span data-ttu-id="8b33c-136">Allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="8b33c-136">GA</span></span>          |<span data-ttu-id="8b33c-137">Vorschau</span><span class="sxs-lookup"><span data-stu-id="8b33c-137">Preview</span></span>  |
|<span data-ttu-id="8b33c-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="8b33c-138">**JavaScript**</span></span>|<span data-ttu-id="8b33c-139">Allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="8b33c-139">GA</span></span>          |<span data-ttu-id="8b33c-140">Vorschau</span><span class="sxs-lookup"><span data-stu-id="8b33c-140">Preview</span></span>  |
|<span data-ttu-id="8b33c-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="8b33c-141">**F#**</span></span>        |<span data-ttu-id="8b33c-142">Allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="8b33c-142">GA</span></span>          |         |
|<span data-ttu-id="8b33c-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="8b33c-143">**Java**</span></span>      |            |<span data-ttu-id="8b33c-144">Vorschau</span><span class="sxs-lookup"><span data-stu-id="8b33c-144">Preview</span></span>  |
|<span data-ttu-id="8b33c-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="8b33c-145">**Python**</span></span>    |<span data-ttu-id="8b33c-146">Experimentell</span><span class="sxs-lookup"><span data-stu-id="8b33c-146">Experimental</span></span>|         |
|<span data-ttu-id="8b33c-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="8b33c-147">**PHP**</span></span>       |<span data-ttu-id="8b33c-148">Experimentell</span><span class="sxs-lookup"><span data-stu-id="8b33c-148">Experimental</span></span>|         |
|<span data-ttu-id="8b33c-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="8b33c-149">**TypeScript**</span></span>|<span data-ttu-id="8b33c-150">Experimentell</span><span class="sxs-lookup"><span data-stu-id="8b33c-150">Experimental</span></span>|         |
|<span data-ttu-id="8b33c-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="8b33c-151">**Batch**</span></span>     |<span data-ttu-id="8b33c-152">Experimentell</span><span class="sxs-lookup"><span data-stu-id="8b33c-152">Experimental</span></span>|         |
|<span data-ttu-id="8b33c-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="8b33c-153">**Bash**</span></span>      |<span data-ttu-id="8b33c-154">Experimentell</span><span class="sxs-lookup"><span data-stu-id="8b33c-154">Experimental</span></span>|         |
|<span data-ttu-id="8b33c-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8b33c-155">**PowerShell**</span></span>|<span data-ttu-id="8b33c-156">Experimentell</span><span class="sxs-lookup"><span data-stu-id="8b33c-156">Experimental</span></span>|         |

<span data-ttu-id="8b33c-157">Weitere Informationen finden Sie unter [Unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="8b33c-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="8b33c-158">App Service-Pläne</span><span class="sxs-lookup"><span data-stu-id="8b33c-158">App service plans</span></span>

<span data-ttu-id="8b33c-159">Funktionen werden durch einen *App Service-Plan* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b33c-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="8b33c-160">Der Plan definiert die Ressourcen, die von der Funktions-App verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b33c-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="8b33c-161">Sie können einer Region Pläne zuweisen, die Größe und Anzahl der zu verwendenden virtuellen Computer bestimmen und einen Tarif auswählen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="8b33c-162">Für einen echten serverlosen Ansatz können Funktions-Apps den **Verbrauchstarif** verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b33c-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="8b33c-163">Der Verbrauchstarif skaliert das Back-End automatisch basierend auf der Auslastung.</span><span class="sxs-lookup"><span data-stu-id="8b33c-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="8b33c-164">Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="8b33c-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="8b33c-165">Erstellen Ihrer ersten Funktion</span><span class="sxs-lookup"><span data-stu-id="8b33c-165">Create your first function</span></span>

<span data-ttu-id="8b33c-166">Es gibt drei gängige Methoden, um Funktions-Apps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-166">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="8b33c-167">Skriptfunktionen im Portal.</span><span class="sxs-lookup"><span data-stu-id="8b33c-167">Script functions in the portal.</span></span>
- <span data-ttu-id="8b33c-168">Erstellen der erforderlichen Ressourcen mithilfe der Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="8b33c-168">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="8b33c-169">Lokales Erstellen von Funktionen mithilfe Ihrer bevorzugten IDE und Veröffentlichen der Funktionen in Azure.</span><span class="sxs-lookup"><span data-stu-id="8b33c-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="8b33c-170">Weitere Informationen zum Erstellen einer Skriptfunktion im Portal finden Sie unter [Erstellen Ihrer ersten Funktion im Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="8b33c-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="8b33c-171">Wenn Sie den Buildvorgang mit der Azure CLI ausführen möchten, finden Sie weitere Informationen unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="8b33c-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="8b33c-172">Informationen zum Erstellen einer Funktion aus Visual Studio finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="8b33c-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="8b33c-173">Informationen zu Triggern und Bindungen</span><span class="sxs-lookup"><span data-stu-id="8b33c-173">Understand triggers and bindings</span></span>

<span data-ttu-id="8b33c-174">Funktionen werden von einem *Trigger* aufgerufen und können über genau einen Trigger verfügen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="8b33c-175">Zusätzlich zum Aufrufen der Funktion dienen bestimmte Trigger auch als Bindungen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="8b33c-176">Zusätzlich zum Trigger können Sie auch mehrere Bindungen definieren.</span><span class="sxs-lookup"><span data-stu-id="8b33c-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="8b33c-177">*Bindungen* stellen eine deklarative Möglichkeit zum Verbinden von Daten mit Ihrem Code bereit.</span><span class="sxs-lookup"><span data-stu-id="8b33c-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="8b33c-178">Sie können übergeben werden (Eingabe) oder Daten empfangen (Ausgabe).</span><span class="sxs-lookup"><span data-stu-id="8b33c-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="8b33c-179">Trigger und Bindungen erleichtern das Arbeiten mit Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="8b33c-180">Durch Bindungen entfällt der Mehraufwand für das manuelle Erstellen von Datenbank- oder Dateisystemverbindungen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="8b33c-181">Alle für die Bindungen benötigten Informationen sind in einer speziellen Datei *functions.json* für Skripts enthalten oder werden mit Attributen im Code deklariert.</span><span class="sxs-lookup"><span data-stu-id="8b33c-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="8b33c-182">Einige gängige Trigger sind:</span><span class="sxs-lookup"><span data-stu-id="8b33c-182">Some common triggers include:</span></span>

- <span data-ttu-id="8b33c-183">Blob Storage: Rufen Sie Ihre Funktion auf, wenn eine Datei oder ein Ordner in den Speicher hochgeladen oder dort geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8b33c-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="8b33c-184">HTTP: Rufen Sie Ihre Funktion wie eine REST-API auf.</span><span class="sxs-lookup"><span data-stu-id="8b33c-184">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="8b33c-185">Queue: Rufen Sie die Funktion auf, wenn Elemente in einer Warteschlange vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8b33c-185">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="8b33c-186">Timer: Rufen Sie Ihre Funktion in einem regulären Intervall auf.</span><span class="sxs-lookup"><span data-stu-id="8b33c-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="8b33c-187">Beispiele für Bindungen sind:</span><span class="sxs-lookup"><span data-stu-id="8b33c-187">Examples of bindings include:</span></span>

- <span data-ttu-id="8b33c-188">CosmosDB: Stellen Sie problemlos eine Verbindung mit der Datenbank her, um Dateien zu laden oder zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8b33c-188">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="8b33c-189">Table Storage: Arbeiten Sie mit dem Schlüssel-Wert-Speicher aus Ihrer Funktions-App.</span><span class="sxs-lookup"><span data-stu-id="8b33c-189">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="8b33c-190">Queue Storage: Rufen Sie problemlos Elemente aus einer Warteschlange ab, oder speichern Sie neue Elemente in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="8b33c-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="8b33c-191">In der folgenden Beispieldatei *functions.json* wird ein Trigger und eine Bindung definiert:</span><span class="sxs-lookup"><span data-stu-id="8b33c-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="8b33c-192">In diesem Beispiel wird die Funktion durch eine Änderung am Blobspeicher im `images`-Container ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8b33c-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="8b33c-193">Die Informationen für die Datei werden übergeben, sodass der Trigger auch als Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="8b33c-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="8b33c-194">Eine weitere Bindung ist vorhanden, um Informationen in eine Warteschlange namens `images`einzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="8b33c-195">Dies ist das C#-Skript für die Funktion:</span><span class="sxs-lookup"><span data-stu-id="8b33c-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="8b33c-196">Das Beispiel ist eine einfache Funktion, die den Namen der Datei annimmt, die geändert oder in den Blobspeicher hochgeladen wurde, und sie zur späteren Verarbeitung in einer Warteschlange platziert.</span><span class="sxs-lookup"><span data-stu-id="8b33c-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="8b33c-197">Eine vollständige Liste der Trigger und Bindungen finden Sie unter [Konzepte für Azure Functions-Trigger und -Bindungen](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="8b33c-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="8b33c-198">Proxys</span><span class="sxs-lookup"><span data-stu-id="8b33c-198">Proxies</span></span>

<span data-ttu-id="8b33c-199">Proxys bieten Umleitungsfunktionen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8b33c-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="8b33c-200">Proxies stellen einen Endpunkt bereit und ordnen diesen Endpunkt einer anderen Ressource zu.</span><span class="sxs-lookup"><span data-stu-id="8b33c-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="8b33c-201">Mit Proxys haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="8b33c-201">With proxies, you can:</span></span>

- <span data-ttu-id="8b33c-202">Umleiten einer eingehenden Anforderung an einen anderen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b33c-202">Reroute an incoming request to another endpoint.</span></span>
- <span data-ttu-id="8b33c-203">Ändern der eingehenden Anforderung, bevor sie übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="8b33c-203">Modify the incoming request before it's passed along.</span></span>
- <span data-ttu-id="8b33c-204">Ändern oder Bereitstellen einer Antwort.</span><span class="sxs-lookup"><span data-stu-id="8b33c-204">Modify or provide a response.</span></span>

<span data-ttu-id="8b33c-205">Proxys werden beispielsweise für die folgenden Szenarien verwendet:</span><span class="sxs-lookup"><span data-stu-id="8b33c-205">Proxies are used for scenarios such as:</span></span>

- <span data-ttu-id="8b33c-206">Vereinfachen, Kürzen oder Ändern der URL.</span><span class="sxs-lookup"><span data-stu-id="8b33c-206">Simplifying, shortening, or changing the URL.</span></span>
- <span data-ttu-id="8b33c-207">Bereitstellen eines konsistenten API-Präfix für mehrere Back-End-Dienste.</span><span class="sxs-lookup"><span data-stu-id="8b33c-207">Providing a consistent API prefix to multiple back-end services.</span></span>
- <span data-ttu-id="8b33c-208">Simulieren einer Antwort an einen Endpunkt, der entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="8b33c-208">Mocking a response to an endpoint being developed.</span></span>
- <span data-ttu-id="8b33c-209">Bereitstellen einer statischen Antwort für einen bekannten Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="8b33c-209">Providing a static response to a well-known endpoint.</span></span>
- <span data-ttu-id="8b33c-210">Aufrechterhalten der Konsistenz eines API-Endpunkts, während das Back-End verschoben oder migriert wird.</span><span class="sxs-lookup"><span data-stu-id="8b33c-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="8b33c-211">Proxys werden als JSON-Definitionen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8b33c-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="8b33c-212">Im Folgenden ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8b33c-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="8b33c-213">Der `Domain Redirect`-Proxy verwendet eine gekürzte Route und ordnet sie der längeren Funktionsressource zu.</span><span class="sxs-lookup"><span data-stu-id="8b33c-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="8b33c-214">Die Transformation sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8b33c-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="8b33c-215">Der `Root`-Proxy verwendet alles, was an die Stamm-URL (`https://--shorturl--/`) gesendet wird, und leitet es an die Dokumentationswebsite weiter.</span><span class="sxs-lookup"><span data-stu-id="8b33c-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="8b33c-216">Ein Beispiel für die Verwendung von Proxys sehen Sie im Video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102) (Migrieren einer App zur Cloud mit serverlosen Azure Functions).</span><span class="sxs-lookup"><span data-stu-id="8b33c-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="8b33c-217">In Echtzeit wird eine ASP.NET Core-Anwendung, die auf einem lokalen SQL-Server ausgeführt wird, zur Azure-Cloud migriert.</span><span class="sxs-lookup"><span data-stu-id="8b33c-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="8b33c-218">Proxys werden verwendet, um das Refactoring eines traditionellen Web-API-Projekts zur Verwendung von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8b33c-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="8b33c-219">Weitere Informationen zu Proxys finden Sie unter [Arbeiten mit Azure Functions-Proxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="8b33c-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8b33c-220">[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="8b33c-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
