---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 9ece2fe051855d0fd39556f56a4343ead2c437bc
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288130"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="11d17-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="11d17-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="11d17-103">WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente von .NET Framework, mit der Sie zum Erstellen von Diensten, mit denen, die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Verfügbarmachen und Verarbeiten von Daten über das Internet oder Intranet mit der Semantik der [ Rest (Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="11d17-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="11d17-104">OData macht Daten als durch URIs adressierbare Ressourcen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11d17-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="11d17-105">Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE.</span><span class="sxs-lookup"><span data-stu-id="11d17-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="11d17-106">OData verwendet die entitätsbeziehungskonventionen von der [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="11d17-106">OData uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="11d17-107">WCF Data Services verwendet das OData-Protokoll zum Adressieren und Aktualisieren von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="11d17-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="11d17-108">Auf diese Weise können Sie diese Dienste von jedem Client aus zugreifen, die von OData unterstützt.</span><span class="sxs-lookup"><span data-stu-id="11d17-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="11d17-109">OData ermöglicht es Ihnen, anfordern und Schreiben von Daten in Ressourcen mithilfe der folgenden bekannten Übertragungsformate: Atom, ein Satz von Standards zum Austauschen und Aktualisieren von Daten als XML- und JavaScript Object Notation (JSON), eine textbasierte Datenaustauschformat umfassend in AJAX die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11d17-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>

<span data-ttu-id="11d17-110">WCF Data Services kann Daten, die aus verschiedenen Quellen stammen, als OData-feeds verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="11d17-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="11d17-111">Visual Studio-Tools erleichtern Ihnen die Erstellung einen OData-basierten Dienst mit einem ADO.NET Entity Framework-Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="11d17-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="11d17-112">Sie können auch den OData-Feeds auf Grundlage common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="11d17-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="11d17-113">WCF Data Services umfasst auch einen Satz von Clientbibliotheken, eine für allgemeine .NET Framework-Clientanwendungen und eine weitere speziell für Silverlight-basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="11d17-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="11d17-114">Beim Zugriff auf einen OData-Feeds aus Umgebungen wie .NET Framework und Silverlight stellen diese Clientbibliotheken ein objektbasiertes Programmiermodell bereit.</span><span class="sxs-lookup"><span data-stu-id="11d17-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="11d17-115">Wo sollte ich beginnen?</span><span class="sxs-lookup"><span data-stu-id="11d17-115">Where Should I Start?</span></span>

<span data-ttu-id="11d17-116">Je nach Ihren Interessen sollten Sie in der erste Schritte mit WCF Data Services in einem der folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="11d17-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="11d17-117">Ich möchte direkt beginnen…</span><span class="sxs-lookup"><span data-stu-id="11d17-117">I want to jump right in...</span></span>

