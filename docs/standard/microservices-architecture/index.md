---
title: .NET-Microservices. .NET-Microservices-Architektur für .NET-Containeranwendungen
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Microservices sind modulare und unabhängig bereitstellbare Dienste. Docker-Container (für Linux und Windows) vereinfachen die Bereitstellung und das Testen, indem ein Dienst und seine Abhängigkeiten zu einer einzigen Einheit gebündelt werden, die dann in einer isolierten Umgebung ausgeführt wird.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/06/2018
ms.openlocfilehash: 154cb0eafb8f14d61191b7cad749cb93d269ff34
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105063"
---
![](./media/cover.png)

# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="65dc4-105">.NET-Microservices.</span><span class="sxs-lookup"><span data-stu-id="65dc4-105">.NET Microservices.</span></span> <span data-ttu-id="65dc4-106">.NET-Microservices-Architektur für .NET-Containeranwendungen</span><span class="sxs-lookup"><span data-stu-id="65dc4-106">Architecture for Containerized .NET Applications</span></span>

<span data-ttu-id="65dc4-107">DOWNLOAD verfügbar unter: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="65dc4-107">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="65dc4-108">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="65dc4-108">PUBLISHED BY</span></span>

<span data-ttu-id="65dc4-109">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="65dc4-109">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="65dc4-110">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="65dc4-110">A division of Microsoft Corporation</span></span>

<span data-ttu-id="65dc4-111">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="65dc4-111">One Microsoft Way</span></span>

<span data-ttu-id="65dc4-112">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="65dc4-112">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="65dc4-113">Copyright © 2018 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="65dc4-113">Copyright © 2018 by Microsoft Corporation</span></span>

<span data-ttu-id="65dc4-114">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="65dc4-114">All rights reserved.</span></span> <span data-ttu-id="65dc4-115">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="65dc4-115">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="65dc4-116">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="65dc4-116">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="65dc4-117">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="65dc4-117">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="65dc4-118">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="65dc4-118">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="65dc4-119">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="65dc4-119">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="65dc4-120">Microsoft und die auf der Webseite „Marken“ unter http://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="65dc4-120">Microsoft and the trademarks listed at http://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="65dc4-121">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="65dc4-121">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="65dc4-122">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="65dc4-122">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="65dc4-123">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="65dc4-123">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="65dc4-124">Mitautoren:</span><span class="sxs-lookup"><span data-stu-id="65dc4-124">Co-Authors:</span></span>

> <span data-ttu-id="65dc4-125">**Cesar de la Torre**, Sr. PM, .NET-Produktionsteam, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="65dc4-125">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="65dc4-126">**Bill Wagner**, Sr. Inhaltsentwickler, C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="65dc4-126">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="65dc4-127">
  **Mike Rousos**, leitender Softwareentwickler, DevDiv CAT-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-127">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="65dc4-128">Editoren:</span><span class="sxs-lookup"><span data-stu-id="65dc4-128">Editors:</span></span>

> <span data-ttu-id="65dc4-129">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="65dc4-129">**Mike Pope**</span></span>
>
> <span data-ttu-id="65dc4-130">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="65dc4-130">**Steve Hoag**</span></span>

<span data-ttu-id="65dc4-131">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="65dc4-131">Participants and reviewers:</span></span>

