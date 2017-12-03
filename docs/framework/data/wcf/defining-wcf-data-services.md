---
title: Definieren von WCF Data Services
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e66c26c12f3f62ee61e02e16318e747793ff927
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="77ee7-102">Definieren von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="77ee7-102">Defining WCF Data Services</span></span>
<span data-ttu-id="77ee7-103">In diesem Abschnitt wird beschrieben, wie zum Erstellen und konfigurieren [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] zum Verfügbarmachen von Daten als ein [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span><span class="sxs-lookup"><span data-stu-id="77ee7-103">This section describes how to create and configure [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="77ee7-104">die grundlegenden Schritte zum Erstellen eines Datendiensts finden Sie unter [Verfügbarmachen von Daten als Dienst](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="77ee7-104"> the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77ee7-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="77ee7-105">In This Section</span></span>  
 [<span data-ttu-id="77ee7-106">Konfigurieren des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="77ee7-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="77ee7-107">Beschreibt die in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbaren Konfigurationsoptionen für Datendienste.</span><span class="sxs-lookup"><span data-stu-id="77ee7-107">Describes the data service configuration options provided by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="77ee7-108">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="77ee7-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 <span data-ttu-id="77ee7-109">Beschreibt die Anbietermodelle zum Verfügbarmachen von Daten als Datendienst.</span><span class="sxs-lookup"><span data-stu-id="77ee7-109">Describes the provider models for exposing data as a data service.</span></span>  
  
 [<span data-ttu-id="77ee7-110">Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="77ee7-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)  
 <span data-ttu-id="77ee7-111">Beschreibt, wie Dienstvorgänge definiert werden, die Methoden auf dem Server verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="77ee7-111">Describes how to define service operations that expose methods on the server.</span></span>  
  
 [<span data-ttu-id="77ee7-112">Anpassung von Feeds</span><span class="sxs-lookup"><span data-stu-id="77ee7-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)  
 <span data-ttu-id="77ee7-113">Beschreibt das Erstellen einer Zuordnung zwischen Entitäten im Datenmodell, das vom Datendienstanbieter definiert wird, und den Elementen im Datenfeed.</span><span class="sxs-lookup"><span data-stu-id="77ee7-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>  
  
 [<span data-ttu-id="77ee7-114">Interceptors</span><span class="sxs-lookup"><span data-stu-id="77ee7-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)  
 <span data-ttu-id="77ee7-115">Beschreibt, wie Interceptormethoden definiert werden, um benutzerdefinierte Geschäftslogik für Anforderungen an den Datendienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="77ee7-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>  
  
 [<span data-ttu-id="77ee7-116">Entwickeln und Bereitstellen von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="77ee7-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 <span data-ttu-id="77ee7-117">Beschreibt, wie ein Datendienst mithilfe von Visual Studio entwickelt und bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="77ee7-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>  
  
 [<span data-ttu-id="77ee7-118">Sichern von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="77ee7-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 <span data-ttu-id="77ee7-119">Beschreibt die Authentifizierung und Autorisierung für den Datendienst sowie weitere Sicherheitsüberlegungen.</span><span class="sxs-lookup"><span data-stu-id="77ee7-119">Describes authentication and authorization for the data service and other security considerations.</span></span>  
  
 [<span data-ttu-id="77ee7-120">Hosting des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="77ee7-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="77ee7-121">Beschreibt, wie ein Host für den Datendienst ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="77ee7-121">Describes how to select a host for your data service.</span></span>  
  
 [<span data-ttu-id="77ee7-122">Datendienst-Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="77ee7-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)  
 <span data-ttu-id="77ee7-123">Beschreibt die Verwendung unterschiedlicher Versionen von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77ee7-123">Describes how to work with different versions of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span>  
  
 [<span data-ttu-id="77ee7-124">WCF Data Services-Protokoll-Implementierungsdetails</span><span class="sxs-lookup"><span data-stu-id="77ee7-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)  
 <span data-ttu-id="77ee7-125">Beschreibt optionale Funktionen des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokolls, die aktuell nicht von WCF Data Services implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="77ee7-125">Describes optional functionalities of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol that are not currently implemented by WCF Data Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ee7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77ee7-126">See Also</span></span>  
 [<span data-ttu-id="77ee7-127">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="77ee7-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="77ee7-128">Zugreifen auf Datendienstressourcen</span><span class="sxs-lookup"><span data-stu-id="77ee7-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [<span data-ttu-id="77ee7-129">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="77ee7-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
