---
title: Microsoft WCF Web Service Reference Provider-Tool
description: "Übersicht zum Microsoft WCF Web Service Reference Provider-Tool, über das Funktionen für .NET Core- und ASP.NET Core-Projekte hinzugefügt werden, z.B. das Hinzufügen von Dienstverweisen für .NET Framework-Projekte."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: e445361f9f4a858f4b34ca1008670fadc62b8b3c
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2018
---
# <a name="microsoft-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="dd091-103">Microsoft WCF Web Service Reference Provider-Tool</span><span class="sxs-lookup"><span data-stu-id="dd091-103">Microsoft WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="dd091-104">Im Laufe der Jahre konnten viele Visual Studio-Entwickler von dem [**Dienstverweis hinzufügen**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)-Tool profitieren und ihre Produktivität steigern, wenn sie für ihre .NET Framework-Projekte Zugriff auf Webdienste benötigten.</span><span class="sxs-lookup"><span data-stu-id="dd091-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="dd091-105">Bei dem **WCF Web Service Reference**-Tool handelt es sich um eine mit Visual Studio verknüpfte Diensterweiterung, die Funktionen wie „Dienstverweis hinzufügen“ für .NET Core und ASP.NET Core-Projekte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dd091-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="dd091-106">Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe, von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei. Diese enthält den Proxycode des WCF-Clients (Windows Communication Foundation), den Sie verwenden können, um auf einen Webdienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd091-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd091-107">Sie sollten nur auf Dienste aus einer vertrauenswürdigen Quelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="dd091-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="dd091-108">Wenn Sie Verweise aus nicht vertrauenswürdigen Quellen hinzufügen, hat das möglicherweise Auswirkungen auf die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="dd091-108">Adding references from an untrusted source may compromise security.</span></span> 

## <a name="how-to-use-the-extension"></a><span data-ttu-id="dd091-109">Verwenden der Erweiterung</span><span class="sxs-lookup"><span data-stu-id="dd091-109">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="dd091-110">Die Option **WCF Web Service Reference** ist auf Projekte anwendbar, die über eine der folgenden Projektvorlagen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="dd091-110">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
> * <span data-ttu-id="dd091-111">**Visual C#** > **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="dd091-111">**Visual C#** > **.NET Core**</span></span>
> * <span data-ttu-id="dd091-112">**Visual C#** > **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="dd091-112">**Visual C#** > **.NET Standard**</span></span>
> * <span data-ttu-id="dd091-113">**Visual C#** > **Web** > **ASP.NET Core-Webanwendung**</span><span class="sxs-lookup"><span data-stu-id="dd091-113">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="dd091-114">In diesem Artikel wird die Projektvorlage **ASP.NET Core-Webanwendung** als Beispiel genommen, um Ihnen exemplarisch zu erläutern, wie Sie einem Projekt einen WCF-Dienstverweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="dd091-114">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="dd091-115">Doppelklicken Sie im Projektmappen-Explorer auf den Knoten **Verbundene Dienste** des Projekts. Bei .NET Core- oder .NET Standard-Projekten finden Sie diese Option, wenn Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des Projekts klicken.</span><span class="sxs-lookup"><span data-stu-id="dd091-115">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

<span data-ttu-id="dd091-116">Die Seite **Verbundene Dienste** wird wie in der folgenden Abbildung dargestellt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd091-116">The **Connected Services** page appears as shown in the following image:</span></span>