> <span data-ttu-id="65dc4-132">**Jeffrey Richter**, Partner Software Engineer, Azure-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-132">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-133">**Jimmy Bogard**, leitender Architekt bei Headspring</span><span class="sxs-lookup"><span data-stu-id="65dc4-133">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="65dc4-134">**Udi Dahan**, Gründer & CEO, bestimmte Software</span><span class="sxs-lookup"><span data-stu-id="65dc4-134">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="65dc4-135">**Jimmy Nilsson**, Mitgründer und CEO von Factor10</span><span class="sxs-lookup"><span data-stu-id="65dc4-135">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="65dc4-136">**Glenn Condron**, Sr. Programmmanager, ASP.NET-Team</span><span class="sxs-lookup"><span data-stu-id="65dc4-136">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="65dc4-137">**Mark Fussell**, PM-Teamleiter, Azure Service Fabric-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-137">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-138">**Diego Vega**, PM-Teamleiter, Entity Framework-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-138">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-139">**Barry Dorrans**, Sr. Manager für das Sicherheitsprogramm</span><span class="sxs-lookup"><span data-stu-id="65dc4-139">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="65dc4-140">**Rowan Miller**, Sr. Programmmanager, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-140">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-141">**Ankit Asthana**, leitender PM-Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-141">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-142">**Scott Hunter**, Partner Director von PM, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-142">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-143">**Dylan Reisenberger**, Architekt und Entwicklungsleiter bei Polly</span><span class="sxs-lookup"><span data-stu-id="65dc4-143">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="65dc4-144">**Steve Smith**, Softwarespezialist & Trainer bei ASPSmith Ltd.</span><span class="sxs-lookup"><span data-stu-id="65dc4-144">**Steve Smith**, Software Craftsman & Trainer at ASPSmith Ltd.</span></span>
>
> <span data-ttu-id="65dc4-145">**Ian Cooper**, Codearchitekt bei Brighter</span><span class="sxs-lookup"><span data-stu-id="65dc4-145">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="65dc4-146">**Unai Zorrilla**, Architekt und Entwicklungsleiter bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65dc4-146">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="65dc4-147">**Eduard Tomas**, Entwicklungsleiter bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65dc4-147">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="65dc4-148">**Ramon Tomas**, Entwickler bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65dc4-148">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="65dc4-149">**David Sanz**, Entwickler bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="65dc4-149">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="65dc4-150">**Javier Valero**, Chief Operating Officer bei Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="65dc4-150">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="65dc4-151">**Pierre Millet**, Sr. Berater, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-151">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="65dc4-152">**Michael Friis**, Produktmanager, Docker Inc</span><span class="sxs-lookup"><span data-stu-id="65dc4-152">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="65dc4-153">
  **Charles Lowell**, Softwareentwickler, VS CAT-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="65dc4-153">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="65dc4-154">Einführung</span><span class="sxs-lookup"><span data-stu-id="65dc4-154">Introduction</span></span>

<span data-ttu-id="65dc4-155">Unternehmen sparen zunehmend Kosten, lösen Entwicklungsprobleme und verbessern DevOps und Produktvorgänge durch das Verwenden von Containern.</span><span class="sxs-lookup"><span data-stu-id="65dc4-155">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="65dc4-156">Microsoft hat durch das Erstellen von Produkten wie Azure Container Service und Azure Service Fabric sowie durch die Partnerschaft mit Marktführern wie Docker, Mesosphere und Kubernetes Containerinnovationen für Linux und Windows veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="65dc4-156">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Container Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="65dc4-157">Diese Produkte stellen Containerlösungen bereit, die Unternehmen beim Erstellen und Bereitstellen von Anwendungen mit Cloudgeschwindigkeit und im Cloudmaßstab unterstützen, unabhängig von der Wahl ihrer Plattformen oder Tools.</span><span class="sxs-lookup"><span data-stu-id="65dc4-157">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="65dc4-158">Docker entwickelt sich praktisch zum Standard in der Containerindustrie und wird von den meisten wichtigen Anbietern der Windows- und Linux-Ökosysteme unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65dc4-158">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="65dc4-159">(Microsoft ist einer der wichtigsten Cloudanbieter, die Docker unterstützen.) In Zukunft wird Docker wahrscheinlich in jedem lokalen oder Cloud-Datencenter allgegenwärtig sein.</span><span class="sxs-lookup"><span data-stu-id="65dc4-159">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="65dc4-160">Darüber hinaus hat sich die [Microservices](https://martinfowler.com/articles/microservices.html)-Architektur zu einem wichtigen Ansatz für verteilte unternehmenskritische Anwendungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="65dc4-160">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="65dc4-161">In einer auf Microservice basierenden Architektur wird die Anwendung auf einer Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, bereitgestellt und mit Versionsangabe versehen werden können.</span><span class="sxs-lookup"><span data-stu-id="65dc4-161">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="65dc4-162">Über diesen Leitfaden</span><span class="sxs-lookup"><span data-stu-id="65dc4-162">About this guide</span></span>

