---
title: WCF Data Services 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b6b9ddd27422c09f21833548634afd7945afa89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="30c56-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="30c56-102">WCF Data Services 4.5</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="30c56-103"> (früher als „ADO.NET Data Services“ bezeichnet) ist eine Komponente von .NET Framework, die Ihnen ermöglicht, Dienste zu erstellen, die mithilfe von [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Daten über das Internet oder Intranet mit der Semantik von [Representational State Transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="30c56-103"> (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="30c56-104"> macht Daten als durch URIs adressierbare Ressourcen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30c56-104"> exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="30c56-105">Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE.</span><span class="sxs-lookup"><span data-stu-id="30c56-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="30c56-106"> verwendet die Entitätsbeziehungskonventionen von [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md), um Ressourcen als Mengen von durch Zuordnungen verknüpften Entitäten verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="30c56-106"> uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="30c56-107"> verwendet das [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokoll zum Adressieren und Aktualisieren von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="30c56-107"> uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="30c56-108">Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt.</span><span class="sxs-lookup"><span data-stu-id="30c56-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="30c56-109"> ermöglicht das Anfordern von Daten und das Schreiben von Daten in Ressourcen mithilfe der folgenden bekannten Übertragungsformate: Atom, ein Satz von Standards zum Austauschen und Aktualisieren von Daten als XML, und JSON (JavaScript Object Notation), ein in AJAX-Anwendungen häufig verwendetes textbasiertes Datenaustauschformat.</span><span class="sxs-lookup"><span data-stu-id="30c56-109"> enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="30c56-110"> kann Daten, die aus verschiedenen Quellen stammen, als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="30c56-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="30c56-111">Visual Studio Tools vereinfachen das Erstellen eines [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Diensts mithilfe eines ADO.NET Entity Framework-Datenmodells.</span><span class="sxs-lookup"><span data-stu-id="30c56-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="30c56-112">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds können auch auf Grundlage von CLR-Klassen (Common Language Runtime) und sogar auf Grundlage von spät gebundenen oder nicht typisierten Daten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="30c56-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="30c56-113"> umfasst auch einen Satz Clientbibliotheken; eine Bibliothek für allgemeine .NET Framework-Clientanwendungen und eine andere speziell für Silverlight-basierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="30c56-113"> also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="30c56-114">Diese Clientbibliotheken stellen ein objektbasiertes Programmiermodell für den Zugriff auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds aus Umgebungen wie .NET Framework und Silverlight bereit.</span><span class="sxs-lookup"><span data-stu-id="30c56-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="30c56-115">Wo sollte ich beginnen?</span><span class="sxs-lookup"><span data-stu-id="30c56-115">Where Should I Start?</span></span>  
 <span data-ttu-id="30c56-116">Je nach Ihren Interessen sollten Sie zuerst mit einem der folgenden [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Themen beginnen.</span><span class="sxs-lookup"><span data-stu-id="30c56-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="30c56-117">Ich möchte direkt beginnen…</span><span class="sxs-lookup"><span data-stu-id="30c56-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="30c56-118">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="30c56-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-119">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="30c56-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-120">Silverlight-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="30c56-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="30c56-121">Silverlight-Schnellstart für Windows Phone-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="30c56-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="30c56-122">Ich möchte einige Codebeispiele anzeigen…</span><span class="sxs-lookup"><span data-stu-id="30c56-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="30c56-123">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="30c56-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-124">Vorgehensweise: Ausführen von Datendienstabfragen</span><span class="sxs-lookup"><span data-stu-id="30c56-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-125">Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente</span><span class="sxs-lookup"><span data-stu-id="30c56-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="30c56-126">Ich möchte mehr über [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] erfahren...</span><span class="sxs-lookup"><span data-stu-id="30c56-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="30c56-127">Whitepaper: Einführung in OData</span><span class="sxs-lookup"><span data-stu-id="30c56-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="30c56-128">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="30c56-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="30c56-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="30c56-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="30c56-130">OData: Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="30c56-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="30c56-131">Ich möchte Videos ansehen…</span><span class="sxs-lookup"><span data-stu-id="30c56-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="30c56-132">Einführung in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="30c56-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="30c56-133">WCF Data Services Developer-Videos</span><span class="sxs-lookup"><span data-stu-id="30c56-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="30c56-134">OData: Entwickler-Website</span><span class="sxs-lookup"><span data-stu-id="30c56-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="30c56-135">Ich möchte End-to-End-Beispiele anzeigen</span><span class="sxs-lookup"><span data-stu-id="30c56-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="30c56-136">WCF Data Services-Dokumentationsbeispiele auf MSDN Samples Gallery</span><span class="sxs-lookup"><span data-stu-id="30c56-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="30c56-137">Weitere WCF Data Services-Beispiele auf MSDN Samples Gallery</span><span class="sxs-lookup"><span data-stu-id="30c56-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="30c56-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="30c56-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="30c56-139">Wie erfolgt die Integration in Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="30c56-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="30c56-140">Generieren der Datendienst-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="30c56-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-141">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="30c56-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="30c56-142">Entity Framework-Anbieter</span><span class="sxs-lookup"><span data-stu-id="30c56-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="30c56-143">Für welche Aufgaben kann ich es verwenden?</span><span class="sxs-lookup"><span data-stu-id="30c56-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="30c56-144">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30c56-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="30c56-145">Whitepaper: Einführung in OData</span><span class="sxs-lookup"><span data-stu-id="30c56-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="30c56-146">Anwendungsszenarios</span><span class="sxs-lookup"><span data-stu-id="30c56-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="30c56-147">Ich möchte Silverlight verwenden…</span><span class="sxs-lookup"><span data-stu-id="30c56-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="30c56-148">Silverlight-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="30c56-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="30c56-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="30c56-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="30c56-150">Erste Schritte mit Silverlight</span><span class="sxs-lookup"><span data-stu-id="30c56-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="30c56-151">Ich möchte eine Windows Phone-Anwendung erstellen…</span><span class="sxs-lookup"><span data-stu-id="30c56-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="30c56-152">Silverlight-Schnellstart für Windows Phone-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="30c56-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="30c56-153">Open Data Protocol (OData) Client für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="30c56-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="30c56-154">Ich möchte LINQ verwenden…</span><span class="sxs-lookup"><span data-stu-id="30c56-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="30c56-155">Abfragen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="30c56-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-156">Überlegungen zu LINQ</span><span class="sxs-lookup"><span data-stu-id="30c56-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="30c56-157">Vorgehensweise: Ausführen von Datendienstabfragen</span><span class="sxs-lookup"><span data-stu-id="30c56-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="30c56-158">Ich benötige weitere Informationen…</span><span class="sxs-lookup"><span data-stu-id="30c56-158">I still need some more information…</span></span>  
 -   [<span data-ttu-id="30c56-159">WCF Data Services-Teamblog</span><span class="sxs-lookup"><span data-stu-id="30c56-159">WCF Data Services Team Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [<span data-ttu-id="30c56-160">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="30c56-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="30c56-161">WCF Data Services Developer Center</span><span class="sxs-lookup"><span data-stu-id="30c56-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="30c56-162">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="30c56-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="30c56-163">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="30c56-163">In This Section</span></span>  
 [<span data-ttu-id="30c56-164">Übersicht</span><span class="sxs-lookup"><span data-stu-id="30c56-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="30c56-165">Bietet eine Übersicht über die in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbaren Features und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="30c56-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="30c56-166">Neues in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="30c56-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/en-us/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="30c56-167">Beschreibt neue Funktionen in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] und Unterstützung für neue [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="30c56-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="30c56-168">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="30c56-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="30c56-169">Beschreibt das Verfügbarmachen und Verarbeiten von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds mithilfe von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30c56-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="30c56-170">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="30c56-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="30c56-171">Beschreibt das Erstellen und Konfigurieren eines Datendiensts, der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="30c56-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="30c56-172">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="30c56-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="30c56-173">Beschreibt, wie Sie mithilfe von Clientbibliotheken [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feeds aus einer .NET Framework-Clientanwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="30c56-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c56-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30c56-174">See Also</span></span>  
 [<span data-ttu-id="30c56-175">Representational State Transfer (REST)</span><span class="sxs-lookup"><span data-stu-id="30c56-175">Representational State Transfer (REST)</span></span>](http://go.microsoft.com/fwlink/?LinkId=113919)