-   [<span data-ttu-id="11d17-118">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="11d17-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [<span data-ttu-id="11d17-119">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="11d17-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

-   [<span data-ttu-id="11d17-120">Silverlight-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="11d17-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [<span data-ttu-id="11d17-121">Silverlight-Schnellstart für Windows Phone-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="11d17-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="11d17-122">Nur Code anzeigen...</span><span class="sxs-lookup"><span data-stu-id="11d17-122">Just show me some code...</span></span>

-   [<span data-ttu-id="11d17-123">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="11d17-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [<span data-ttu-id="11d17-124">Vorgehensweise: Ausführen von Datendienstabfragen</span><span class="sxs-lookup"><span data-stu-id="11d17-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

-   [<span data-ttu-id="11d17-125">Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente</span><span class="sxs-lookup"><span data-stu-id="11d17-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="11d17-126">Ich möchte mehr über OData erfahren...</span><span class="sxs-lookup"><span data-stu-id="11d17-126">I want to know more about OData...</span></span>

 -   [<span data-ttu-id="11d17-127">Whitepaper: Einführung in OData</span><span class="sxs-lookup"><span data-stu-id="11d17-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [<span data-ttu-id="11d17-128">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="11d17-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

-   [<span data-ttu-id="11d17-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="11d17-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

-   [<span data-ttu-id="11d17-130">OData: Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="11d17-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="11d17-131">Ich möchte Videos ansehen…...</span><span class="sxs-lookup"><span data-stu-id="11d17-131">I want to watch some videos...</span></span>

-   [<span data-ttu-id="11d17-132">Einführung in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="11d17-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

-   [<span data-ttu-id="11d17-133">WCF Data Services Developer-Videos</span><span class="sxs-lookup"><span data-stu-id="11d17-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

-   [<span data-ttu-id="11d17-134">OData: Entwickler-Website</span><span class="sxs-lookup"><span data-stu-id="11d17-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="11d17-135">Ich möchte End-to-End-Beispiele finden Sie unter...</span><span class="sxs-lookup"><span data-stu-id="11d17-135">I want to see end-to-end samples...</span></span>

-   [<span data-ttu-id="11d17-136">WCF Data Services-Dokumentationsbeispiele auf MSDN Samples Gallery</span><span class="sxs-lookup"><span data-stu-id="11d17-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

-   [<span data-ttu-id="11d17-137">Weitere WCF Data Services-Beispiele auf MSDN Samples Gallery</span><span class="sxs-lookup"><span data-stu-id="11d17-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

-   [<span data-ttu-id="11d17-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="11d17-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="11d17-139">Wie erfolgt die Integration in Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="11d17-139">How does it integrate with Visual Studio?</span></span>

-   [<span data-ttu-id="11d17-140">Generieren der Datendienst-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="11d17-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

-   [<span data-ttu-id="11d17-141">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="11d17-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

-   [<span data-ttu-id="11d17-142">Entity Framework-Anbieter</span><span class="sxs-lookup"><span data-stu-id="11d17-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="11d17-143">Für welche Aufgaben kann ich es verwenden?</span><span class="sxs-lookup"><span data-stu-id="11d17-143">What can I do with it?</span></span>

-   [<span data-ttu-id="11d17-144">Übersicht</span><span class="sxs-lookup"><span data-stu-id="11d17-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

-   [<span data-ttu-id="11d17-145">Whitepaper: Einführung in OData</span><span class="sxs-lookup"><span data-stu-id="11d17-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [<span data-ttu-id="11d17-146">Anwendungsszenarios</span><span class="sxs-lookup"><span data-stu-id="11d17-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

<span data-ttu-id="11d17-147">Ich möchte Silverlight verwenden…</span><span class="sxs-lookup"><span data-stu-id="11d17-147">I want to use Silverlight...</span></span>

-   [<span data-ttu-id="11d17-148">Silverlight-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="11d17-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [<span data-ttu-id="11d17-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="11d17-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

-   [<span data-ttu-id="11d17-150">Erste Schritte mit Silverlight</span><span class="sxs-lookup"><span data-stu-id="11d17-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="11d17-151">Ich möchte LINQ verwenden…</span><span class="sxs-lookup"><span data-stu-id="11d17-151">I want to use LINQ...</span></span>

-   [<span data-ttu-id="11d17-152">Abfragen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="11d17-152">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

-   [<span data-ttu-id="11d17-153">Überlegungen zu LINQ</span><span class="sxs-lookup"><span data-stu-id="11d17-153">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

-   [<span data-ttu-id="11d17-154">Vorgehensweise: Ausführen von Datendienstabfragen</span><span class="sxs-lookup"><span data-stu-id="11d17-154">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="11d17-155">Ich benötige weitere...</span><span class="sxs-lookup"><span data-stu-id="11d17-155">I still need some more information...</span></span>

-   [<span data-ttu-id="11d17-156">WCF Data Services-Teamblog</span><span class="sxs-lookup"><span data-stu-id="11d17-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

-   [<span data-ttu-id="11d17-157">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="11d17-157">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

-   [<span data-ttu-id="11d17-158">WCF Data Services Developer Center</span><span class="sxs-lookup"><span data-stu-id="11d17-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

-   [<span data-ttu-id="11d17-159">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="11d17-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="11d17-160">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="11d17-160">In This Section</span></span>

 [<span data-ttu-id="11d17-161">Übersicht</span><span class="sxs-lookup"><span data-stu-id="11d17-161">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

 <span data-ttu-id="11d17-162">Bietet eine Übersicht über die Features und Funktionen, die in WCF Data Services verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11d17-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

 [<span data-ttu-id="11d17-163">Neues in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="11d17-163">What's New in WCF Data Services</span></span>](https://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)

 <span data-ttu-id="11d17-164">Beschreibt neue Funktionen in WCF Data Services und Unterstützung für neue Features von OData.</span><span class="sxs-lookup"><span data-stu-id="11d17-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

 [<span data-ttu-id="11d17-165">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="11d17-165">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

 <span data-ttu-id="11d17-166">Beschreibt das Verfügbarmachen und Verarbeiten von OData-Feeds mithilfe von WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="11d17-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

 [<span data-ttu-id="11d17-167">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="11d17-167">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

 <span data-ttu-id="11d17-168">Beschreibt das Erstellen und Konfigurieren eines Datendiensts, das OData-Feeds verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="11d17-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

 [<span data-ttu-id="11d17-169">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="11d17-169">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

 <span data-ttu-id="11d17-170">Beschreibt, wie Clientbibliotheken verwenden, die OData-Feeds aus einer .NET Framework-Clientanwendung nutzen.</span><span class="sxs-lookup"><span data-stu-id="11d17-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="11d17-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11d17-171">See Also</span></span>

- [<span data-ttu-id="11d17-172">Representational State Transfer (REST)</span><span class="sxs-lookup"><span data-stu-id="11d17-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
