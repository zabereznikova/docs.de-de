---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 017fe2177cf824d461b4c51ea805f75b6ddbe064
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779985"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="991c1-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="991c1-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="991c1-103">WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente des .NET Framework, die es Ihnen ermöglicht, Dienste [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] zu erstellen, die verwenden, um mithilfe der Semantik des darstellenden [Zustandsdaten über das Internet oder Intranet verfügbar zu machen und zu nutzen. Übertragung (Rest)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="991c1-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="991c1-104">OData macht Daten als durch URIs adressierbare Ressourcen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="991c1-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="991c1-105">Der Zugriff auf und die Änderung von Daten erfolgt mithilfe der Standard-HTTP-Befehle GET, PUT, POST und DELETE.</span><span class="sxs-lookup"><span data-stu-id="991c1-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="991c1-106">Odata verwendet die Entitäts Beziehungs Konventionen des [Entity Data Model](../adonet/entity-data-model.md) , um Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="991c1-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="991c1-107">WCF Data Services verwendet das odata-Protokoll zum adressieren und Aktualisieren von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="991c1-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="991c1-108">Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der odata unterstützt.</span><span class="sxs-lookup"><span data-stu-id="991c1-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="991c1-109">Mithilfe von odata können Sie Daten mithilfe von bekannten Übertragungs Formaten anfordern und in Ressourcen schreiben: Atom, ein Satz von Standards zum austauschen und Aktualisieren von Daten als XML und JavaScript Object Notation (JSON), ein in AJAX-Anwendungen häufig verwendetes textbasiertes Datenaustauschformat.</span><span class="sxs-lookup"><span data-stu-id="991c1-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="991c1-110">WCF Data Services können Daten, die aus verschiedenen Quellen stammen, als odata-Feeds verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="991c1-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="991c1-111">Mithilfe von Visual Studio-Tools können Sie einen odata-basierten Dienst einfacher erstellen, indem Sie ein ADO.NET Entity Framework-Datenmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="991c1-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="991c1-112">Sie können auch odata-Feeds basierend auf Common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="991c1-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="991c1-113">WCF Data Services umfasst auch eine Reihe von Client Bibliotheken, eine für allgemeine .NET Framework Client Anwendungen und eine für Silverlight-basierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="991c1-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="991c1-114">Diese Client Bibliotheken stellen ein objektbasiertes Programmiermodell bereit, wenn Sie auf einen odata-Feed aus Umgebungen wie .NET Framework und Silverlight zugreifen.</span><span class="sxs-lookup"><span data-stu-id="991c1-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="991c1-115">Wo sollte ich beginnen?</span><span class="sxs-lookup"><span data-stu-id="991c1-115">Where Should I Start?</span></span>

<span data-ttu-id="991c1-116">In Abhängigkeit von ihren Interessen sollten Sie die ersten Schritte mit WCF Data Services in einem der folgenden Themen Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="991c1-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="991c1-117">Ich möchte direkt beginnen…</span><span class="sxs-lookup"><span data-stu-id="991c1-117">I want to jump right in...</span></span>

