---
title: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure
description: "Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Einführung"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 44864274a86634c0199885b5507124f2f54ce0f6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="e16ae-103">Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure</span><span class="sxs-lookup"><span data-stu-id="e16ae-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

<span data-ttu-id="e16ae-104">.NET Core und ASP.NET Core bieten mehrere Vorteile gegenüber der traditionellen .NET-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="e16ae-104">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="e16ae-105">Sie sollten .NET Core für Ihre Serveranwendungen verwenden, wenn einige oder alle der folgenden Punkte für den Erfolg Ihrer Anwendung wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="e16ae-105">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="e16ae-106">Plattformübergreifende Unterstützung</span><span class="sxs-lookup"><span data-stu-id="e16ae-106">Cross-platform support</span></span>

-   <span data-ttu-id="e16ae-107">Verwendung von Microservices</span><span class="sxs-lookup"><span data-stu-id="e16ae-107">Use of microservices</span></span>

-   <span data-ttu-id="e16ae-108">Verwendung von Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="e16ae-108">Use of Docker containers</span></span>

-   <span data-ttu-id="e16ae-109">Anforderungen für hohe Leistung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="e16ae-109">High performance and scalability requirements</span></span>

-   <span data-ttu-id="e16ae-110">Parallele Versionsverwaltung von .NET-Versionen durch Anwendung auf demselben Server</span><span class="sxs-lookup"><span data-stu-id="e16ae-110">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="e16ae-111">Traditionelle .NET-Anwendungen können und werden diese Anforderungen unterstützen, aber ASP.NET Core und .NET Core wurden optimiert, um eine verbesserte Unterstützung für die oben genannten Szenarien zu bieten.</span><span class="sxs-lookup"><span data-stu-id="e16ae-111">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="e16ae-112">Immer mehr Unternehmen entscheiden sich dafür, ihre Webanwendungen in der Cloud zu hosten, indem sie Dienste wie Microsoft Azure nutzen.</span><span class="sxs-lookup"><span data-stu-id="e16ae-112">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="e16ae-113">Sie sollten in Erwägung ziehen, Ihre Anwendung in der Cloud zu hosten, wenn die folgenden Punkte für Ihre Anwendung oder Organisation wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="e16ae-113">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="e16ae-114">Geringere Investitionen in die Kosten des Datencenters (Hardware, Software, Speicherplatz, Hilfsprogramme usw.)</span><span class="sxs-lookup"><span data-stu-id="e16ae-114">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="e16ae-115">Flexible Preisgestaltung (nutzungsbasierte Abrechnung, nicht nach Leerlaufkapazität)</span><span class="sxs-lookup"><span data-stu-id="e16ae-115">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="e16ae-116">Extreme Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="e16ae-116">Extreme reliability</span></span>

-   <span data-ttu-id="e16ae-117">Verbesserte App-Mobilität, einfaches Ändern, wo und wie Ihre App bereitgestellt wird</span><span class="sxs-lookup"><span data-stu-id="e16ae-117">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="e16ae-118">Flexible Kapazität, Hoch- oder Herunterskalierung basieren auf dem tatsächlichen Bedarf</span><span class="sxs-lookup"><span data-stu-id="e16ae-118">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="e16ae-119">Das Erstellen von Webanwendungen mit ASP.NET Core (gehostet in Microsoft Azure) bietet zahlreiche Wettbewerbsvorteile gegenüber herkömmlichen Alternativen.</span><span class="sxs-lookup"><span data-stu-id="e16ae-119">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="e16ae-120">ASP.NET Core ist für moderne Webanwendungs-Entwicklungspraktiken und Cloudhostingszenarien optimiert.</span><span class="sxs-lookup"><span data-stu-id="e16ae-120">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="e16ae-121">In diesem Leitfaden erfahren Sie, wie Sie Ihre ASP.NET Core-Anwendungen so gestalten, dass Sie diese Funktionen optimal nutzen können.</span><span class="sxs-lookup"><span data-stu-id="e16ae-121">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="e16ae-122">Zweck</span><span class="sxs-lookup"><span data-stu-id="e16ae-122">Purpose</span></span>

