---
title: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure
description: Ein Leitfaden, der eine End-to-End-Anleitung zur Erstellung monolithischer Webanwendungen mit ASP.NET Core und Azure bietet.
author: ardalis
ms.author: wiwagn
ms.date: 12/07/2020
ms.openlocfilehash: 90d092b2269315e5b6734430e82cc7211324479b
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851294"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="d178f-103">Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure</span><span class="sxs-lookup"><span data-stu-id="d178f-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Titelbild des Leitfadens „Entfernen moderner Webanwendungen“](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="d178f-105">**EDITION v5.0:** auf ASP.NET Core 5.0 aktualisiert</span><span class="sxs-lookup"><span data-stu-id="d178f-105">**EDITION v5.0** - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="d178f-106">Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/aspnet-ebook-changelog).</span><span class="sxs-lookup"><span data-stu-id="d178f-106">Refer [changelog](https://aka.ms/aspnet-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="d178f-107">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="d178f-107">PUBLISHED BY</span></span>

<span data-ttu-id="d178f-108">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="d178f-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="d178f-109">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d178f-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="d178f-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="d178f-110">One Microsoft Way</span></span>

<span data-ttu-id="d178f-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="d178f-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="d178f-112">Copyright © 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d178f-112">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="d178f-113">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="d178f-113">All rights reserved.</span></span> <span data-ttu-id="d178f-114">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="d178f-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="d178f-115">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="d178f-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="d178f-116">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d178f-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="d178f-117">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="d178f-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="d178f-118">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="d178f-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="d178f-119">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="d178f-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="d178f-120">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="d178f-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="d178f-121">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="d178f-121">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="d178f-122">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="d178f-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="d178f-123">Autor:</span><span class="sxs-lookup"><span data-stu-id="d178f-123">Author:</span></span>

> <span data-ttu-id="d178f-124">**Steve „ardalis“ Smith** – Softwarearchitekt und Trainer – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="d178f-124">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="d178f-125">Editoren:</span><span class="sxs-lookup"><span data-stu-id="d178f-125">Editors:</span></span>

> <span data-ttu-id="d178f-126">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="d178f-126">**Maira Wenzel**</span></span>

## <a name="action-links"></a><span data-ttu-id="d178f-127">Aktionslinks</span><span class="sxs-lookup"><span data-stu-id="d178f-127">Action links</span></span>

- <span data-ttu-id="d178f-128">Dieses E-Book ist ebenso im PDF-Format erhältlich (nur in englischer Sprache) [Download](https://aka.ms/webappebook)</span><span class="sxs-lookup"><span data-stu-id="d178f-128">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/webappebook)</span></span>

- <span data-ttu-id="d178f-129">Klonen oder forken Sie die Referenzanwendung [eShopOnWeb auf GitHub](https://github.com/dotnet-architecture/eShopOnWeb).</span><span class="sxs-lookup"><span data-stu-id="d178f-129">Clone/Fork the reference application [eShopOnWeb on GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span></span>

## <a name="introduction"></a><span data-ttu-id="d178f-130">Einführung</span><span class="sxs-lookup"><span data-stu-id="d178f-130">Introduction</span></span>

<span data-ttu-id="d178f-131">.NET 5 und ASP.NET Core bieten mehrere Vorteile gegenüber der traditionellen .NET-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="d178f-131">.NET 5 and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="d178f-132">Sie sollten .NET 5 für Ihre Serveranwendungen verwenden, wenn einige oder alle der folgenden Punkte für den Erfolg Ihrer Anwendung wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="d178f-132">You should use .NET 5 for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="d178f-133">Plattformübergreifende Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d178f-133">Cross-platform support.</span></span>

- <span data-ttu-id="d178f-134">Verwendung von Microservices</span><span class="sxs-lookup"><span data-stu-id="d178f-134">Use of microservices.</span></span>

- <span data-ttu-id="d178f-135">Verwendung von Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="d178f-135">Use of Docker containers.</span></span>

- <span data-ttu-id="d178f-136">Anforderungen für hohe Leistung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="d178f-136">High performance and scalability requirements.</span></span>

- <span data-ttu-id="d178f-137">Parallele Versionsverwaltung von .NET-Versionen durch Anwendung auf demselben Server</span><span class="sxs-lookup"><span data-stu-id="d178f-137">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="d178f-138">Traditionelle .NET-Anwendungen können und werden viele dieser Anforderungen unterstützen, aber ASP.NET Core und .NET 5 wurden optimiert, um eine verbesserte Unterstützung für die oben genannten Szenarien zu bieten.</span><span class="sxs-lookup"><span data-stu-id="d178f-138">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET 5 have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="d178f-139">Immer mehr Unternehmen entscheiden sich dafür, ihre Webanwendungen in der Cloud zu hosten, indem sie Dienste wie Microsoft Azure nutzen.</span><span class="sxs-lookup"><span data-stu-id="d178f-139">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="d178f-140">Sie sollten in Erwägung ziehen, Ihre Anwendung in der Cloud zu hosten, wenn die folgenden Punkte für Ihre Anwendung oder Organisation wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="d178f-140">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="d178f-141">Geringere Investitionen bei den Rechenzentrumskosten (Hardware, Software, Speicherplatz, Hilfsprogramme, Serververwaltung usw.)</span><span class="sxs-lookup"><span data-stu-id="d178f-141">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="d178f-142">Flexible Preisgestaltung (nutzungsbasierte Abrechnung, nicht nach Leerlaufkapazität)</span><span class="sxs-lookup"><span data-stu-id="d178f-142">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="d178f-143">Extreme Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="d178f-143">Extreme reliability.</span></span>

- <span data-ttu-id="d178f-144">Verbesserte App-Mobilität, einfaches Ändern, wo und wie Ihre App bereitgestellt wird</span><span class="sxs-lookup"><span data-stu-id="d178f-144">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="d178f-145">Flexible Kapazität, Hoch- oder Herunterskalierung basieren auf dem tatsächlichen Bedarf</span><span class="sxs-lookup"><span data-stu-id="d178f-145">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="d178f-146">Das Erstellen von Webanwendungen mit ASP.NET Core (gehostet in Azure) bietet eine Menge Wettbewerbsvorteile gegenüber herkömmlichen Alternativen.</span><span class="sxs-lookup"><span data-stu-id="d178f-146">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="d178f-147">ASP.NET Core ist für moderne Webanwendungs-Entwicklungspraktiken und Cloudhostingszenarien optimiert.</span><span class="sxs-lookup"><span data-stu-id="d178f-147">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="d178f-148">In diesem Leitfaden erfahren Sie, wie Sie Ihre ASP.NET Core-Anwendungen so gestalten, dass Sie diese Funktionen optimal nutzen können.</span><span class="sxs-lookup"><span data-stu-id="d178f-148">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="version"></a><span data-ttu-id="d178f-149">Version</span><span class="sxs-lookup"><span data-stu-id="d178f-149">Version</span></span>

<span data-ttu-id="d178f-150">Dieser Leitfaden wurde für Version **.NET 5.0** überarbeitet und enthält viele weitere Updates zu artverwandten Technologien (also Azure und Drittanbietertechnologien), die zeitgleich mit dem.NET 5.0-Release veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="d178f-150">This guide has been revised to cover **.NET 5.0** version along with many additional updates related to the same "wave" of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET 5.0 release.</span></span> <span data-ttu-id="d178f-151">Aus diesem Grund wurde auch die Versionsnummer des Leitfadens auf Version **5.0** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d178f-151">That's why the book version has also been updated to version **5.0**.</span></span>

## <a name="purpose"></a><span data-ttu-id="d178f-152">Zweck</span><span class="sxs-lookup"><span data-stu-id="d178f-152">Purpose</span></span>

<span data-ttu-id="d178f-153">Dieser Leitfaden bietet eine End-to-End-Anleitung zur Erstellung *monolithischer* Webanwendungen mit ASP.NET Core und Azure.</span><span class="sxs-lookup"><span data-stu-id="d178f-153">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="d178f-154">In diesem Zusammenhang bezieht sich „monolithisch“ auf die Tatsache, dass diese Anwendungen als eine einzige Einheit und nicht als eine Sammlung von interagierenden Diensten und Anwendungen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d178f-154">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="d178f-155">Dieser Leitfaden ist eine Ergänzung zum E-Book [ _.NET Microservices: Architektur für .NET-Containeranwendungen_](../microservices/index.md), in dem vorrangig Docker, Microservices und die Bereitstellung von Containern zum Hosten von Unternehmensanwendungen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d178f-155">This guide is complementary to ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices/index.md), which focuses more on Docker, microservices, and deployment of containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="d178f-156">.NET-Microservices.</span><span class="sxs-lookup"><span data-stu-id="d178f-156">.NET Microservices.</span></span> <span data-ttu-id="d178f-157">.NET-Microservices-Architektur für .NET-Containeranwendungen</span><span class="sxs-lookup"><span data-stu-id="d178f-157">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="d178f-158">**E-Book**</span><span class="sxs-lookup"><span data-stu-id="d178f-158">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="d178f-159">**Beispielanwendung**</span><span class="sxs-lookup"><span data-stu-id="d178f-159">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="d178f-160">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="d178f-160">Who should use this guide</span></span>

<span data-ttu-id="d178f-161">Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die daran interessiert sind, moderne Webanwendungen mit Microsoft-Technologien und -Diensten in der Cloud zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d178f-161">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="d178f-162">Eine zweite Zielgruppe sind technische Entscheidungsträger, die bereits mit ASP.NET oder Azure vertraut sind und Informationen dazu suchen, ob ein Upgrade auf ASP.NET Core für neue oder vorhandene Projekte sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="d178f-162">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="d178f-163">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="d178f-163">How you can use this guide</span></span>

<span data-ttu-id="d178f-164">Dieser Leitfaden wurde in einem relativ kleinen Dokument zusammengefasst, das sich auf die Erstellung von Webanwendungen mit modernen .NET-Technologien und Azure konzentriert.</span><span class="sxs-lookup"><span data-stu-id="d178f-164">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Azure.</span></span> <span data-ttu-id="d178f-165">Als solches kann er in seiner Gesamtheit gelesen werden, um eine Grundlage für das Verständnis solcher Anwendungen und ihrer technischen Überlegungen zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="d178f-165">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="d178f-166">Der Leitfaden kann zusammen mit seiner Beispielanwendung auch als Ausgangspunkt oder Referenz dienen.</span><span class="sxs-lookup"><span data-stu-id="d178f-166">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="d178f-167">Verwenden Sie die zugehörige Beispielanwendung als Vorlage für Ihre eigenen Anwendungen oder um zu sehen, wie Sie die einzelnen Komponenten Ihrer Anwendung organisieren können.</span><span class="sxs-lookup"><span data-stu-id="d178f-167">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="d178f-168">Erinnern Sie sich an die Grundsätze des Leitfadens und die Beschreibung von Architektur- und Technologieoptionen und Entscheidungsüberlegungen, wenn Sie diese Entscheidungen für Ihre eigene Anwendung abwägen.</span><span class="sxs-lookup"><span data-stu-id="d178f-168">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="d178f-169">Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="d178f-169">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="d178f-170">Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="d178f-170">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="d178f-171">Verweise</span><span class="sxs-lookup"><span data-stu-id="d178f-171">References</span></span>

- <span data-ttu-id="d178f-172">**.NET 5 für Server-Apps im Vergleich zum .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="d178f-172">**Choosing between .NET 5 and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="d178f-173">Nächste</span><span class="sxs-lookup"><span data-stu-id="d178f-173">Next</span></span>](modern-web-applications-characteristics.md)