![Registerkarte „Verbundene Dienste“](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="dd091-118">Klicken Sie auf der Seite **Verbundene Dienste** auf **Microsoft WCF Web Service Reference Provider**.</span><span class="sxs-lookup"><span data-stu-id="dd091-118">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="dd091-119">Dann wird der Assistent **zum Konfigurieren von WCF-Webdienstverweisen** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd091-119">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

![Registerkarte „Dienstendpunkt“](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="dd091-121">Wählen Sie einen Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="dd091-121">Select a service.</span></span>

    <span data-ttu-id="dd091-122">3a.</span><span class="sxs-lookup"><span data-stu-id="dd091-122">3a.</span></span> <span data-ttu-id="dd091-123">Es sind einige Suchoptionen für den Dienst im Assistenten zum **Konfigurieren von WCF-Webdienstverweisen** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="dd091-123">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>
    
     * <span data-ttu-id="dd091-124">Klicken Sie auf die Schaltfläche **Ermitteln**, um nach Diensten zu suchen, die in der aktuellen Projektmappe definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dd091-124">To search for services defined in the current solution, click the **Discover** button.</span></span> 
     * <span data-ttu-id="dd091-125">Geben Sie eine Dienst-URL im Feld **Adresse** ein, und klicken Sie auf die Schaltfläche **Gehe zu**, um nach Diensten zu suchen, die an einer bestimmten Adresse gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="dd091-125">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="dd091-126">Klicken Sie auf die Schaltfläche **Durchsuchen**, um eine WSDL-Datei auszuwählen, die die Metadateninformationen des Webdiensts enthält.</span><span class="sxs-lookup"><span data-stu-id="dd091-126">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span> 
     
    <span data-ttu-id="dd091-127">3b.</span><span class="sxs-lookup"><span data-stu-id="dd091-127">3b.</span></span> <span data-ttu-id="dd091-128">Wählen Sie den Dienst aus der Liste der Suchergebnisse im Feld **Dienste** aus.</span><span class="sxs-lookup"><span data-stu-id="dd091-128">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="dd091-129">Geben Sie ggf. den Namespace für den generierten Code im entsprechenden Textfeld **Namespace** ein.</span><span class="sxs-lookup"><span data-stu-id="dd091-129">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>
    
    <span data-ttu-id="dd091-130">3c.</span><span class="sxs-lookup"><span data-stu-id="dd091-130">3c.</span></span> <span data-ttu-id="dd091-131">Klicken Sie auf die Schaltfläche **Weiter**, um die **Datentypoptionen** und die Seiten **Clientoptionen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd091-131">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="dd091-132">Sie können stattdessen auch auf die Schaltfläche **Fertig stellen** klicken, um die Standardoptionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd091-132">Alternatively, click the **Finish** button to use the default options.</span></span>


4. <span data-ttu-id="dd091-133">Mithilfe des Formulars **Datentypoptionen** können Sie die generierten Einstellungen für die Dienstverweise einschränken:</span><span class="sxs-lookup"><span data-stu-id="dd091-133">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

![Registerkarte „Datentypoptionen“](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

> [!NOTE]
> <span data-ttu-id="dd091-135">Die Kontrollkästchenoption **Typen in Assemblys, auf die verwiesen wird, wiederverwenden** ist nützlich, wenn Datentypen, die für die Codegenerierung für Dienstverweise benötigt werden, in einer der Assemblys definiert werden, auf die Ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="dd091-135">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="dd091-136">Es ist wichtig, dass Sie die vorhandenen Datentypen wiederverwenden, um Typkollisionen oder Probleme mit der Runtime zur Kompilierzeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="dd091-136">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

<span data-ttu-id="dd091-137">Es kann zu Verzögerungen kommen, während die Typinformationen geladen werden. Dies ist von der Anzahl von Projektabhängigkeiten und anderen die Systemleistung betreffenden Faktoren abhängig.</span><span class="sxs-lookup"><span data-stu-id="dd091-137">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="dd091-138">Die Schaltfläche **Fertig stellen** wird beim Laden deaktiviert. Dies ist nicht der Fall, wenn das Kontrollkästchen **Typen in Assemblys, auf die verwiesen wird, wiederverwenden** deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dd091-138">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="dd091-139">Klicken Sie auf **Fertig stellen**, wenn Sie so weit sind.</span><span class="sxs-lookup"><span data-stu-id="dd091-139">Click **Finish** when you are done.</span></span>


<span data-ttu-id="dd091-140">Das Tool führt folgende Schritte aus, während es den Fortschritt anzeigt:</span><span class="sxs-lookup"><span data-stu-id="dd091-140">While displaying progress, the tool:</span></span>

* <span data-ttu-id="dd091-141">Metadaten werden von dem WCF-Dienst heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="dd091-141">Downloads metadata from the WCF service.</span></span> 
* <span data-ttu-id="dd091-142">Der Dienstverweiscode in einer Datei mit dem Namen *reference.cs* wird generiert und Ihrem Projekt unter dem Knoten **Verbundene Dienste** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dd091-142">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span> 
* <span data-ttu-id="dd091-143">Aktualisiert die Projektdatei (.csproj) mit NuGet-Paketverweisen, die erforderlich sind, damit diese Datei auf der Zielplattform kompiliert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd091-143">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![Statusfenster](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="dd091-145">Nachdem die Prozesse abgeschlossen sind, können Sie eine Instanz des generierten WCF-Clienttyps generieren und die Dienstvorgänge ausrufen.</span><span class="sxs-lookup"><span data-stu-id="dd091-145">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd091-146">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dd091-146">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="dd091-147">Feedback und Fragen</span><span class="sxs-lookup"><span data-stu-id="dd091-147">Feedback & questions</span></span>
<span data-ttu-id="dd091-148">Wenn Sie Fragen haben oder uns Feedback geben möchten, [öffnen Sie ein Problem auf GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="dd091-148">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="dd091-149">Sie können außerdem bereits vorhandene Fragen oder Probleme [im WCF-Repository auf GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dd091-149">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="dd091-150">Anmerkungen zu diesem Release</span><span class="sxs-lookup"><span data-stu-id="dd091-150">Release notes</span></span>
* <span data-ttu-id="dd091-151">Aktualisierte Informationen zu den einzelnen Versionen, einschließlich bekannter Probleme, finden Sie in den [Anmerkungen zu den jeweiligen Versionen](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md).</span><span class="sxs-lookup"><span data-stu-id="dd091-151">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span> 
