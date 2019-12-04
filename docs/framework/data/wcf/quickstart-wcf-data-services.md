---
title: Schnellstart (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: df3151dfd3628231d84d2d128c61d1c0b6b0d48e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800352"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="5130e-102">Schnellstart (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="5130e-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="5130e-103">Dieser Schnellstart hilft Ihnen, sich mit WCF Data Services und der Open Data Protocol (odata) durch eine Reihe von Aufgaben vertraut zu machen, die die [Themen in den](getting-started-with-wcf-data-services.md)ersten Schritten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5130e-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="5130e-104">Ihre Lernziele</span><span class="sxs-lookup"><span data-stu-id="5130e-104">What you'll learn</span></span>

<span data-ttu-id="5130e-105">Die erste Aufgabe in diesem Schnellstart zeigt, wie Sie einen Datendienst erstellen, um einen odata-Feed aus der Northwind-Beispieldatenbank verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="5130e-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="5130e-106">In späteren Themen greifen Sie mithilfe eines Webbrowsers auf den odata-Feed zu und erstellen eine Windows Presentation Foundation (WPF)-Client Anwendung, die den odata-Feed mithilfe von Client Bibliotheken nutzt.</span><span class="sxs-lookup"><span data-stu-id="5130e-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5130e-107">Erforderliche Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5130e-107">Prerequisites</span></span>

<span data-ttu-id="5130e-108">Um diesen Schnellstart durchzuführen, müssen Sie die folgenden Komponenten installieren:</span><span class="sxs-lookup"><span data-stu-id="5130e-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="5130e-109">öffnen</span><span class="sxs-lookup"><span data-stu-id="5130e-109">Visual Studio</span></span>

- <span data-ttu-id="5130e-110">Eine Instanz von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5130e-110">An instance of SQL Server.</span></span> <span data-ttu-id="5130e-111">Dies umfasst SQL Server Express, das in einer Standardinstallation von Visual Studio 2015 enthalten ist, oder als Teil der Arbeitsauslastung für die **Datenspeicherung und-Verarbeitung** in Visual Studio 2017 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5130e-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="5130e-112">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="5130e-112">The Northwind sample database.</span></span> <span data-ttu-id="5130e-113">Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="5130e-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="5130e-114">WCF Data Services-Schnellstart Aufgaben</span><span class="sxs-lookup"><span data-stu-id="5130e-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="5130e-115">Erstellen des Daten Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="5130e-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="5130e-116">Definieren Sie die ASP.NET-Anwendung, definieren Sie das Datenmodell, erstellen Sie den Datendienst und aktivieren Sie den Zugriff auf Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="5130e-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="5130e-117">Zugreifen auf den Dienst über einen Webbrowser</span><span class="sxs-lookup"><span data-stu-id="5130e-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="5130e-118">Starten Sie den Dienst aus Visual Studio, und greifen Sie auf den Dienst zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an den verfügbar gemachten Feed senden.</span><span class="sxs-lookup"><span data-stu-id="5130e-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="5130e-119">Erstellen der .NET Framework Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="5130e-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="5130e-120">Erstellen Sie eine WPF-App, um den odata-Feed zu nutzen, binden Sie Daten an Windows-Steuerelemente, ändern Sie Daten in den gebundenen Steuerelementen, und senden Sie die Änderungen dann an den Datendienst zurück.</span><span class="sxs-lookup"><span data-stu-id="5130e-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="5130e-121">Projektdateien einer abgeschlossenen Version des Schnellstarts können von der Seite [WCF Data Services Quickstart (OData Service and WPF Client)](https://go.microsoft.com/fwlink/?LinkId=179994) (WCF Data Services-Schnellstart (OData-Dienst und WPF-Client)) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="5130e-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5130e-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5130e-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5130e-123">Starten des Schnellstarts</span><span class="sxs-lookup"><span data-stu-id="5130e-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="5130e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5130e-124">See also</span></span>

- [<span data-ttu-id="5130e-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="5130e-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
