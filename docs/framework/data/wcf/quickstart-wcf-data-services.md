---
title: Schnellstart (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121226"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="610a3-102">Schnellstart (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="610a3-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="610a3-103">Diese Schnellstartanleitung hilft Ihnen, sich mit WCF Data Services und dem Open Data Protocol (OData) durch eine Reihe von Aufgaben vertraut zu machen, die die Themen unter [Erste Schritte](getting-started-with-wcf-data-services.md)unterstützen.</span><span class="sxs-lookup"><span data-stu-id="610a3-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="610a3-104">Sie lernen Folgendes</span><span class="sxs-lookup"><span data-stu-id="610a3-104">What you'll learn</span></span>

<span data-ttu-id="610a3-105">Die erste Aufgabe in dieser Schnellstartanleitung zeigt, wie Sie einen Datendienst erstellen, um einen OData-Feed aus der Northwind-Beispieldatenbank verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="610a3-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="610a3-106">In späteren Themen greifen Sie über einen Webbrowser auf den OData-Feed zu und erstellen außerdem eine Windows Presentation Foundation (WPF)-Clientanwendung, die den OData-Feed mithilfe von Clientbibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="610a3-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="610a3-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="610a3-107">Prerequisites</span></span>

<span data-ttu-id="610a3-108">Um diese Schnellstartanleitung abzuschließen, installieren Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="610a3-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="610a3-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="610a3-109">Visual Studio</span></span>

- <span data-ttu-id="610a3-110">Eine Instanz von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="610a3-110">An instance of SQL Server.</span></span> <span data-ttu-id="610a3-111">Dies schließt SQL Server Express ein, das in einer Standardinstallation von Visual Studio 2015 oder als Teil der **Datenspeicherung und Verarbeitungsworkload** in Visual Studio 2017 oder höher enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="610a3-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="610a3-112">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="610a3-112">The Northwind sample database.</span></span> <span data-ttu-id="610a3-113">Um die Datenbank zu installieren, führen Sie das Transact-SQL-Skript von [Northwind und pubs Beispieldatenbanken für Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)aus.</span><span class="sxs-lookup"><span data-stu-id="610a3-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="610a3-114">WCF-Datendienste-Schnellstartaufgaben</span><span class="sxs-lookup"><span data-stu-id="610a3-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="610a3-115">Erstellen des Datendienstes</span><span class="sxs-lookup"><span data-stu-id="610a3-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="610a3-116">Definieren Sie die ASP.NET-Anwendung, definieren Sie das Datenmodell, erstellen Sie den Datendienst und aktivieren Sie den Zugriff auf Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="610a3-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="610a3-117">Zugriff auf den Dienst über einen Webbrowser</span><span class="sxs-lookup"><span data-stu-id="610a3-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="610a3-118">Starten Sie den Dienst aus Visual Studio, und greifen Sie auf den Dienst zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an den verfügbar gemachten Feed senden.</span><span class="sxs-lookup"><span data-stu-id="610a3-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="610a3-119">Erstellen der .NET Framework Client-Anwendung</span><span class="sxs-lookup"><span data-stu-id="610a3-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="610a3-120">Erstellen Sie eine WPF-App, um den OData-Feed zu nutzen, Daten an Windows-Steuerelemente zu binden, Daten in den gebundenen Steuerelementen zu ändern und die Änderungen dann an den Datendienst zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="610a3-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="610a3-121">Projektdateien aus einer fertigen Version des Schnellstarts können von [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="610a3-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="610a3-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="610a3-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="610a3-123">Starten Sie den Schnellstart</span><span class="sxs-lookup"><span data-stu-id="610a3-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="610a3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610a3-124">See also</span></span>

- [<span data-ttu-id="610a3-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="610a3-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
