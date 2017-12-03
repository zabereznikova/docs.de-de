---
title: Schnellstart (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08296be1002ee50e18a45c546645f4cc117d6bb5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="4ad5c-102">Schnellstart (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="4ad5c-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="4ad5c-103">Dieser Schnellstart hilft dabei, sich mit vertraut [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] und [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] durch eine Reihe von Aufgaben, die in die Themen unterstützen [Einstieg](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ad5c-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="4ad5c-104">Lernziele</span><span class="sxs-lookup"><span data-stu-id="4ad5c-104">What You Will Learn</span></span>  
 <span data-ttu-id="4ad5c-105">Die erste Aufgabe in diesem Schnellstart zeigt das Erstellen eines Datendiensts, um einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed aus der Northwind-Beispieldatenbank verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="4ad5c-106">In späteren Themen greifen Sie mit einem Webbrowser auf den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed zu, und Sie erstellen eine [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] -Clientanwendung, die den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed mithilfe von Clientbibliotheken nutzt.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ad5c-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4ad5c-107">Prerequisites</span></span>  
 <span data-ttu-id="4ad5c-108">Um diesen Schnellstart durchzuführen, müssen Sie die folgenden Komponenten installieren:</span><span class="sxs-lookup"><span data-stu-id="4ad5c-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="4ad5c-109">.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-109">.</span></span>  
  
-   <span data-ttu-id="4ad5c-110">Eine Instanz von [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ad5c-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ad5c-111">Dies beinhaltet das in einer Standardinstallation von [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]enthaltene SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="4ad5c-112">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-112">The Northwind sample database.</span></span> <span data-ttu-id="4ad5c-113">Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](http://go.microsoft.com/fwlink/?linkid=24758)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="4ad5c-114">Aufgaben beim WCF Data Services-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="4ad5c-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="4ad5c-115">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="4ad5c-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="4ad5c-116">Definieren Sie die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung, definieren Sie das Datenmodell, erstellen Sie den Datendienst, und aktivieren Sie den Zugriff auf Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="4ad5c-117">Zugriff auf den Dienst über einen Webbrowser</span><span class="sxs-lookup"><span data-stu-id="4ad5c-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="4ad5c-118">Starten Sie den Dienst in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] , und greifen Sie auf den Dienst zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an den verfügbar gemachten Feed senden.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="4ad5c-119">Erstellen der .NET Framework-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="4ad5c-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="4ad5c-120">Erstellen Sie eine [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] -Clientanwendung, um den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed zu nutzen, binden Sie Daten an Windows-Steuerelemente, ändern Sie Daten in den gebundenen Steuerelementen, und senden Sie die Änderungen dann an den Datendienst zurück.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ad5c-121">Projektdateien einer abgeschlossenen Version des Schnellstarts können von der Seite [WCF Data Services Quickstart (OData Service and WPF Client)](http://go.microsoft.com/fwlink/?LinkId=179994) (WCF Data Services-Schnellstart (OData-Dienst und WPF-Client)) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4ad5c-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4ad5c-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4ad5c-122">Next Steps</span></span>  
 <span data-ttu-id="4ad5c-123">[Starten des Schnellstarts](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="4ad5c-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad5c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ad5c-124">See Also</span></span>  
 [<span data-ttu-id="4ad5c-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4ad5c-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