<span data-ttu-id="65dc4-163">Dieser Leitfaden ist eine Einführung in das Entwickeln von auf Microservices basierenden Anwendung und das Verwalten derselben mithilfe von Containern.</span><span class="sxs-lookup"><span data-stu-id="65dc4-163">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="65dc4-164">Er erläutert das Architekturdesign und Implementierungsansätze mithilfe von .NET Core und Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="65dc4-164">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="65dc4-165">Um den Einstieg in Container und Microservices einfacher zu gestalten, konzentriert sich der Leitfaden auf eine auf Containern und Microservice basierende Verweisanwendung, die Sie erforschen können.</span><span class="sxs-lookup"><span data-stu-id="65dc4-165">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="65dc4-166">Die Beispielanwendung ist im [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)-GitHub-Repository verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65dc4-166">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="65dc4-167">Dieser Leitfaden enthält in erster Linie grundlegende Entwicklungs- und Architekturrichtlinien auf Ebene der Entwicklungsumgebung mit einem Schwerpunkt auf zwei Technologien: Docker und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="65dc4-167">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="65dc4-168">Dieser Leitfaden ist dafür gedacht, dass Sie ihn lesen, wenn Sie über das Design Ihrer Anwendung nachdenken, ohne sich auf die Infrastruktur (Cloud oder lokal) Ihrer Produktionsumgebung zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="65dc4-168">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="65dc4-169">Die Entscheidung über Ihre Infrastruktur treffen Sie später, wenn Sie Ihre produktionsbereiten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="65dc4-169">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="65dc4-170">Deshalb ignoriert dieser Leitfaden die Infrastruktur und konzentriert sich auf die Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="65dc4-170">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="65dc4-171">Der nächste Schritt nach dem Durcharbeiten dieses Leitfadens ist der, mehr über produktionsbereite Microservices in Microsoft Azure zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="65dc4-171">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="65dc4-172">Was in diesem Leitfaden nicht behandelt wird</span><span class="sxs-lookup"><span data-stu-id="65dc4-172">What this guide does not cover</span></span>

<span data-ttu-id="65dc4-173">Dieser Leitfaden konzentriert sich nicht auf den Lebenszyklus der Anwendung, DevOps, CI/CD-Pipelines oder Teamarbeit.</span><span class="sxs-lookup"><span data-stu-id="65dc4-173">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="65dc4-174">Der komplementäre Leitfaden [Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools)](https://aka.ms/dockerlifecycleebook) konzentriert sich auf dieses Thema.</span><span class="sxs-lookup"><span data-stu-id="65dc4-174">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="65dc4-175">Der aktuelle Leitfaden enthält ebenfalls keine Details zu der Implementierung in die Azure-Infrastruktur, z.B. Informationen zu bestimmten Koordinatoren.</span><span class="sxs-lookup"><span data-stu-id="65dc4-175">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="65dc4-176">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="65dc4-176">Additional resources</span></span>

-   <span data-ttu-id="65dc4-177">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools)** (E-Book zum Download) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="65dc4-177">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="65dc4-178">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="65dc4-178">Who should use this guide</span></span>

<span data-ttu-id="65dc4-179">Dieser Leitfaden wurde für Entwickler und Lösungsarchitekten geschrieben, die mit der Entwicklung von auf Docker basierenden Anwendungen und mit der auf Microservices basierenden Architektur noch nicht vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="65dc4-179">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="65dc4-180">Dieser Leitfaden ist für Sie geeignet, wenn Sie mehr über das Entwickeln, Entwerfen und Implementieren von Machbarkeitsstudienanwendungen mit den Entwicklungstechnologien von Microsoft (mit Schwerpunkt auf .NET Core) und mit Docker-Containern erfahren möchten.</span><span class="sxs-lookup"><span data-stu-id="65dc4-180">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="65dc4-181">Außerdem kann dieser Leitfaden hilfreich für Sie sein, wenn Sie ein technischer Entscheidungsträger sind, z.B. ein Unternehmensarchitekt, der einen Überblick über die Architektur und Technologie erhalten möchte, bevor über einen Ansatz für neue und moderne verteilte Anwendungen entschieden wird.</span><span class="sxs-lookup"><span data-stu-id="65dc4-181">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="65dc4-182">So verwenden Sie diesen Leitfaden</span><span class="sxs-lookup"><span data-stu-id="65dc4-182">How to use this guide</span></span>

