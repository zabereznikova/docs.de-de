---
title: .NET-Microservices. .NET-Microservices-Architektur für .NET-Containeranwendungen
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Microservices sind modulare und unabhängig bereitstellbare Dienste. Docker-Container (für Linux und Windows) vereinfachen die Bereitstellung und das Testen, indem ein Dienst und seine Abhängigkeiten zu einer einzigen Einheit gebündelt werden, die dann in einer isolierten Umgebung ausgeführt wird.
ms.date: 01/30/2020
ms.openlocfilehash: 1337fe56e78e03a85627737bd52a089fd946b842
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543533"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="9104b-105">.NET-Microservices: .NET-Microservices-Architektur für .NET-Containeranwendungen</span><span class="sxs-lookup"><span data-stu-id="9104b-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![Bucheinband](./media/cover-small.png)

<span data-ttu-id="9104b-107">**EDITION v3.1** – für ASP.NET Core 3.1 aktualisiert</span><span class="sxs-lookup"><span data-stu-id="9104b-107">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="9104b-108">Dieser Leitfaden ist eine Einführung in das Entwickeln von auf Microservices basierenden Anwendung und das Verwalten derselben mithilfe von Containern.</span><span class="sxs-lookup"><span data-stu-id="9104b-108">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="9104b-109">Er erläutert das Architekturdesign und Implementierungsansätze mithilfe von .NET Core und Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="9104b-109">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span>

<span data-ttu-id="9104b-110">Um den Einstieg einfacher zu gestalten, konzentriert sich der Leitfaden auf eine auf Containern und Microservice basierende Referenzanwendung, die Sie erforschen können.</span><span class="sxs-lookup"><span data-stu-id="9104b-110">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="9104b-111">Die Referenzanwendung ist im [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)-GitHub-Repository verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9104b-111">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="9104b-112">Aktionslinks</span><span class="sxs-lookup"><span data-stu-id="9104b-112">Action links</span></span>

