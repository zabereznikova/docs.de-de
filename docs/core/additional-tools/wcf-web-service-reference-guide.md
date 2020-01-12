---
title: Hinzufügen von WCF Web Service Reference
description: Übersicht zum Microsoft WCF Web Service Reference Provider-Tool, über das Funktionen für .NET Core- und ASP.NET Core-Projekte hinzugefügt werden, z.B. das Hinzufügen von Dienstverweisen für .NET Framework-Projekte.
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc
ms.openlocfilehash: cdd6b457d289dd7b752c97c5645f0797f24b72aa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715682"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="cbd3c-103">Verwenden des Provider-Tools für den WCF-Webdienstverweis</span><span class="sxs-lookup"><span data-stu-id="cbd3c-103">Use the WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="cbd3c-104">Im Laufe der Jahre konnten viele Visual Studio-Entwickler von dem [**Dienstverweis hinzufügen**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)-Tool profitieren und ihre Produktivität steigern, wenn sie für ihre .NET Framework-Projekte Zugriff auf Webdienste benötigten.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="cbd3c-105">Bei dem **WCF Web Service Reference**-Tool handelt es sich um eine mit Visual Studio verknüpfte Diensterweiterung, die Funktionen wie „Dienstverweis hinzufügen“ für .NET Core und ASP.NET Core-Projekte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="cbd3c-106">Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe, von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei. Diese enthält den Proxycode des WCF-Clients (Windows Communication Foundation), den Sie verwenden können, um auf einen Webdienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbd3c-107">Sie sollten nur auf Dienste aus einer vertrauenswürdigen Quelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="cbd3c-108">Wenn Sie Verweise aus nicht vertrauenswürdigen Quellen hinzufügen, hat das möglicherweise Auswirkungen auf die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-108">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cbd3c-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cbd3c-109">Prerequisites</span></span>

- <span data-ttu-id="cbd3c-110">[Visual Studio 2017, Version 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) oder höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="cbd3c-110">[Visual Studio 2017 version 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) or later versions</span></span>

