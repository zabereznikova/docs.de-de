---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 890f0ba25d8320008228c73660753b9899269fd7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901002"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="d7e6f-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="d7e6f-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="d7e6f-103">WCF Data Services (früher als "ADO.NET Data Services" bezeichnet) ist eine Komponente des .NET Framework, die es Ihnen ermöglicht, Dienste zu erstellen, die die Open Data Protocol (odata) verwenden, um Daten mithilfe der Semantik von [Representational State Transfer (Rest)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)über das Internet oder Intranet verfügbar zu machen und zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="d7e6f-104">OData macht Daten als Ressourcen verfügbar, die durch URIs adressierbar sind.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="d7e6f-105">Der Zugriff auf Daten und deren Änderung erfolgt mithilfe der Standard-HTTP-Verben GET, PUT, POST und DELETE.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="d7e6f-106">Odata verwendet die Entitäts Beziehungs Konventionen des [Entity Data Model](../adonet/entity-data-model.md) , um Ressourcen als Sätze von Entitäten verfügbar zu machen, die durch Zuordnungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="d7e6f-107">WCF Data Services verwendet das odata-Protokoll zum adressieren und Aktualisieren von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="d7e6f-108">Auf diese Weise können Sie von jedem Client aus auf diese Dienste zugreifen, der odata unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="d7e6f-109">Odata ermöglicht das anfordern und Schreiben von Daten in Ressourcen mithilfe von bekannten Übertragungs Formaten: Atom, ein Satz von Standards zum austauschen und Aktualisieren von Daten als XML und JavaScript Object Notation (JSON), ein in AJAX häufig verwendetes textbasiertes Datenaustauschformat. Bereich.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="d7e6f-110">WCF Data Services können Daten, die aus verschiedenen Quellen stammen, als odata-Feeds verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="d7e6f-111">Mithilfe von Visual Studio-Tools können Sie einen odata-basierten Dienst einfacher erstellen, indem Sie ein ADO.NET Entity Framework-Datenmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="d7e6f-112">Sie können auch odata-Feeds basierend auf Common Language Runtime (CLR)-Klassen und sogar spät gebundenen oder nicht typisierten Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="d7e6f-113">WCF Data Services umfasst auch eine Reihe von Client Bibliotheken, eine für allgemeine .NET Framework Client Anwendungen und eine für Silverlight-basierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="d7e6f-114">Diese Client Bibliotheken stellen ein objektbasiertes Programmiermodell bereit, wenn Sie auf einen odata-Feed aus Umgebungen wie .NET Framework und Silverlight zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="d7e6f-115">Wo sollte ich beginnen?</span><span class="sxs-lookup"><span data-stu-id="d7e6f-115">Where Should I Start?</span></span>

<span data-ttu-id="d7e6f-116">In Abhängigkeit von ihren Interessen sollten Sie die ersten Schritte mit WCF Data Services in einem der folgenden Themen Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="d7e6f-117">Ich möchte direkt beginnen…</span><span class="sxs-lookup"><span data-stu-id="d7e6f-117">I want to jump right in...</span></span>

- [<span data-ttu-id="d7e6f-118">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="d7e6f-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="d7e6f-119">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="d7e6f-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="d7e6f-120">Nur Code anzeigen...</span><span class="sxs-lookup"><span data-stu-id="d7e6f-120">Just show me some code...</span></span>

- [<span data-ttu-id="d7e6f-121">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="d7e6f-121">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="d7e6f-122">Vorgehensweise: Ausführen von Datendienstabfragen</span><span class="sxs-lookup"><span data-stu-id="d7e6f-122">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="d7e6f-123">Vorgehensweise: Binden von Daten an Windows Presentation Foundation-Elemente</span><span class="sxs-lookup"><span data-stu-id="d7e6f-123">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="d7e6f-124">Ich möchte mehr über odata erfahren...</span><span class="sxs-lookup"><span data-stu-id="d7e6f-124">I want to know more about OData...</span></span>

- [<span data-ttu-id="d7e6f-125">Whitepaper: Einführung in OData</span><span class="sxs-lookup"><span data-stu-id="d7e6f-125">Whitepaper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="d7e6f-126">Open Data Protocol-Website</span><span class="sxs-lookup"><span data-stu-id="d7e6f-126">Open Data Protocol Web site</span></span>](https://www.odata.org/)
- [<span data-ttu-id="d7e6f-127">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="d7e6f-127">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="d7e6f-128">Ich möchte End-to-End-Beispiele sehen...</span><span class="sxs-lookup"><span data-stu-id="d7e6f-128">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="d7e6f-129">[WCF Data Services Schnellstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="d7e6f-129">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="d7e6f-130">Odata-SDK-Beispiel Code</span><span class="sxs-lookup"><span data-stu-id="d7e6f-130">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="d7e6f-131">Wie erfolgt die Integration in Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="d7e6f-131">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="d7e6f-132">Generieren der Datendienst-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="d7e6f-132">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="d7e6f-133">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="d7e6f-133">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="d7e6f-134">Entity Framework-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d7e6f-134">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="d7e6f-135">Für welche Aufgaben kann ich es verwenden?</span><span class="sxs-lookup"><span data-stu-id="d7e6f-135">What can I do with it?</span></span>

- [<span data-ttu-id="d7e6f-136">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d7e6f-136">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="d7e6f-137">Anwendungsszenarios</span><span class="sxs-lookup"><span data-stu-id="d7e6f-137">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="d7e6f-138">Ich möchte LINQ verwenden...</span><span class="sxs-lookup"><span data-stu-id="d7e6f-138">I want to use LINQ...</span></span>

- [<span data-ttu-id="d7e6f-139">Abfragen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="d7e6f-139">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="d7e6f-140">Überlegungen zu LINQ</span><span class="sxs-lookup"><span data-stu-id="d7e6f-140">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="d7e6f-141">Vorgehensweise: Ausführen von Datendienstabfragen</span><span class="sxs-lookup"><span data-stu-id="d7e6f-141">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="d7e6f-142">Ich benötige noch weitere Informationen...</span><span class="sxs-lookup"><span data-stu-id="d7e6f-142">I still need some more information...</span></span>

- [<span data-ttu-id="d7e6f-143">WCF Data Services-Teamblog</span><span class="sxs-lookup"><span data-stu-id="d7e6f-143">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="d7e6f-144">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d7e6f-144">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="d7e6f-145">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d7e6f-145">In This Section</span></span>

[<span data-ttu-id="d7e6f-146">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d7e6f-146">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="d7e6f-147">Bietet eine Übersicht über die Features und Funktionen, die in WCF Data Services verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-147">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="d7e6f-148">[Neues in WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="d7e6f-148">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="d7e6f-149">Beschreibt neue Funktionen in WCF Data Services und Unterstützung neuer odata-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-149">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="d7e6f-150">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="d7e6f-150">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="d7e6f-151">Beschreibt, wie odata-Feeds mithilfe von WCF Data Services verfügbar gemacht und genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-151">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="d7e6f-152">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d7e6f-152">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="d7e6f-153">Beschreibt, wie Sie einen Datendienst erstellen und konfigurieren, der odata-Feeds verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-153">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="d7e6f-154">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="d7e6f-154">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="d7e6f-155">Beschreibt die Verwendung von Client Bibliotheken für die Nutzung von odata-Feeds aus einer .NET Framework Client Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d7e6f-155">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7e6f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7e6f-156">See also</span></span>

- [<span data-ttu-id="d7e6f-157">Representational State Transfer (REST)</span><span class="sxs-lookup"><span data-stu-id="d7e6f-157">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
