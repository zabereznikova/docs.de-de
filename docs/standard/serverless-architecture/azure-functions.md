---
title: Azure Functions – serverlose apps
description: Azure Functions bietet serverlose Funktionen in mehreren Sprachen (c#, JavaScript, Java) und Plattformen ereignisgesteuerte sofortige Skalierung Code.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754236"
---
# <a name="azure-functions"></a><span data-ttu-id="e4703-103">Überprüfung auf</span><span class="sxs-lookup"><span data-stu-id="e4703-103">Azure Functions</span></span>

<span data-ttu-id="e4703-104">Azure Functions bietet eine serverlosen computeoberfläche.</span><span class="sxs-lookup"><span data-stu-id="e4703-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="e4703-105">Eine Funktion wird aufgerufen, indem eine *Trigger* (z. B. Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Anweisungsblock Code oder die Geschäftslogik aus.</span><span class="sxs-lookup"><span data-stu-id="e4703-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="e4703-106">Unterstützt auch spezielle Funktionen *Bindungen* , die Verbindung mit Ressourcen wie Speichersystemen und Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="e4703-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions-logo](./media/azure-functions-logo.png)

<span data-ttu-id="e4703-108">Es gibt zwei Versionen von Azure Functions-Framework.</span><span class="sxs-lookup"><span data-stu-id="e4703-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="e4703-109">Die ältere Version unterstützt das vollständige .NET Framework und die neue Runtime unterstützt die plattformübergreifende .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e4703-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="e4703-110">Weitere Sprachen neben C# wie z.B. JavaScript F#, und Java werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4703-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="e4703-111">Im Portal erstellte Funktionen bieten eine umfangreiche Syntax für die Skripterstellung.</span><span class="sxs-lookup"><span data-stu-id="e4703-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="e4703-112">Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Unterstützung und Funktionen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e4703-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="e4703-113">Weitere Informationen finden Sie unter [Dokumentation zu Azure Functions](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="e4703-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="e4703-114">Funktionen von v1 und v2</span><span class="sxs-lookup"><span data-stu-id="e4703-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="e4703-115">Es gibt zwei Versionen von Azure Functions-Laufzeit: 1.x und 2.x.</span><span class="sxs-lookup"><span data-stu-id="e4703-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="e4703-116">Version 1.x ist allgemein verfügbar (GA).</span><span class="sxs-lookup"><span data-stu-id="e4703-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="e4703-117">Es unterstützt die Entwicklung von .NET über das Portal oder die Windows-Computer und verwendet die .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4703-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="e4703-118">1.x unterstützt C#, JavaScript und F#, experimentelle Unterstützung für Python, PHP, TypeScript, Batch, Bash und PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4703-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="e4703-119">[Version 2.x ist nun ebenfalls allgemein verfügbar](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="e4703-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="e4703-120">Es nutzt die .NET Core und unterstützt die plattformübergreifende Entwicklung unter Windows, MacOS und Linux-Computer.</span><span class="sxs-lookup"><span data-stu-id="e4703-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="e4703-121">2.x bietet erstklassige Unterstützung für Java, aber noch direkt unterstützt keine experimentellen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="e4703-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="e4703-122">Version 2.x verwendet ein neues Erweiterbarkeitsmodell von Bindung, die Erweiterungen von Drittanbietern für die Plattform, Bindungen, voneinander unabhängige Versionen ermöglicht und eine optimierte ausführungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="e4703-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="e4703-123">**Es gibt ein bekanntes Problem in 1.x mit [Umleitung bindungsunterstützung](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="e4703-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="e4703-124">Das Problem ist spezifisch für die Entwicklung von .NET.</span><span class="sxs-lookup"><span data-stu-id="e4703-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="e4703-125">Projekte mit Abhängigkeiten von Bibliotheken, die eine andere Version der Bibliotheken, die in der Laufzeit enthalten sind, sind betroffen.</span><span class="sxs-lookup"><span data-stu-id="e4703-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="e4703-126">Die Functions-Team für die konkrete Fortschritte auf dem Problem zugesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="e4703-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="e4703-127">Das Team werden bindungsumleitungen in 2.x behandelt, bevor er in der allgemeinen Verfügbarkeit geht.</span><span class="sxs-lookup"><span data-stu-id="e4703-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="e4703-128">Die offizielle Team-Anweisung mit empfohlenen Problembehebungen und problemumgehungen ist hier verfügbar: [Assembly-Auflösung in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="e4703-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="e4703-129">Weitere Informationen finden Sie unter [Vergleichen von 1.x und 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="e4703-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="e4703-130">Unterstützung für Programmiersprachen</span><span class="sxs-lookup"><span data-stu-id="e4703-130">Programming language support</span></span>

<span data-ttu-id="e4703-131">Die folgenden Sprachen unterstützt werden entweder im allgemeinen Verfügbarkeit (GA), in der Vorschau anzuzeigen oder experimentell.</span><span class="sxs-lookup"><span data-stu-id="e4703-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="e4703-132">Sprache</span><span class="sxs-lookup"><span data-stu-id="e4703-132">Language</span></span>      |<span data-ttu-id="e4703-133">1.x</span><span class="sxs-lookup"><span data-stu-id="e4703-133">1.x</span></span>         |<span data-ttu-id="e4703-134">2.x</span><span class="sxs-lookup"><span data-stu-id="e4703-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="e4703-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="e4703-135">**C#**</span></span>        |<span data-ttu-id="e4703-136">GA</span><span class="sxs-lookup"><span data-stu-id="e4703-136">GA</span></span>          |<span data-ttu-id="e4703-137">Vorschau</span><span class="sxs-lookup"><span data-stu-id="e4703-137">Preview</span></span>  |
|<span data-ttu-id="e4703-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="e4703-138">**JavaScript**</span></span>|<span data-ttu-id="e4703-139">GA</span><span class="sxs-lookup"><span data-stu-id="e4703-139">GA</span></span>          |<span data-ttu-id="e4703-140">Vorschau</span><span class="sxs-lookup"><span data-stu-id="e4703-140">Preview</span></span>  |
|<span data-ttu-id="e4703-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="e4703-141">**F#**</span></span>        |<span data-ttu-id="e4703-142">GA</span><span class="sxs-lookup"><span data-stu-id="e4703-142">GA</span></span>          |         |
|<span data-ttu-id="e4703-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="e4703-143">**Java**</span></span>      |            |<span data-ttu-id="e4703-144">Vorschau</span><span class="sxs-lookup"><span data-stu-id="e4703-144">Preview</span></span>  |
|<span data-ttu-id="e4703-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="e4703-145">**Python**</span></span>    |<span data-ttu-id="e4703-146">Experimentell</span><span class="sxs-lookup"><span data-stu-id="e4703-146">Experimental</span></span>|         |
|<span data-ttu-id="e4703-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="e4703-147">**PHP**</span></span>       |<span data-ttu-id="e4703-148">Experimentell</span><span class="sxs-lookup"><span data-stu-id="e4703-148">Experimental</span></span>|         |
|<span data-ttu-id="e4703-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="e4703-149">**TypeScript**</span></span>|<span data-ttu-id="e4703-150">Experimentell</span><span class="sxs-lookup"><span data-stu-id="e4703-150">Experimental</span></span>|         |
|<span data-ttu-id="e4703-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="e4703-151">**Batch**</span></span>     |<span data-ttu-id="e4703-152">Experimentell</span><span class="sxs-lookup"><span data-stu-id="e4703-152">Experimental</span></span>|         |
|<span data-ttu-id="e4703-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="e4703-153">**Bash**</span></span>      |<span data-ttu-id="e4703-154">Experimentell</span><span class="sxs-lookup"><span data-stu-id="e4703-154">Experimental</span></span>|         |
|<span data-ttu-id="e4703-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e4703-155">**PowerShell**</span></span>|<span data-ttu-id="e4703-156">Experimentell</span><span class="sxs-lookup"><span data-stu-id="e4703-156">Experimental</span></span>|         |

<span data-ttu-id="e4703-157">Weitere Informationen finden Sie unter [unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="e4703-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="e4703-158">App Service-Pläne</span><span class="sxs-lookup"><span data-stu-id="e4703-158">App service plans</span></span>

<span data-ttu-id="e4703-159">Funktionen verfügen über eine *app Service-Plan*.</span><span class="sxs-lookup"><span data-stu-id="e4703-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="e4703-160">Der Plan definiert die von der Functions-app verwendeten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="e4703-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="e4703-161">Sie können Pläne in einer Region zuweisen, bestimmen die Größe und Anzahl von virtuellen Computern, die verwendet werden, und wählen Sie einen Tarif.</span><span class="sxs-lookup"><span data-stu-id="e4703-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="e4703-162">Für einen Ansatz mit "true" serverlosen Funktionen-apps verwenden die **Verbrauch** Plan.</span><span class="sxs-lookup"><span data-stu-id="e4703-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="e4703-163">Das Back-End automatisch je nach Auslastung kann der verbrauchsbasierten Verbrauchsplan skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="e4703-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="e4703-164">Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="e4703-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="e4703-165">Erstellen Sie Ihrer ersten Funktion</span><span class="sxs-lookup"><span data-stu-id="e4703-165">Create your first function</span></span>

<span data-ttu-id="e4703-166">Es gibt drei Möglichkeiten, die Sie die Funktions-apps erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e4703-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="e4703-167">ScriptEngine-Funktionen im Portal.</span><span class="sxs-lookup"><span data-stu-id="e4703-167">Script functions in the portal.</span></span>
* <span data-ttu-id="e4703-168">Erstellen Sie die erforderlichen Ressourcen mithilfe der Azure-Befehlszeilenschnittstelle (CLI).</span><span class="sxs-lookup"><span data-stu-id="e4703-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="e4703-169">Erstellen Sie Funktionen lokal mit Ihrer bevorzugten IDE, und veröffentlichen Sie sie in Azure.</span><span class="sxs-lookup"><span data-stu-id="e4703-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="e4703-170">Weitere Informationen zum Erstellen einer skriptgesteuerten Funktion im Portal finden Sie unter [Erstellen Ihrer ersten Funktion im Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="e4703-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="e4703-171">Um über das Azure-Befehlszeilenschnittstelle zu erstellen, finden Sie unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="e4703-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="e4703-172">Um eine Funktion von Visual Studio zu erstellen, finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e4703-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="e4703-173">Verstehen von Triggern und Bindungen</span><span class="sxs-lookup"><span data-stu-id="e4703-173">Understand triggers and bindings</span></span>

<span data-ttu-id="e4703-174">Funktionen aufgerufen werden, indem eine *Trigger* sind genau möglich.</span><span class="sxs-lookup"><span data-stu-id="e4703-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="e4703-175">Bestimmte Trigger stellen zusätzlich zum Aufrufen der Funktion können auch Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e4703-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="e4703-176">Sie können auch mehrere Bindungen zusätzlich zu den Trigger definieren.</span><span class="sxs-lookup"><span data-stu-id="e4703-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="e4703-177">*Bindungen* bieten eine deklarative Möglichkeit, Daten zu Ihrem Code zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="e4703-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="e4703-178">Sie können im (Eingabe) übergeben werden oder Empfangen von Daten (Ausgabe).</span><span class="sxs-lookup"><span data-stu-id="e4703-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="e4703-179">Trigger und Bindungen stellen Funktionen einfach zu können.</span><span class="sxs-lookup"><span data-stu-id="e4703-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="e4703-180">Entfernen Sie Bindungen systemverbindungen Datenbank oder Datei manuell erstellt.</span><span class="sxs-lookup"><span data-stu-id="e4703-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="e4703-181">Alle Informationen, die erforderlich sind, für die Bindungen befindet sich in einem speziellen *"Functions.JSON"* -Datei für Skripts oder mit Attributen im Code deklariert.</span><span class="sxs-lookup"><span data-stu-id="e4703-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="e4703-182">Einige gängigen Trigger enthalten:</span><span class="sxs-lookup"><span data-stu-id="e4703-182">Some common triggers include:</span></span>

* <span data-ttu-id="e4703-183">BLOB-Speicher: Rufen Sie Ihre Funktion auf, wenn eine Datei oder einen Ordner hochgeladen oder im Speicher geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e4703-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="e4703-184">HTTP: Rufen Sie die Funktion wie eine REST-API.</span><span class="sxs-lookup"><span data-stu-id="e4703-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="e4703-185">Warteschlange: Aufrufen der Funktion aus, wenn Elemente in einer Warteschlange vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e4703-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="e4703-186">Timer: Rufen Sie Ihre Funktion in regelmäßigen Abständen.</span><span class="sxs-lookup"><span data-stu-id="e4703-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="e4703-187">Beispiele für Bindungen sind:</span><span class="sxs-lookup"><span data-stu-id="e4703-187">Examples of bindings include:</span></span>

* <span data-ttu-id="e4703-188">COSMOS DB: problemlos Herstellen einer Verbindung mit der Datenbank zu laden oder Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="e4703-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="e4703-189">Tabellenspeicher: Arbeiten Sie mit Schlüssel/Wert-Speicher aus Ihrer Funktionen-app.</span><span class="sxs-lookup"><span data-stu-id="e4703-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="e4703-190">Warteschlangenspeicher: problemlos Abrufen von Elementen aus einer Warteschlange, oder platzieren Sie neue Elemente in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="e4703-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="e4703-191">Im folgenden Beispiel *"Functions.JSON"* -Datei definiert wird, einen Trigger und eine Bindung:</span><span class="sxs-lookup"><span data-stu-id="e4703-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="e4703-192">In diesem Beispiel wird die Funktion ausgelöst, durch eine Änderung in den blobspeicher in die `images` Container.</span><span class="sxs-lookup"><span data-stu-id="e4703-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="e4703-193">Die Informationen für die Datei ist, übergeben, damit der Trigger außerdem als Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="e4703-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="e4703-194">Eine andere Bindung vorhanden ist, um die Informationen in eine Warteschlange mit dem Namen `images`.</span><span class="sxs-lookup"><span data-stu-id="e4703-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="e4703-195">Hier ist der C#-Skript für die Funktion:</span><span class="sxs-lookup"><span data-stu-id="e4703-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="e4703-196">Das Beispiel ist eine einfache Funktion, die dem Namen der Datei, die akzeptiert wurde geändert oder BLOB-Speicher hochgeladen, und platziert es in eine Warteschlange für die spätere Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="e4703-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="e4703-197">Eine vollständige Liste von Triggern und Bindungen, finden Sie unter [Konzepte Azure Functions-Trigger und-Bindungen](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="e4703-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="e4703-198">Proxys</span><span class="sxs-lookup"><span data-stu-id="e4703-198">Proxies</span></span>

<span data-ttu-id="e4703-199">Proxys geben den umleitungs-Funktionalität für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e4703-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="e4703-200">Proxys einen Endpunkt verfügbar machen, und ordnen Sie diesen Endpunkt zu einer anderen Ressource.</span><span class="sxs-lookup"><span data-stu-id="e4703-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="e4703-201">Mit Proxys möglich ist können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e4703-201">With proxies, you can:</span></span>

* <span data-ttu-id="e4703-202">Eine eingehende Anforderung an einen anderen Endpunkt umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e4703-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="e4703-203">Ändern Sie die eingehende Anforderung aus, bevor sie weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4703-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="e4703-204">Ändern Sie, oder geben Sie eine Antwort.</span><span class="sxs-lookup"><span data-stu-id="e4703-204">Modify or provide a response.</span></span>

<span data-ttu-id="e4703-205">Proxys werden z. B. für Szenarien verwendet:</span><span class="sxs-lookup"><span data-stu-id="e4703-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="e4703-206">Vereinfachen, verkürzen, oder Ändern der URL.</span><span class="sxs-lookup"><span data-stu-id="e4703-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="e4703-207">Bereitstellen einer API-präfixkonsistenz an mehrere Back-End-Dienste.</span><span class="sxs-lookup"><span data-stu-id="e4703-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="e4703-208">Simulieren eine Antwort an einen Endpunkt, entwickelt.</span><span class="sxs-lookup"><span data-stu-id="e4703-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="e4703-209">Bereitstellen von statischen Antwort auf einen bekannten Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="e4703-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="e4703-210">API-Endpunkt Sicherstellen der Konsistenz und während das Back-End migriert oder verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="e4703-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="e4703-211">Proxys werden als JSON-Definitionen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e4703-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="e4703-212">Im Folgenden ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e4703-212">Here is an example:</span></span>

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

<span data-ttu-id="e4703-213">Die `Domain Redirect` Proxy akzeptiert eine verkürzte Route und ordnet es zu längeren Funktion Ressource.</span><span class="sxs-lookup"><span data-stu-id="e4703-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="e4703-214">Die Transformation sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e4703-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="e4703-215">Die `Root` Proxy wird alles gesendet, um die Stamm-URL (`https://--shorturl--/`) und leitet ihn an der Dokumentationswebsite.</span><span class="sxs-lookup"><span data-stu-id="e4703-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="e4703-216">Ein Beispiel der Verwendung von Proxys im Video [Azure: Bringen Sie Ihre app in die Cloud mit serverlosen Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span><span class="sxs-lookup"><span data-stu-id="e4703-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="e4703-217">In Echtzeit wird eine ASP.NET Core-Anwendung, die auf lokalen SQL Server ausgeführt wird mit der Azure Cloud migriert.</span><span class="sxs-lookup"><span data-stu-id="e4703-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="e4703-218">Proxys werden verwendet, um zu ein herkömmlichen Web-API-Projekt zum Verwenden der Funktionen Umgestalten.</span><span class="sxs-lookup"><span data-stu-id="e4703-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="e4703-219">Weitere Informationen zu Proxys finden Sie unter [arbeiten mit Azure Functions-Proxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="e4703-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e4703-220">[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="e4703-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