- <span data-ttu-id="9104b-113">Dieses E-Book ist ebenso im PDF-Format erhältlich (nur in englischer Sprache) [Download](https://aka.ms/microservicesebook)</span><span class="sxs-lookup"><span data-stu-id="9104b-113">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/microservicesebook)</span></span>

- <span data-ttu-id="9104b-114">Klonen/forken Sie die Referenzanwendung [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="9104b-114">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>

- <span data-ttu-id="9104b-115">Sehen Sie das [Einführungsvideo auf Channel 9](https://aka.ms/microservices-video) an.</span><span class="sxs-lookup"><span data-stu-id="9104b-115">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

- <span data-ttu-id="9104b-116">Lernen Sie die [Microservicearchitektur](https://aka.ms/MicroservicesArchitecture) unmittelbar kennen.</span><span class="sxs-lookup"><span data-stu-id="9104b-116">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="9104b-117">Einführung</span><span class="sxs-lookup"><span data-stu-id="9104b-117">Introduction</span></span>

<span data-ttu-id="9104b-118">Unternehmen sparen zunehmend Kosten, lösen Entwicklungsprobleme und verbessern DevOps und Produktvorgänge durch das Verwenden von Containern.</span><span class="sxs-lookup"><span data-stu-id="9104b-118">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="9104b-119">Microsoft hat mit Produkten wie Azure Kubernetes Service und Azure Service Fabric sowie durch die Partnerschaft mit Marktführern wie Docker, Mesosphere und Kubernetes Containerinnovationen für Linux und Windows veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="9104b-119">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Kubernetes Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="9104b-120">Diese Produkte stellen Containerlösungen bereit, die Unternehmen beim Erstellen und Bereitstellen von Anwendungen mit Cloudgeschwindigkeit und im Cloudmaßstab unterstützen, unabhängig von der Wahl ihrer Plattformen oder Tools.</span><span class="sxs-lookup"><span data-stu-id="9104b-120">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="9104b-121">Docker entwickelt sich praktisch zum Standard in der Containerindustrie und wird von den meisten wichtigen Anbietern der Windows- und Linux-Ökosysteme unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9104b-121">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="9104b-122">(Microsoft ist einer der wichtigsten Cloudanbieter, die Docker unterstützen.) In Zukunft wird Docker wahrscheinlich in jedem lokalen oder Cloud-Datencenter allgegenwärtig sein.</span><span class="sxs-lookup"><span data-stu-id="9104b-122">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="9104b-123">Darüber hinaus hat sich die [Microservices](https://martinfowler.com/articles/microservices.html)-Architektur zu einem wichtigen Ansatz für verteilte unternehmenskritische Anwendungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="9104b-123">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="9104b-124">In einer auf Microservice basierenden Architektur wird die Anwendung auf einer Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, bereitgestellt und mit Versionsangabe versehen werden können.</span><span class="sxs-lookup"><span data-stu-id="9104b-124">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="9104b-125">Über diesen Leitfaden</span><span class="sxs-lookup"><span data-stu-id="9104b-125">About this guide</span></span>

<span data-ttu-id="9104b-126">Dieser Leitfaden ist eine Einführung in das Entwickeln von auf Microservices basierenden Anwendung und das Verwalten derselben mithilfe von Containern.</span><span class="sxs-lookup"><span data-stu-id="9104b-126">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="9104b-127">Er erläutert das Architekturdesign und Implementierungsansätze mithilfe von .NET Core und Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="9104b-127">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="9104b-128">Um den Einstieg in Container und Microservices einfacher zu gestalten, konzentriert sich der Leitfaden auf eine auf Containern und Microservice basierende Verweisanwendung, die Sie erforschen können.</span><span class="sxs-lookup"><span data-stu-id="9104b-128">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="9104b-129">Die Beispielanwendung ist im [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)-GitHub-Repository verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9104b-129">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="9104b-130">Dieser Leitfaden enthält in erster Linie grundlegende Entwicklungs- und Architekturrichtlinien auf Ebene der Entwicklungsumgebung mit einem Schwerpunkt auf zwei Technologien: Docker und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9104b-130">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="9104b-131">Dieser Leitfaden ist dafür gedacht, dass Sie ihn lesen, wenn Sie über das Design Ihrer Anwendung nachdenken, ohne sich auf die Infrastruktur (Cloud oder lokal) Ihrer Produktionsumgebung zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="9104b-131">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="9104b-132">Die Entscheidung über Ihre Infrastruktur treffen Sie später, wenn Sie Ihre produktionsbereiten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9104b-132">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="9104b-133">Deshalb ignoriert dieser Leitfaden die Infrastruktur und konzentriert sich auf die Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="9104b-133">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="9104b-134">Der nächste Schritt nach dem Durcharbeiten dieses Leitfadens ist der, mehr über produktionsbereite Microservices in Microsoft Azure zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="9104b-134">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="9104b-135">Version</span><span class="sxs-lookup"><span data-stu-id="9104b-135">Version</span></span>

<span data-ttu-id="9104b-136">Dieser Leitfaden wurde für Version **.NET Core 3.1** überarbeitet und enthält viele weitere Updates zu artverwandten Technologien (also Azure und Drittanbietertechnologien), die zeitgleich mit dem.NET Core 3.1-Release veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="9104b-136">This guide has been revised to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span> <span data-ttu-id="9104b-137">Aus diesem Grund wurde auch die Versionsnummer des Leitfadens auf Version **3.1** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9104b-137">That’s why the book version has also been updated to version **3.1**.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="9104b-138">Was in diesem Leitfaden nicht behandelt wird</span><span class="sxs-lookup"><span data-stu-id="9104b-138">What this guide does not cover</span></span>

<span data-ttu-id="9104b-139">Dieser Leitfaden konzentriert sich nicht auf den Lebenszyklus der Anwendung, DevOps, CI/CD-Pipelines oder Teamarbeit.</span><span class="sxs-lookup"><span data-stu-id="9104b-139">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="9104b-140">Der komplementäre Leitfaden [Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools)](https://aka.ms/dockerlifecycleebook) konzentriert sich auf dieses Thema.</span><span class="sxs-lookup"><span data-stu-id="9104b-140">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="9104b-141">Der aktuelle Leitfaden enthält ebenfalls keine Details zu der Implementierung in die Azure-Infrastruktur, z.B. Informationen zu bestimmten Koordinatoren.</span><span class="sxs-lookup"><span data-stu-id="9104b-141">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9104b-142">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9104b-142">Additional resources</span></span>

- <span data-ttu-id="9104b-143">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools) (E-Book zum Download)</span><span class="sxs-lookup"><span data-stu-id="9104b-143">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="9104b-144">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="9104b-144">Who should use this guide</span></span>

<span data-ttu-id="9104b-145">Dieser Leitfaden wurde für Entwickler und Lösungsarchitekten geschrieben, die mit der Entwicklung von auf Docker basierenden Anwendungen und mit der auf Microservices basierenden Architektur noch nicht vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="9104b-145">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="9104b-146">Dieser Leitfaden ist für Sie geeignet, wenn Sie mehr über das Entwickeln, Entwerfen und Implementieren von Machbarkeitsstudienanwendungen mit den Entwicklungstechnologien von Microsoft (mit Schwerpunkt auf .NET Core) und mit Docker-Containern erfahren möchten.</span><span class="sxs-lookup"><span data-stu-id="9104b-146">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="9104b-147">Außerdem kann dieser Leitfaden hilfreich für Sie sein, wenn Sie ein technischer Entscheidungsträger sind, z.B. ein Unternehmensarchitekt, der einen Überblick über die Architektur und Technologie erhalten möchte, bevor über einen Ansatz für neue und moderne verteilte Anwendungen entschieden wird.</span><span class="sxs-lookup"><span data-stu-id="9104b-147">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="9104b-148">So verwenden Sie diesen Leitfaden</span><span class="sxs-lookup"><span data-stu-id="9104b-148">How to use this guide</span></span>

<span data-ttu-id="9104b-149">Im ersten Teil dieses Leitfadens werden Docker-Container vorgestellt. Außerdem wird erläutert, wie zwischen .NET Core und .NET Framework als Entwicklungsframework gewählt werden kann und ein Überblick über Microservices bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9104b-149">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="9104b-150">Dieser Inhalt ist an Architekten und technische Entscheidungsträger gerichtet, die sich einen Überblick verschaffen möchten, aber sich nicht auf die Details zur Implementierung des Codes konzentrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9104b-150">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="9104b-151">Der zweite Teil dieses Leitfadens beginnt mit dem Abschnitt [Development Process for Docker Based Applications (Entwicklungsprozess für auf Docker basierende Anwendungen)](./docker-application-development-process/index.md).</span><span class="sxs-lookup"><span data-stu-id="9104b-151">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="9104b-152">Der Schwerpunkt liegt auf den Mustern für die Entwicklung und Microservices, um Anwendungen mithilfe von .NET Core und Docker zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9104b-152">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="9104b-153">Dieser Abschnitt ist am besten für Entwickler und Architekten geeignet, die sich auf den Code, auf Muster und auf Implementierungsdetails konzentrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9104b-153">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="9104b-154">Verknüpfte auf Microservice und Containern basierende Verweisanwendung: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="9104b-154">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="9104b-155">Bei der eShopOnContainers-Anwendung handelt es sich um eine Open-Source-Referenz-App für .NET Core und Microservices, die für die Bereitstellung mithilfe von Docker-Containern entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9104b-155">The eShopOnContainers application is an open-source reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="9104b-156">Die Anwendung besteht aus mehreren Subsystemen, einschließlich mehrerer Front-Ends der E-Store-Benutzeroberfläche (eine Web-MVC-App, eine Web-SPA und eine native mobile App).</span><span class="sxs-lookup"><span data-stu-id="9104b-156">The application consists of multiple subsystems, including several e-store UI front ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="9104b-157">Sie enthält ebenfalls den Back-End-Microservice und Container für alle erforderlichen serverseitigen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="9104b-157">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="9104b-158">Der Zweck der Anwendung besteht in der Präsentation von Architekturmustern.</span><span class="sxs-lookup"><span data-stu-id="9104b-158">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="9104b-159">**SIE STELLT KEINE PRODUKTIONSBEREITE VORLAGE DAR**, die sich als Ausgangspunkt für reale Anwendungen eignet.</span><span class="sxs-lookup"><span data-stu-id="9104b-159">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="9104b-160">Tatsächlich befindet sich die Anwendung in einem dauerhaften Betastadium, da sie ebenfalls zum Testen neuer, potenziell interessanter Technologien direkt bei ihrem Erscheinen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9104b-160">In fact, the application is in a permanent beta state, as it’s also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="9104b-161">Senden Sie uns Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="9104b-161">Send us your feedback!</span></span>

<span data-ttu-id="9104b-162">Dieser Leitfaden wurde geschrieben, um Ihnen die Architektur von Containeranwendungen und Microservices in .NET näherzubringen.</span><span class="sxs-lookup"><span data-stu-id="9104b-162">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="9104b-163">Der Leitfaden und die verknüpfte Verweisanwendung werden weiterentwickelt. Wir freuen uns über Ihr Feedback!</span><span class="sxs-lookup"><span data-stu-id="9104b-163">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="9104b-164">Wenn Sie Kommentare dazu haben, wie dieser Leitfaden verbessert werden kann, senden Sie Ihr Feedback bitte an <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="9104b-164">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="9104b-165">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="9104b-165">Credits</span></span>

<span data-ttu-id="9104b-166">Mitautoren:</span><span class="sxs-lookup"><span data-stu-id="9104b-166">Co-Authors:</span></span>

> <span data-ttu-id="9104b-167">**Cesar de la Torre**, leitender PM, .NET-Produktteam, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="9104b-167">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="9104b-168">**Bill Wagner**, leitender Inhaltsentwickler, C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="9104b-168">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="9104b-169">**Mike Rousos**, leitender Softwareentwickler, DevDiv CAT-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-169">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="9104b-170">Editoren:</span><span class="sxs-lookup"><span data-stu-id="9104b-170">Editors:</span></span>

> <span data-ttu-id="9104b-171">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="9104b-171">**Mike Pope**</span></span>
>
> <span data-ttu-id="9104b-172">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="9104b-172">**Steve Hoag**</span></span>

<span data-ttu-id="9104b-173">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="9104b-173">Participants and reviewers:</span></span>

> <span data-ttu-id="9104b-174">**Jeffrey Richter**, Partner Software Engineer, Azure-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-174">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-175">**Jimmy Bogard**, leitender Architekt bei Headspring</span><span class="sxs-lookup"><span data-stu-id="9104b-175">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="9104b-176">**Udi Dahan**, Gründer & CEO, bestimmte Software</span><span class="sxs-lookup"><span data-stu-id="9104b-176">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="9104b-177">**Jimmy Nilsson**, Mitgründer und CEO von Factor10</span><span class="sxs-lookup"><span data-stu-id="9104b-177">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="9104b-178">**Glenn Condron**, leitender Programm-Manager, ASP.NET-Team</span><span class="sxs-lookup"><span data-stu-id="9104b-178">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="9104b-179">**Mark Fussell**, PM-Teamleiter, Azure Service Fabric-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-179">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-180">**Diego Vega**, PM-Teamleiter, Entity Framework-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-180">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-181">**Barry Dorrans**, leitender Sicherheitsprogramm-Manager</span><span class="sxs-lookup"><span data-stu-id="9104b-181">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="9104b-182">**Rowan Miller**, leitender Programm-Manager, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-182">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="9104b-183">**Ankit Asthana**, leitender PM-Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-183">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-184">**Scott Hunter**, Partner Director von PM, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-184">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-185">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-185">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-186">**Dylan Reisenberger**, Architekt und Entwicklungsleiter bei Polly</span><span class="sxs-lookup"><span data-stu-id="9104b-186">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="9104b-187">**Steve „ardalis“ Smith** – Softwarearchitekt und Trainer – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="9104b-187">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="9104b-188">**Ian Cooper**, Codearchitekt bei Brighter</span><span class="sxs-lookup"><span data-stu-id="9104b-188">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="9104b-189">**Unai Zorrilla**, Architekt und Entwicklungsleiter bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="9104b-189">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="9104b-190">**Eduard Tomas**, Entwicklungsleiter bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="9104b-190">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="9104b-191">**Ramon Tomas**, Entwickler bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="9104b-191">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="9104b-192">**David Sanz**, Entwickler bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="9104b-192">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="9104b-193">**Javier Valero**, Chief Operating Officer bei Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="9104b-193">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="9104b-194">**Pierre Millet**, leitender Berater, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-194">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="9104b-195">**Michael Friis**, Produktmanager, Docker Inc</span><span class="sxs-lookup"><span data-stu-id="9104b-195">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="9104b-196">**Charles Lowell**, Softwareentwickler, VS CAT-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9104b-196">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="9104b-197">**Miguel Veloso**, Software Development Engineer bei Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="9104b-197">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>

## <a name="copyright"></a><span data-ttu-id="9104b-198">Copyright</span><span class="sxs-lookup"><span data-stu-id="9104b-198">Copyright</span></span>

<span data-ttu-id="9104b-199">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="9104b-199">PUBLISHED BY</span></span>

<span data-ttu-id="9104b-200">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="9104b-200">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="9104b-201">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9104b-201">A division of Microsoft Corporation</span></span>

<span data-ttu-id="9104b-202">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9104b-202">One Microsoft Way</span></span>

<span data-ttu-id="9104b-203">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="9104b-203">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="9104b-204">Copyright © 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9104b-204">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="9104b-205">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="9104b-205">All rights reserved.</span></span> <span data-ttu-id="9104b-206">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9104b-206">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="9104b-207">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="9104b-207">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="9104b-208">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9104b-208">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="9104b-209">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="9104b-209">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="9104b-210">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="9104b-210">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="9104b-211">Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="9104b-211">Microsoft and the trademarks listed at <https://www.microsoft.com> on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="9104b-212">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="9104b-212">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="9104b-213">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="9104b-213">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="9104b-214">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="9104b-214">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="9104b-215">Nächste</span><span class="sxs-lookup"><span data-stu-id="9104b-215">Next</span></span>](container-docker-introduction/index.md)