<span data-ttu-id="e16ae-123">Dieser Leitfaden bietet eine End-to-End-Anleitung zur Erstellung monolithischer Webanwendungen mit ASP.NET Core und Azure.</span><span class="sxs-lookup"><span data-stu-id="e16ae-123">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="e16ae-124">Dieser Leitfaden ist das Gegenstück zum Dokument „*Entwerfen und Entwickeln von containerisierten und auf Microservices basierenden Anwendungen mit .NET*“, das sich mehr auf Docker, Microservices und die Bereitstellung von Containern für Unternehmensanwendungen konzentriert.</span><span class="sxs-lookup"><span data-stu-id="e16ae-124">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="e16ae-125">Entwerfen und Entwickeln von containerisierten und auf Microservices basierenden Apps in .NET</span><span class="sxs-lookup"><span data-stu-id="e16ae-125">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="e16ae-126">**E-Book**</span><span class="sxs-lookup"><span data-stu-id="e16ae-126">**e-book**</span></span>  
> <span data-ttu-id="e16ae-127"><http://aka.ms/MicroservicesEbook></span><span class="sxs-lookup"><span data-stu-id="e16ae-127"><http://aka.ms/MicroservicesEbook></span></span>
> - <span data-ttu-id="e16ae-128">**Beispielanwendung**</span><span class="sxs-lookup"><span data-stu-id="e16ae-128">**Sample Application**</span></span>  
> <span data-ttu-id="e16ae-129"><http://aka.ms/microservicesarchitecture></span><span class="sxs-lookup"><span data-stu-id="e16ae-129"><http://aka.ms/microservicesarchitecture></span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="e16ae-130">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="e16ae-130">Who should use this guide</span></span>

<span data-ttu-id="e16ae-131">Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die daran interessiert sind, moderne Webanwendungen mit Microsoft-Technologien und -Diensten in der Cloud zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e16ae-131">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="e16ae-132">Eine zweite Zielgruppe sind technische Entscheidungsträger, die bereits mit ASP.NET und/oder Azure vertraut sind und Informationen dazu suchen, ob ein Upgrade auf ASP.NET Core für neue oder vorhandene Projekte sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="e16ae-132">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="e16ae-133">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="e16ae-133">How you can use this guide</span></span>

<span data-ttu-id="e16ae-134">Dieser Leitfaden wurde in einem relativ kleinen Dokument zusammengefasst, das sich auf die Erstellung von Webanwendungen mit modernen .NET-Technologien und Windows Azure konzentriert.</span><span class="sxs-lookup"><span data-stu-id="e16ae-134">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="e16ae-135">Als solches kann er in seiner Gesamtheit gelesen werden, um eine Grundlage für das Verständnis solcher Anwendungen und ihrer technischen Überlegungen zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="e16ae-135">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="e16ae-136">Der Leitfaden kann zusammen mit seiner Beispielanwendung auch als Ausgangspunkt oder Referenz dienen.</span><span class="sxs-lookup"><span data-stu-id="e16ae-136">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="e16ae-137">Verwenden Sie die zugehörige Beispielanwendung als Vorlage für Ihre eigenen Anwendungen oder um zu sehen, wie Sie die einzelnen Komponenten Ihrer Anwendung organisieren können.</span><span class="sxs-lookup"><span data-stu-id="e16ae-137">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="e16ae-138">Erinnern Sie sich an die Grundsätze des Leitfadens und die Beschreibung von Architektur- und Technologieoptionen und Entscheidungsüberlegungen, wenn Sie diese Entscheidungen für Ihre eigene Anwendung abwägen.</span><span class="sxs-lookup"><span data-stu-id="e16ae-138">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="e16ae-139">Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="e16ae-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="e16ae-140">Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="e16ae-140">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="e16ae-141">Verweise</span><span class="sxs-lookup"><span data-stu-id="e16ae-141">References</span></span>
- <span data-ttu-id="e16ae-142">**Wahl zwischen .NET Core und .NET Framework für Server-Apps**</span><span class="sxs-lookup"><span data-stu-id="e16ae-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<span data-ttu-id="e16ae-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="e16ae-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e16ae-144">[Nächster] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="e16ae-144">[Next] (modern-web-applications-characteristics.md)</span></span>