## <a name="how-to-use-the-extension"></a><span data-ttu-id="cbd3c-111">Verwenden der Erweiterung</span><span class="sxs-lookup"><span data-stu-id="cbd3c-111">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="cbd3c-112">Die Option **WCF Web Service Reference** ist auf Projekte anwendbar, die über eine der folgenden Projektvorlagen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-112">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
>
> - <span data-ttu-id="cbd3c-113">**Visual C#**  >  **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="cbd3c-113">**Visual C#** > **.NET Core**</span></span>
> - <span data-ttu-id="cbd3c-114">**Visual C#**  >  **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="cbd3c-114">**Visual C#** > **.NET Standard**</span></span>
> - <span data-ttu-id="cbd3c-115">**Visual C#**  > **Web** > **ASP.NET Core-Webanwendung**</span><span class="sxs-lookup"><span data-stu-id="cbd3c-115">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="cbd3c-116">In diesem Artikel wird die Projektvorlage **ASP.NET Core-Webanwendung** als Beispiel genommen, um Ihnen exemplarisch zu erläutern, wie Sie einem Projekt einen WCF-Dienstverweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-116">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="cbd3c-117">Doppelklicken Sie im Projektmappen-Explorer auf den Knoten **Verbundene Dienste** des Projekts. Bei .NET Core- oder .NET Standard-Projekten finden Sie diese Option, wenn Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des Projekts klicken.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-117">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

    <span data-ttu-id="cbd3c-118">Die Seite **Verbundene Dienste** wird wie in der folgenden Abbildung dargestellt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-118">The **Connected Services** page appears as shown in the following image:</span></span>

    ![Registerkarte „Verbundene Dienste in Visual Studio“ für .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="cbd3c-120">Klicken Sie auf der Seite **Verbundene Dienste** auf **Microsoft WCF Web Service Reference Provider**.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-120">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="cbd3c-121">Dann wird der Assistent **zum Konfigurieren von WCF-Webdienstverweisen** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-121">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

    ![Registerkarte „Dienstendpunkt in Visual Studio“ für .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="cbd3c-123">Wählen Sie einen Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-123">Select a service.</span></span>

    <span data-ttu-id="cbd3c-124">3a.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-124">3a.</span></span> <span data-ttu-id="cbd3c-125">Es sind einige Suchoptionen für den Dienst im Assistenten zum **Konfigurieren von WCF-Webdienstverweisen** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-125">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>

     * <span data-ttu-id="cbd3c-126">Klicken Sie auf die Schaltfläche **Ermitteln**, um nach Diensten zu suchen, die in der aktuellen Projektmappe definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-126">To search for services defined in the current solution, click the **Discover** button.</span></span>
     * <span data-ttu-id="cbd3c-127">Geben Sie eine Dienst-URL im Feld **Adresse** ein, und klicken Sie auf die Schaltfläche **Gehe zu**, um nach Diensten zu suchen, die an einer bestimmten Adresse gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-127">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="cbd3c-128">Klicken Sie auf die Schaltfläche **Durchsuchen**, um eine WSDL-Datei auszuwählen, die die Metadateninformationen des Webdiensts enthält.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-128">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span>

    <span data-ttu-id="cbd3c-129">3b.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-129">3b.</span></span> <span data-ttu-id="cbd3c-130">Wählen Sie den Dienst aus der Liste der Suchergebnisse im Feld **Dienste** aus.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-130">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="cbd3c-131">Geben Sie ggf. den Namespace für den generierten Code im entsprechenden Textfeld **Namespace** ein.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-131">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>

    <span data-ttu-id="cbd3c-132">3c.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-132">3c.</span></span> <span data-ttu-id="cbd3c-133">Klicken Sie auf die Schaltfläche **Weiter**, um die **Datentypoptionen** und die Seiten **Clientoptionen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-133">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="cbd3c-134">Sie können stattdessen auch auf die Schaltfläche **Fertig stellen** klicken, um die Standardoptionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-134">Alternatively, click the **Finish** button to use the default options.</span></span>

4. <span data-ttu-id="cbd3c-135">Mithilfe des Formulars **Datentypoptionen** können Sie die generierten Einstellungen für die Dienstverweise einschränken:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-135">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

    ![Registerkarte „Datentypoptionen in Visual Studio“ für .NET Core](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > <span data-ttu-id="cbd3c-137">Die Kontrollkästchenoption **Typen in Assemblys, auf die verwiesen wird, wiederverwenden** ist nützlich, wenn Datentypen, die für die Codegenerierung für Dienstverweise benötigt werden, in einer der Assemblys definiert werden, auf die Ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-137">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="cbd3c-138">Es ist wichtig, dass Sie die vorhandenen Datentypen wiederverwenden, um Typkollisionen oder Probleme mit der Runtime zur Kompilierzeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-138">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

    <span data-ttu-id="cbd3c-139">Es kann zu Verzögerungen kommen, während die Typinformationen geladen werden. Dies ist von der Anzahl von Projektabhängigkeiten und anderen die Systemleistung betreffenden Faktoren abhängig.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-139">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="cbd3c-140">Die Schaltfläche **Fertig stellen** wird beim Laden deaktiviert. Dies ist nicht der Fall, wenn das Kontrollkästchen **Typen in Assemblys, auf die verwiesen wird, wiederverwenden** deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-140">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="cbd3c-141">Klicken Sie auf **Fertig stellen**, wenn Sie so weit sind.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-141">Click **Finish** when you are done.</span></span>

<span data-ttu-id="cbd3c-142">Das Tool führt folgende Schritte aus, während es den Fortschritt anzeigt:</span><span class="sxs-lookup"><span data-stu-id="cbd3c-142">While displaying progress, the tool:</span></span>

- <span data-ttu-id="cbd3c-143">Metadaten werden von dem WCF-Dienst heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-143">Downloads metadata from the WCF service.</span></span>
- <span data-ttu-id="cbd3c-144">Der Dienstverweiscode in einer Datei mit dem Namen *reference.cs* wird generiert und Ihrem Projekt unter dem Knoten **Verbundene Dienste** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-144">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span>
- <span data-ttu-id="cbd3c-145">Aktualisiert die Projektdatei (.csproj) mit NuGet-Paketverweisen, die erforderlich sind, damit diese Datei auf der Zielplattform kompiliert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-145">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![Visual Studio-Fortschrittsfenster](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="cbd3c-147">Nachdem die Prozesse abgeschlossen sind, können Sie eine Instanz des generierten WCF-Clienttyps generieren und die Dienstvorgänge ausrufen.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-147">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbd3c-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbd3c-148">See also</span></span>

- [<span data-ttu-id="cbd3c-149">Erste Schritte mit Windows Communication Foundation-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="cbd3c-149">Get started with Windows Communication Foundation applications</span></span>](../../framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="cbd3c-150">Windows Communication Foundation-Dienste und WCF Data Services in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cbd3c-150">Windows Communication Foundation services and WCF data services in Visual Studio</span></span>](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [<span data-ttu-id="cbd3c-151">Von WCF unterstützte Features in .NET Core</span><span class="sxs-lookup"><span data-stu-id="cbd3c-151">WCF supported features on .NET Core</span></span>](https://github.com/dotnet/wcf/blob/master/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a><span data-ttu-id="cbd3c-152">Feedback und Fragen</span><span class="sxs-lookup"><span data-stu-id="cbd3c-152">Feedback & questions</span></span>

<span data-ttu-id="cbd3c-153">Wenn Sie Fragen haben oder uns Feedback geben möchten, können Sie dies über die [Entwicklercommunity](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) mithilfe des Tools [Problem melden](https://developercommunity.visualstudio.com/) tun.</span><span class="sxs-lookup"><span data-stu-id="cbd3c-153">If you have any questions or feedback, report it at [Developer Community](https://developercommunity.visualstudio.com/) using the [Report a problem](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) tool.</span></span>

## <a name="release-notes"></a><span data-ttu-id="cbd3c-154">Anmerkungen zu diesem Release</span><span class="sxs-lookup"><span data-stu-id="cbd3c-154">Release notes</span></span>

- <span data-ttu-id="cbd3c-155">Aktualisierte Informationen zu den einzelnen Versionen, einschließlich bekannter Probleme, finden Sie in den [Anmerkungen zu den jeweiligen Versionen](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md).</span><span class="sxs-lookup"><span data-stu-id="cbd3c-155">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span>