- [<span data-ttu-id="991c1-118">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="991c1-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="991c1-119">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="991c1-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="991c1-120">Silverlight-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="991c1-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="991c1-121">Silverlight-Schnellstart für Windows Phone-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="991c1-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="991c1-122">Nur Code anzeigen...</span><span class="sxs-lookup"><span data-stu-id="991c1-122">Just show me some code...</span></span>

- [<span data-ttu-id="991c1-123">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="991c1-123">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="991c1-124">Vorgehensweise: Ausführen von Datendienst Abfragen</span><span class="sxs-lookup"><span data-stu-id="991c1-124">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="991c1-125">Vorgehensweise: Binden von Daten an Windows Presentation Foundation Elemente</span><span class="sxs-lookup"><span data-stu-id="991c1-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="991c1-126">Ich möchte mehr über odata erfahren...</span><span class="sxs-lookup"><span data-stu-id="991c1-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="991c1-127">Whitepaper Einführung in odata</span><span class="sxs-lookup"><span data-stu-id="991c1-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="991c1-128">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="991c1-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="991c1-129">OData SDK</span><span class="sxs-lookup"><span data-stu-id="991c1-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="991c1-130">OData Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="991c1-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="991c1-131">Ich möchte einige Videos ansehen...</span><span class="sxs-lookup"><span data-stu-id="991c1-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="991c1-132">Einführung in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="991c1-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="991c1-133">WCF Data Services Developer-Videos</span><span class="sxs-lookup"><span data-stu-id="991c1-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="991c1-134">OData Entwickler Website</span><span class="sxs-lookup"><span data-stu-id="991c1-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="991c1-135">Ich möchte End-to-End-Beispiele sehen...</span><span class="sxs-lookup"><span data-stu-id="991c1-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="991c1-136">WCF Data Services-Dokumentationsbeispiele auf MSDN Samples Gallery</span><span class="sxs-lookup"><span data-stu-id="991c1-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="991c1-137">Weitere WCF Data Services-Beispiele auf MSDN Samples Gallery</span><span class="sxs-lookup"><span data-stu-id="991c1-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="991c1-138">OData SDK</span><span class="sxs-lookup"><span data-stu-id="991c1-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="991c1-139">Wie erfolgt die Integration in Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="991c1-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="991c1-140">Generieren der Datendienst-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="991c1-140">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="991c1-141">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="991c1-141">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="991c1-142">Entity Framework-Anbieter</span><span class="sxs-lookup"><span data-stu-id="991c1-142">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="991c1-143">Für welche Aufgaben kann ich es verwenden?</span><span class="sxs-lookup"><span data-stu-id="991c1-143">What can I do with it?</span></span>

- [<span data-ttu-id="991c1-144">Übersicht</span><span class="sxs-lookup"><span data-stu-id="991c1-144">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="991c1-145">Whitepaper Einführung in odata</span><span class="sxs-lookup"><span data-stu-id="991c1-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="991c1-146">Anwendungsszenarios</span><span class="sxs-lookup"><span data-stu-id="991c1-146">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="991c1-147">Ich möchte Silverlight verwenden...</span><span class="sxs-lookup"><span data-stu-id="991c1-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="991c1-148">Silverlight-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="991c1-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="991c1-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="991c1-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="991c1-150">Erste Schritte mit Silverlight</span><span class="sxs-lookup"><span data-stu-id="991c1-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="991c1-151">Ich möchte LINQ verwenden...</span><span class="sxs-lookup"><span data-stu-id="991c1-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="991c1-152">Abfragen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="991c1-152">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="991c1-153">Überlegungen zu LINQ</span><span class="sxs-lookup"><span data-stu-id="991c1-153">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="991c1-154">Vorgehensweise: Ausführen von Datendienst Abfragen</span><span class="sxs-lookup"><span data-stu-id="991c1-154">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="991c1-155">Ich benötige noch weitere Informationen...</span><span class="sxs-lookup"><span data-stu-id="991c1-155">I still need some more information...</span></span>

- [<span data-ttu-id="991c1-156">WCF Data Services-Teamblog</span><span class="sxs-lookup"><span data-stu-id="991c1-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="991c1-157">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="991c1-157">Resources</span></span>](wcf-data-services-resources.md)

- [<span data-ttu-id="991c1-158">WCF Data Services Developer Center</span><span class="sxs-lookup"><span data-stu-id="991c1-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="991c1-159">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="991c1-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="991c1-160">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="991c1-160">In This Section</span></span>

[<span data-ttu-id="991c1-161">Übersicht</span><span class="sxs-lookup"><span data-stu-id="991c1-161">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="991c1-162">Bietet eine Übersicht über die Features und Funktionen, die in WCF Data Services verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="991c1-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="991c1-163">[Neues in WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="991c1-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="991c1-164">Beschreibt neue Funktionen in WCF Data Services und Unterstützung neuer odata-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="991c1-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="991c1-165">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="991c1-165">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="991c1-166">Beschreibt, wie odata-Feeds mithilfe von WCF Data Services verfügbar gemacht und genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="991c1-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="991c1-167">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="991c1-167">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="991c1-168">Beschreibt, wie Sie einen Datendienst erstellen und konfigurieren, der odata-Feeds verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="991c1-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="991c1-169">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="991c1-169">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="991c1-170">Beschreibt die Verwendung von Client Bibliotheken für die Nutzung von odata-Feeds aus einer .NET Framework Client Anwendung.</span><span class="sxs-lookup"><span data-stu-id="991c1-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="991c1-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="991c1-171">See also</span></span>

- [<span data-ttu-id="991c1-172">Representational State Transfer (REST)</span><span class="sxs-lookup"><span data-stu-id="991c1-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
