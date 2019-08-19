---
title: Azure Functions Server Lose apps
description: Azure Functions bietet Server lose Funktionen in mehreren Sprachen (C#JavaScript, Java) und Plattformen, um ereignisgesteuerten Code für die sofortige Skalierung bereitzustellen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577603"
---
# <a name="azure-functions"></a><span data-ttu-id="b4061-103">Überprüfung auf</span><span class="sxs-lookup"><span data-stu-id="b4061-103">Azure Functions</span></span>

<span data-ttu-id="b4061-104">Azure Functions bietet eine Server lose computeerfahrung.</span><span class="sxs-lookup"><span data-stu-id="b4061-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="b4061-105">Eine Funktion wird von einem *Trigger* aufgerufen (z. b. Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Codeblock oder eine Geschäftslogik aus.</span><span class="sxs-lookup"><span data-stu-id="b4061-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="b4061-106">Funktionen unterstützen außerdem spezialisierte *Bindungen* , die eine Verbindung mit Ressourcen wie Speicher und Warteschlangen herstellen.</span><span class="sxs-lookup"><span data-stu-id="b4061-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions-Logo](./media/azure-functions-logo.png)

<span data-ttu-id="b4061-108">Es gibt zwei Versionen des Azure Functions-Frameworks.</span><span class="sxs-lookup"><span data-stu-id="b4061-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="b4061-109">Die Legacy Version unterstützt die vollständige .NET Framework und die neue Laufzeit unterstützt plattformübergreifende .net Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b4061-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="b4061-110">Neben C# JavaScript, F#und Java werden weitere Sprachen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4061-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="b4061-111">Funktionen, die im Portal erstellt werden, bieten eine umfangreiche Skript Syntax.</span><span class="sxs-lookup"><span data-stu-id="b4061-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="b4061-112">Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Platt Form Unterstützung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b4061-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="b4061-113">Weitere Informationen finden Sie unter [Azure Functions-Dokumentation](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="b4061-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="b4061-114">Functions v1 und v2</span><span class="sxs-lookup"><span data-stu-id="b4061-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="b4061-115">Es gibt zwei Versionen der Azure Functions Laufzeit: 1. x und 2. x.</span><span class="sxs-lookup"><span data-stu-id="b4061-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="b4061-116">Version 1. x ist allgemein verfügbar (GA).</span><span class="sxs-lookup"><span data-stu-id="b4061-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="b4061-117">Es unterstützt die .net-Entwicklung im Portal oder auf Windows-Computern und verwendet die .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b4061-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="b4061-118">1. x unter C#stützt, JavaScript und F#und bietet experimentelle Unterstützung für python, PHP, typescript, Batch, bash und PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4061-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="b4061-119">[Version 2. x ist jetzt auch allgemein verfügbar](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="b4061-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="b4061-120">Es nutzt .net Core und unterstützt die plattformübergreifende Entwicklung auf Windows-, macOS-und Linux-Computern.</span><span class="sxs-lookup"><span data-stu-id="b4061-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="b4061-121">2. x bietet erstklassige Unterstützung für Java, bietet aber noch keine direkte Unterstützung für die experimentellen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="b4061-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="b4061-122">Version 2. x verwendet ein neues Modell für die Bindungs Erweiterbarkeit, das Erweiterungen von Drittanbietern für die Plattform, unabhängige Versionsverwaltung von Bindungen und eine optimierte Ausführungsumgebung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b4061-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="b4061-123">**In 1. x ist ein bekanntes Problem mit der [Unterstützung für die Bindungs Umleitung](https://github.com/Azure/azure-functions-host/issues/992)aufgetreten.**</span><span class="sxs-lookup"><span data-stu-id="b4061-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="b4061-124">Das Problem ist spezifisch für die .net-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="b4061-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="b4061-125">Projekte mit Abhängigkeiten von Bibliotheken, die eine andere Version als die Bibliotheken enthalten, die in der Laufzeit enthalten sind, sind betroffen.</span><span class="sxs-lookup"><span data-stu-id="b4061-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="b4061-126">Das Functions-Team hat sich verpflichtet, konkrete Statusinformationen zu dem Problem zu treffen.</span><span class="sxs-lookup"><span data-stu-id="b4061-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="b4061-127">Das Team adressiert Bindungs Umleitungen in 2. x, bevor es in die allgemeine Verfügbarkeit übergeht.</span><span class="sxs-lookup"><span data-stu-id="b4061-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="b4061-128">Die offizielle Team Anweisung mit den empfohlenen Korrekturen und Problem Umgehungen finden Sie hier: Assemblyauflösung [in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="b4061-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="b4061-129">Weitere Informationen finden Sie unter [Vergleichen von 1. x und 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="b4061-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="b4061-130">Unterstützung für Programmiersprachen</span><span class="sxs-lookup"><span data-stu-id="b4061-130">Programming language support</span></span>

<span data-ttu-id="b4061-131">Die folgenden Sprachen werden entweder in allgemeiner Verfügbarkeit (GA), Vorschau oder experimentell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4061-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="b4061-132">Sprache</span><span class="sxs-lookup"><span data-stu-id="b4061-132">Language</span></span>      |<span data-ttu-id="b4061-133">1. x</span><span class="sxs-lookup"><span data-stu-id="b4061-133">1.x</span></span>         |<span data-ttu-id="b4061-134">2.x</span><span class="sxs-lookup"><span data-stu-id="b4061-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="b4061-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="b4061-135">**C#**</span></span>        |<span data-ttu-id="b4061-136">GAS</span><span class="sxs-lookup"><span data-stu-id="b4061-136">GA</span></span>          |<span data-ttu-id="b4061-137">Vorschau</span><span class="sxs-lookup"><span data-stu-id="b4061-137">Preview</span></span>  |
|<span data-ttu-id="b4061-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="b4061-138">**JavaScript**</span></span>|<span data-ttu-id="b4061-139">GAS</span><span class="sxs-lookup"><span data-stu-id="b4061-139">GA</span></span>          |<span data-ttu-id="b4061-140">Vorschau</span><span class="sxs-lookup"><span data-stu-id="b4061-140">Preview</span></span>  |
|<span data-ttu-id="b4061-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="b4061-141">**F#**</span></span>        |<span data-ttu-id="b4061-142">GAS</span><span class="sxs-lookup"><span data-stu-id="b4061-142">GA</span></span>          |         |
|<span data-ttu-id="b4061-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="b4061-143">**Java**</span></span>      |            |<span data-ttu-id="b4061-144">Vorschau</span><span class="sxs-lookup"><span data-stu-id="b4061-144">Preview</span></span>  |
|<span data-ttu-id="b4061-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="b4061-145">**Python**</span></span>    |<span data-ttu-id="b4061-146">Experimentell</span><span class="sxs-lookup"><span data-stu-id="b4061-146">Experimental</span></span>|         |
|<span data-ttu-id="b4061-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="b4061-147">**PHP**</span></span>       |<span data-ttu-id="b4061-148">Experimentell</span><span class="sxs-lookup"><span data-stu-id="b4061-148">Experimental</span></span>|         |
|<span data-ttu-id="b4061-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="b4061-149">**TypeScript**</span></span>|<span data-ttu-id="b4061-150">Experimentell</span><span class="sxs-lookup"><span data-stu-id="b4061-150">Experimental</span></span>|         |
|<span data-ttu-id="b4061-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="b4061-151">**Batch**</span></span>     |<span data-ttu-id="b4061-152">Experimentell</span><span class="sxs-lookup"><span data-stu-id="b4061-152">Experimental</span></span>|         |
|<span data-ttu-id="b4061-153">**Verschlüsselt**</span><span class="sxs-lookup"><span data-stu-id="b4061-153">**Bash**</span></span>      |<span data-ttu-id="b4061-154">Experimentell</span><span class="sxs-lookup"><span data-stu-id="b4061-154">Experimental</span></span>|         |
|<span data-ttu-id="b4061-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b4061-155">**PowerShell**</span></span>|<span data-ttu-id="b4061-156">Experimentell</span><span class="sxs-lookup"><span data-stu-id="b4061-156">Experimental</span></span>|         |

<span data-ttu-id="b4061-157">Weitere Informationen finden Sie unter [Sprach- und Regionsunterstützung für die Textanalyse-API](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="b4061-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="b4061-158">App Service-Pläne</span><span class="sxs-lookup"><span data-stu-id="b4061-158">App service plans</span></span>

<span data-ttu-id="b4061-159">Funktionen werden durch einen *App Service-Plan*unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4061-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="b4061-160">Der Plan definiert die Ressourcen, die von der Functions-App verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4061-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="b4061-161">Sie können einem Bereich Pläne zuweisen, die Größe und Anzahl der zu verwendenden virtuellen Computer ermitteln und einen Tarif auswählen.</span><span class="sxs-lookup"><span data-stu-id="b4061-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="b4061-162">Für einen echten Server losen Ansatz können Funktions-apps den **Verbrauchs** Plan verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4061-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="b4061-163">Der Verbrauchs Plan skaliert das Back-End automatisch basierend auf der Auslastung.</span><span class="sxs-lookup"><span data-stu-id="b4061-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="b4061-164">Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="b4061-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="b4061-165">Erstellen Ihrer ersten Funktion</span><span class="sxs-lookup"><span data-stu-id="b4061-165">Create your first function</span></span>

<span data-ttu-id="b4061-166">Es gibt drei gängige Methoden, um Funktions-apps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4061-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="b4061-167">Skriptfunktionen im Portal.</span><span class="sxs-lookup"><span data-stu-id="b4061-167">Script functions in the portal.</span></span>
* <span data-ttu-id="b4061-168">Erstellen Sie die erforderlichen Ressourcen mithilfe der Azure-Befehlszeilenschnittstelle (CLI).</span><span class="sxs-lookup"><span data-stu-id="b4061-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="b4061-169">Erstellen Sie Funktionen lokal mithilfe Ihrer bevorzugten IDE, und veröffentlichen Sie Sie in Azure.</span><span class="sxs-lookup"><span data-stu-id="b4061-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="b4061-170">Weitere Informationen zum Erstellen einer Skriptfunktion im Portal finden [Sie unter Erstellen Ihrer ersten Funktion in der Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="b4061-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="b4061-171">Informationen zum Erstellen aus der Azure CLI finden Sie unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="b4061-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="b4061-172">Informationen zum Erstellen einer Funktion aus Visual Studio finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b4061-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="b4061-173">Grundlegendes zu Triggern und Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4061-173">Understand triggers and bindings</span></span>

<span data-ttu-id="b4061-174">Funktionen werden von einem- Aufruf aufgerufen und können über genau einen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b4061-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="b4061-175">Zusätzlich zum Aufrufen der Funktion dienen bestimmte Trigger auch als Bindungen.</span><span class="sxs-lookup"><span data-stu-id="b4061-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="b4061-176">Zusätzlich zum-Vorgang können auch mehrere Bindungen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4061-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="b4061-177">*Bindungen* bieten eine deklarative Möglichkeit, um Daten mit Ihrem Code zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="b4061-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="b4061-178">Sie können an (Eingabe) oder empfangende Daten (Ausgabe) übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="b4061-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="b4061-179">Trigger und Bindungen erleichtern das Arbeiten mit Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4061-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="b4061-180">Bindungen entfernen den Aufwand für das manuelle Erstellen von Datenbank-oder Dateisystem Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="b4061-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="b4061-181">Alle Informationen, die für die Bindungen benötigt werden, sind in einer speziellen Datei " *Functions. JSON* " für Skripts enthalten oder mit Attributen im Code deklariert.</span><span class="sxs-lookup"><span data-stu-id="b4061-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="b4061-182">Einige gängige Trigger sind:</span><span class="sxs-lookup"><span data-stu-id="b4061-182">Some common triggers include:</span></span>

* <span data-ttu-id="b4061-183">BLOB Storage: Rufen Sie Ihre Funktion auf, wenn eine Datei oder ein Ordner im Speicher hochgeladen oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b4061-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="b4061-184">HTTP: Rufen Sie Ihre Funktion wie eine Rest-API auf.</span><span class="sxs-lookup"><span data-stu-id="b4061-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="b4061-185">Queue: Rufen Sie die Funktion auf, wenn Elemente in einer Warteschlange vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b4061-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="b4061-186">Timer: Rufen Sie Ihre Funktion in einem regulären Rhythmus auf.</span><span class="sxs-lookup"><span data-stu-id="b4061-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="b4061-187">Beispiele für Bindungen sind:</span><span class="sxs-lookup"><span data-stu-id="b4061-187">Examples of bindings include:</span></span>

* <span data-ttu-id="b4061-188">Cosmosdb: Stellen Sie problemlos eine Verbindung mit der Datenbank her, um Dateien zu laden oder zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b4061-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="b4061-189">Table Storage: Arbeiten Sie mit dem Schlüssel-Wert-Speicher von ihrer Funktionen-app.</span><span class="sxs-lookup"><span data-stu-id="b4061-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="b4061-190">Queue Storage: problemlos Elemente aus einer Warteschlange abrufen oder neue Elemente in der Warteschlange platzieren.</span><span class="sxs-lookup"><span data-stu-id="b4061-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="b4061-191">Die folgende Beispieldatei " *Functions. JSON* " definiert einen-und eine-Bindung:</span><span class="sxs-lookup"><span data-stu-id="b4061-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="b4061-192">In diesem Beispiel wird die Funktion durch eine Änderung des BLOB-Speichers im `images` Container ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b4061-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="b4061-193">Die Informationen für die Datei werden an die Datei übertragen, sodass der-Triggerwert auch als Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="b4061-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="b4061-194">Eine weitere Bindung besteht darin, Informationen in eine Warte `images`Schlange mit dem Namen einzufügen.</span><span class="sxs-lookup"><span data-stu-id="b4061-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="b4061-195">Hier ist das C# Skript für die-Funktion:</span><span class="sxs-lookup"><span data-stu-id="b4061-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="b4061-196">Das Beispiel ist eine einfache Funktion, die den Namen der Datei annimmt, die geändert oder in den BLOB-Speicher hochgeladen wurde, und Sie zur späteren Verarbeitung in eine Warteschlange platziert.</span><span class="sxs-lookup"><span data-stu-id="b4061-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="b4061-197">Eine vollständige Liste der Trigger und Bindungen finden Sie unter [Azure Functions Trigger und Bindungen Konzepte](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="b4061-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="b4061-198">Proxys</span><span class="sxs-lookup"><span data-stu-id="b4061-198">Proxies</span></span>

<span data-ttu-id="b4061-199">Proxys stellen Umleitungs Funktionen für Ihre Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="b4061-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="b4061-200">Proxys machen einen Endpunkt verfügbar und ordnen diesen Endpunkt einer anderen Ressource zu.</span><span class="sxs-lookup"><span data-stu-id="b4061-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="b4061-201">Mit Proxys können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b4061-201">With proxies, you can:</span></span>

* <span data-ttu-id="b4061-202">Leitet eine eingehende Anforderung an einen anderen Endpunkt um.</span><span class="sxs-lookup"><span data-stu-id="b4061-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="b4061-203">Ändern Sie die eingehende Anforderung, bevor Sie weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b4061-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="b4061-204">Ändern oder Bereitstellen einer Antwort.</span><span class="sxs-lookup"><span data-stu-id="b4061-204">Modify or provide a response.</span></span>

<span data-ttu-id="b4061-205">Proxys werden für folgende Szenarien verwendet:</span><span class="sxs-lookup"><span data-stu-id="b4061-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="b4061-206">Vereinfachen, verkürzen oder Ändern der URL.</span><span class="sxs-lookup"><span data-stu-id="b4061-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="b4061-207">Bereitstellen eines konsistenten API-Präfixes für mehrere Back-End-Dienste.</span><span class="sxs-lookup"><span data-stu-id="b4061-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="b4061-208">Simulieren einer Antwort auf einen Endpunkt, der entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="b4061-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="b4061-209">Bereitstellen einer statischen Antwort auf einen bekannten Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b4061-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="b4061-210">Halten Sie einen API-Endpunkt konsistent, während das Back-End verschoben oder migriert wird.</span><span class="sxs-lookup"><span data-stu-id="b4061-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="b4061-211">Proxys werden als JSON-Definitionen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b4061-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="b4061-212">Im Folgenden ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b4061-212">Here is an example:</span></span>

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

<span data-ttu-id="b4061-213">Der `Domain Redirect` Proxy nimmt eine verkürzte Route an und ordnet Sie der längeren Funktions Ressource zu.</span><span class="sxs-lookup"><span data-stu-id="b4061-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="b4061-214">Die Transformation sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b4061-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="b4061-215">Der `Root` Proxy übernimmt alle Elemente, die an die Stamm`https://--shorturl--/`-URL () gesendet werden, und leitet Sie an die Dokumentations Website um.</span><span class="sxs-lookup"><span data-stu-id="b4061-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="b4061-216">Ein Beispiel für die Verwendung von Proxys finden [Sie im Video Azure: Bringen Sie Ihre APP mit Server losem Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)in die Cloud.</span><span class="sxs-lookup"><span data-stu-id="b4061-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="b4061-217">In Echtzeit wird eine ASP.net Core Anwendung, die auf dem lokalen SQL Server ausgeführt wird, in die Azure-Cloud migriert.</span><span class="sxs-lookup"><span data-stu-id="b4061-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="b4061-218">Proxys dienen zum Umgestalten eines herkömmlichen Web-API-Projekts für die Verwendung von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4061-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="b4061-219">Weitere Informationen zu Proxys finden Sie unter [Arbeiten mit Azure-Funktionsproxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="b4061-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b4061-220">[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b4061-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