<span data-ttu-id="65dc4-183">Im ersten Teil dieses Leitfadens werden Docker-Container vorgestellt. Außerdem wird erläutert, wie zwischen .NET Core und .NET Framework als Entwicklungsframework gewählt werden kann und ein Überblick über Microservices bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="65dc4-183">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="65dc4-184">Dieser Inhalt ist an Architekten und technische Entscheidungsträger gerichtet, die sich einen Überblick verschaffen möchten, aber sich nicht auf die Details zur Implementierung des Codes konzentrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="65dc4-184">This content is for architects and technical decision makers who want an overview but who do not need to focus on code implementation details.</span></span>

<span data-ttu-id="65dc4-185">Der zweite Teil dieses Leitfadens beginnt mit dem Abschnitt [Development Process for Docker Based Applications (Entwicklungsprozess für auf Docker basierende Anwendungen)](#ch_dev_process_for_docker_based_apps).</span><span class="sxs-lookup"><span data-stu-id="65dc4-185">The second part of the guide starts with the [Development process for Docker based applications](#ch_dev_process_for_docker_based_apps) section.</span></span> <span data-ttu-id="65dc4-186">Der Schwerpunkt liegt auf den Mustern für die Entwicklung und Microservices, um Anwendungen mithilfe von .NET Core und Docker zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="65dc4-186">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="65dc4-187">Dieser Abschnitt ist am besten für Entwickler und Architekten geeignet, die sich auf den Code, auf Muster und auf Implementierungsdetails konzentrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="65dc4-187">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="65dc4-188">Verknüpfte auf Microservice und Containern basierende Verweisanwendung: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="65dc4-188">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="65dc4-189">Bei der eShopOnContainers-Anwendung handelt es sich um eine Verweis-App für .NET Core und Microservices, die für die Bereitstellung mithilfe von Docker-Containern entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="65dc4-189">The eShopOnContainers application is a reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="65dc4-190">Die Anwendung besteht aus mehreren Subsystemen, einschließlich mehrerer Front-Ends der E-Store-UI (eine Web-App und eine native mobile App).</span><span class="sxs-lookup"><span data-stu-id="65dc4-190">The application consists of multiple subsystems, including several e-store UI front ends (a Web app and a native mobile app).</span></span> <span data-ttu-id="65dc4-191">Sie enthält ebenfalls den Back-End-Microservice und Container für alle erforderlichen serverseitigen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="65dc4-191">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="65dc4-192">Der Quellcode dieser auf Microservice und Containern basierenden Anwendung ist Open Source und verfügbar im [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)-GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="65dc4-192">This microservice and container-based application source code is open source and available at the [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub repo.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="65dc4-193">Senden Sie uns Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="65dc4-193">Send us your feedback!</span></span>

<span data-ttu-id="65dc4-194">Dieser Leitfaden wurde geschrieben, um Ihnen die Architektur von Containeranwendungen und Microservices in .NET näherzubringen.</span><span class="sxs-lookup"><span data-stu-id="65dc4-194">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="65dc4-195">Der Leitfaden und die verknüpfte Verweisanwendung werden weiterentwickelt. Wir freuen uns über Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="65dc4-195">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="65dc4-196">Wenn Sie Kommentare dazu haben, wie dieser Leitfaden verbessert werden kann, senden Sie diese bitte an:</span><span class="sxs-lookup"><span data-stu-id="65dc4-196">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

>[!div class="step-by-step"]
[<span data-ttu-id="65dc4-197">Nächste</span><span class="sxs-lookup"><span data-stu-id="65dc4-197">Next</span></span>](container-docker-introduction/index.md)
