---
title: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure
description: Ein Leitfaden, der eine End-to-End-Anleitung zur Erstellung monolithischer Webanwendungen mit ASP.NET Core und Azure bietet.
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 27212045d9870c9f2fc15509d76f3e9b07d8657f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675834"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="a39d8-103">Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure</span><span class="sxs-lookup"><span data-stu-id="a39d8-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Titelbild des Leifadens „Architect Modern Web Applications“ (Entwerfen moderner Webanwendungen)](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="a39d8-105">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="a39d8-105">PUBLISHED BY</span></span>

<span data-ttu-id="a39d8-106">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="a39d8-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="a39d8-107">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="a39d8-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="a39d8-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a39d8-108">One Microsoft Way</span></span>

<span data-ttu-id="a39d8-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="a39d8-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="a39d8-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="a39d8-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="a39d8-111">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="a39d8-111">All rights reserved.</span></span> <span data-ttu-id="a39d8-112">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="a39d8-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="a39d8-113">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="a39d8-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="a39d8-114">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a39d8-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="a39d8-115">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="a39d8-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="a39d8-116">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="a39d8-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="a39d8-117">Microsoft und die auf der Webseite „Marken“ unter https://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="a39d8-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="a39d8-118">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="a39d8-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="a39d8-119">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="a39d8-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="a39d8-120">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a39d8-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="a39d8-121">Autor:</span><span class="sxs-lookup"><span data-stu-id="a39d8-121">Author:</span></span>

> <span data-ttu-id="a39d8-122">**Steve „ardalis“ Smith** – Softwarearchitekt und Trainer – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="a39d8-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="a39d8-123">Editoren:</span><span class="sxs-lookup"><span data-stu-id="a39d8-123">Editors:</span></span>

> <span data-ttu-id="a39d8-124">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="a39d8-124">**Maira Wenzel**</span></span>

## <a name="introduction"></a><span data-ttu-id="a39d8-125">Einführung</span><span class="sxs-lookup"><span data-stu-id="a39d8-125">Introduction</span></span>

<span data-ttu-id="a39d8-126">.NET Core und ASP.NET Core bieten mehrere Vorteile gegenüber der traditionellen .NET-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="a39d8-126">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="a39d8-127">Sie sollten .NET Core für Ihre Serveranwendungen verwenden, wenn einige oder alle der folgenden Punkte für den Erfolg Ihrer Anwendung wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="a39d8-127">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="a39d8-128">Plattformübergreifende Unterstützung</span><span class="sxs-lookup"><span data-stu-id="a39d8-128">Cross-platform support.</span></span>

- <span data-ttu-id="a39d8-129">Verwendung von Microservices</span><span class="sxs-lookup"><span data-stu-id="a39d8-129">Use of microservices.</span></span>

- <span data-ttu-id="a39d8-130">Verwendung von Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="a39d8-130">Use of Docker containers.</span></span>

- <span data-ttu-id="a39d8-131">Anforderungen für hohe Leistung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="a39d8-131">High performance and scalability requirements.</span></span>

- <span data-ttu-id="a39d8-132">Parallele Versionsverwaltung von .NET-Versionen durch Anwendung auf demselben Server</span><span class="sxs-lookup"><span data-stu-id="a39d8-132">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="a39d8-133">Traditionelle .NET-Anwendungen können und werden viele dieser Anforderungen unterstützen, aber ASP.NET Core und .NET Core wurden optimiert, um eine verbesserte Unterstützung für die oben genannten Szenarien zu bieten.</span><span class="sxs-lookup"><span data-stu-id="a39d8-133">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="a39d8-134">Immer mehr Unternehmen entscheiden sich dafür, ihre Webanwendungen in der Cloud zu hosten, indem sie Dienste wie Microsoft Azure nutzen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-134">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="a39d8-135">Sie sollten in Erwägung ziehen, Ihre Anwendung in der Cloud zu hosten, wenn die folgenden Punkte für Ihre Anwendung oder Organisation wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="a39d8-135">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="a39d8-136">Geringere Investitionen bei den Rechenzentrumskosten (Hardware, Software, Speicherplatz, Hilfsprogramme, Serververwaltung usw.)</span><span class="sxs-lookup"><span data-stu-id="a39d8-136">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="a39d8-137">Flexible Preisgestaltung (nutzungsbasierte Abrechnung, nicht nach Leerlaufkapazität)</span><span class="sxs-lookup"><span data-stu-id="a39d8-137">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="a39d8-138">Extreme Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="a39d8-138">Extreme reliability.</span></span>

- <span data-ttu-id="a39d8-139">Verbesserte App-Mobilität, einfaches Ändern, wo und wie Ihre App bereitgestellt wird</span><span class="sxs-lookup"><span data-stu-id="a39d8-139">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="a39d8-140">Flexible Kapazität, Hoch- oder Herunterskalierung basieren auf dem tatsächlichen Bedarf</span><span class="sxs-lookup"><span data-stu-id="a39d8-140">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="a39d8-141">Das Erstellen von Webanwendungen mit ASP.NET Core (gehostet in Azure) bietet eine Menge Wettbewerbsvorteile gegenüber herkömmlichen Alternativen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-141">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="a39d8-142">ASP.NET Core ist für moderne Webanwendungs-Entwicklungspraktiken und Cloudhostingszenarien optimiert.</span><span class="sxs-lookup"><span data-stu-id="a39d8-142">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="a39d8-143">In diesem Leitfaden erfahren Sie, wie Sie Ihre ASP.NET Core-Anwendungen so gestalten, dass Sie diese Funktionen optimal nutzen können.</span><span class="sxs-lookup"><span data-stu-id="a39d8-143">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="a39d8-144">Zweck</span><span class="sxs-lookup"><span data-stu-id="a39d8-144">Purpose</span></span>

<span data-ttu-id="a39d8-145">Dieser Leitfaden bietet eine End-to-End-Anleitung zur Erstellung *monolithischer* Webanwendungen mit ASP.NET Core und Azure.</span><span class="sxs-lookup"><span data-stu-id="a39d8-145">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="a39d8-146">In diesem Zusammenhang bezieht sich „monolithisch“ auf die Tatsache, dass diese Anwendungen als eine einzige Einheit und nicht als eine Sammlung von interagierenden Diensten und Anwendungen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a39d8-146">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="a39d8-147">Dieser Leitfaden ist eine Ergänzung zum E-Book [„_.NET Microservices. Architektur für .NET-Containeranwendungen_“](../microservices-architecture/index.md), das sich mehr auf Docker, Microservices und die Bereitstellung von Containern zum Hosten von Unternehmensanwendungen konzentriert.</span><span class="sxs-lookup"><span data-stu-id="a39d8-147">This guide is complementary to the ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices-architecture/index.md) which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="a39d8-148">.NET-Microservices.</span><span class="sxs-lookup"><span data-stu-id="a39d8-148">.NET Microservices.</span></span> <span data-ttu-id="a39d8-149">.NET-Microservices-Architektur für .NET-Containeranwendungen</span><span class="sxs-lookup"><span data-stu-id="a39d8-149">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="a39d8-150">**E-Book**</span><span class="sxs-lookup"><span data-stu-id="a39d8-150">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="a39d8-151">**Beispielanwendung**</span><span class="sxs-lookup"><span data-stu-id="a39d8-151">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="a39d8-152">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="a39d8-152">Who should use this guide</span></span>

<span data-ttu-id="a39d8-153">Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die daran interessiert sind, moderne Webanwendungen mit Microsoft-Technologien und -Diensten in der Cloud zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-153">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="a39d8-154">Eine zweite Zielgruppe sind technische Entscheidungsträger, die bereits mit ASP.NET oder Azure vertraut sind und Informationen dazu suchen, ob ein Upgrade auf ASP.NET Core für neue oder vorhandene Projekte sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="a39d8-154">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="a39d8-155">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="a39d8-155">How you can use this guide</span></span>

<span data-ttu-id="a39d8-156">Dieser Leitfaden wurde in einem relativ kleinen Dokument zusammengefasst, das sich auf die Erstellung von Webanwendungen mit modernen .NET-Technologien und Windows Azure konzentriert.</span><span class="sxs-lookup"><span data-stu-id="a39d8-156">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="a39d8-157">Als solches kann er in seiner Gesamtheit gelesen werden, um eine Grundlage für das Verständnis solcher Anwendungen und ihrer technischen Überlegungen zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-157">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="a39d8-158">Der Leitfaden kann zusammen mit seiner Beispielanwendung auch als Ausgangspunkt oder Referenz dienen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-158">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="a39d8-159">Verwenden Sie die zugehörige Beispielanwendung als Vorlage für Ihre eigenen Anwendungen oder um zu sehen, wie Sie die einzelnen Komponenten Ihrer Anwendung organisieren können.</span><span class="sxs-lookup"><span data-stu-id="a39d8-159">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="a39d8-160">Erinnern Sie sich an die Grundsätze des Leitfadens und die Beschreibung von Architektur- und Technologieoptionen und Entscheidungsüberlegungen, wenn Sie diese Entscheidungen für Ihre eigene Anwendung abwägen.</span><span class="sxs-lookup"><span data-stu-id="a39d8-160">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="a39d8-161">Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a39d8-161">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="a39d8-162">Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="a39d8-162">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="a39d8-163">Verweise</span><span class="sxs-lookup"><span data-stu-id="a39d8-163">References</span></span>

- <span data-ttu-id="a39d8-164">**Wahl zwischen .NET Core und .NET Framework für Server-Apps**</span><span class="sxs-lookup"><span data-stu-id="a39d8-164">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="a39d8-165">Nächste</span><span class="sxs-lookup"><span data-stu-id="a39d8-165">Next</span></span>](modern-web-applications-characteristics.md)