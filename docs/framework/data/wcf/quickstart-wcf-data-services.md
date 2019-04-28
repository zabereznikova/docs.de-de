---
title: Schnellstart (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f20ffcf356aa0493b1e2356746d9ad7b27d9a1aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876199"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="74384-102">Schnellstart (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="74384-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="74384-103">Dieser Schnellstart hilft Ihnen mit WCF Data Services vertraut machen und die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] durch eine Reihe von Aufgaben, die in die Themen unterstützen [Einstieg](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="74384-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="74384-104">Sie lernen Folgendes</span><span class="sxs-lookup"><span data-stu-id="74384-104">What you'll learn</span></span>

<span data-ttu-id="74384-105">Die erste Aufgabe in diesem Schnellstart veranschaulicht das Erstellen eines Datendiensts, um einen OData-feed aus der Northwind-Beispieldatenbank verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="74384-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="74384-106">In späteren Themen greifen auf den-OData-feed mit einem Webbrowser, und Sie erstellen eine Windows Presentation Foundation (WPF)-Clientanwendung, die die OData verwendet Feeds mit Clientbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="74384-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74384-107">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="74384-107">Prerequisites</span></span>

<span data-ttu-id="74384-108">Um diesen Schnellstart durchzuführen, müssen Sie die folgenden Komponenten installieren:</span><span class="sxs-lookup"><span data-stu-id="74384-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="74384-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74384-109">Visual Studio</span></span>

- <span data-ttu-id="74384-110">Eine Instanz von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74384-110">An instance of SQL Server.</span></span> <span data-ttu-id="74384-111">Dies schließt SQL Server Express in einer Standardinstallation von Visual Studio 2015 oder als Teil von aufzunehmen ist die **datenspeicherung und-Verarbeitung** arbeitsauslastung in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="74384-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="74384-112">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="74384-112">The Northwind sample database.</span></span> <span data-ttu-id="74384-113">Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="74384-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="74384-114">WCF Data services-Schnellstart-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="74384-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="74384-115">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="74384-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="74384-116">Definieren Sie die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung, definieren Sie das Datenmodell, erstellen Sie den Datendienst, und aktivieren Sie den Zugriff auf Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="74384-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="74384-117">Auf den Dienst über einen Webbrowser zugreifen.</span><span class="sxs-lookup"><span data-stu-id="74384-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="74384-118">Starten Sie den Dienst aus Visual Studio, und greifen Sie auf den Dienst zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an den verfügbar gemachten Feed senden.</span><span class="sxs-lookup"><span data-stu-id="74384-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="74384-119">Erstellen der .NET Framework-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="74384-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="74384-120">Erstellen einer WPF-app für den OData-Feed zu nutzen, binden Daten an Windows-Steuerelemente, Ändern von Daten in den gebundenen Steuerelementen, und senden Sie, dass die Änderungen an den Datendienst zurück.</span><span class="sxs-lookup"><span data-stu-id="74384-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="74384-121">Projektdateien einer abgeschlossenen Version des Schnellstarts können von der Seite [WCF Data Services Quickstart (OData Service and WPF Client)](https://go.microsoft.com/fwlink/?LinkId=179994) (WCF Data Services-Schnellstart (OData-Dienst und WPF-Client)) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="74384-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74384-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="74384-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="74384-123">Starten des Schnellstarts</span><span class="sxs-lookup"><span data-stu-id="74384-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="74384-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74384-124">See also</span></span>

- [<span data-ttu-id="74384-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="74384-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
