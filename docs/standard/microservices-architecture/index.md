---
title: ".NET-Microservices. .NET-Microservices-Architektur für .NET-Containeranwendungen"
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Titelei"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f869656be4c211c9b028f8ac574eb3bf2de139e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
![](./media/cover.png)

# <a name="net-microservices-architecture-for-containerized-net-applications"></a>.NET-Microservices. .NET-Microservices-Architektur für .NET-Containeranwendungen

DOWNLOAD verfügbar auf: <https://aka.ms/microservicesebook>

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2017 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter http://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Mitautoren:

> **Cesar de la Torre**, Sr. PM, .NET-Produktionsteam, Microsoft Corp.
>
> **Bill Wagner**, Sr. Inhaltsentwickler, C+E, Microsoft Corp.
>
> **Mike Rousos**, leitender Softwareentwickler, DevDiv CAT-Team, Microsoft

Editoren:

> **Mike Pope**
>
> **Steve Hoag**

Teilnehmer und Prüfer:

> **Jeffrey Ritcher**, Entwickler von Partnersoftware, Azure-Team, Microsoft
>
> **Jimmy Bogard**, leitender Architekt bei Headspring
>
> **Udi Dahan**, Gründer & CEO, bestimmte Software
>
> **Jimmy Nilsson**, Mitgründer und CEO von Factor10
>
> **Glenn Condron**, Sr. Programmmanager, ASP.NET-Team
>
> **Mark Fussell**, PM-Teamleiter, Azure Service Fabric-Team, Microsoft
>
> **Diego Vega**, PM-Teamleiter, Entity Framework-Team, Microsoft
>
> **Barry Dorrans**, Sr. Manager für das Sicherheitsprogramm
>
> **Rowan Miller**, Sr. Programmmanager, Microsoft
>
> **Ankit Asthana**, leitender PM-Manager, .NET-Team, Microsoft
>
> **Scott Hunter**, Partner Director von PM, .NET-Team, Microsoft
>
> **Dylan Reisenberger**, Architekt und Entwicklungsleiter bei Polly
>
> **Steve Smith**, Softwarespezialist & Trainer bei ASPSmith Ltd.
>
> **Ian Cooper**, Codearchitekt bei Brighter
>
> **Unai Zorrilla**, Architekt und Entwicklungsleiter bei Plain Concepts
>
> **Eduard Tomas**, Entwicklungsleiter bei Plain Concepts
>
> **Ramon Tomas**, Entwickler bei Plain Concepts
>
> **David Sanz**, Entwickler bei Plain Concepts
>
> **Javier Valero**, Chief Operating Officer bei Grupo Solutio
>
> **Pierre Millet**, Sr. Berater, Microsoft
>
> **Michael Friis**, Produktmanager, Docker Inc
>
> **Charles Lowell**, Softwareentwickler, VS CAT-Team, Microsoft

## <a name="introduction"></a>Einführung

Unternehmen sparen zunehmend Kosten, lösen Entwicklungsprobleme und verbessern DevOps und Produktvorgänge durch das Verwenden von Containern. Microsoft hat durch das Erstellen von Produkten wie Azure Container Service und Azure Service Fabric sowie durch die Partnerschaft mit Marktführern wie Docker, Mesosphere und Kubernetes Containerinnovationen für Linux und Windows veröffentlicht. Diese Produkte stellen Containerlösungen bereit, die Unternehmen beim Erstellen und Bereitstellen von Anwendungen mit Cloudgeschwindigkeit und im Cloudmaßstab unterstützen, unabhängig von der Wahl ihrer Plattformen oder Tools.

Docker entwickelt sich praktisch zum Standard in der Containerindustrie und wird von den meisten wichtigen Anbietern der Windows- und Linux-Ökosysteme unterstützt. (Microsoft ist einer der wichtigsten Cloudanbieter, die Docker unterstützen.) In Zukunft wird Docker wahrscheinlich in jedem lokalen oder Cloud-Datencenter allgegenwärtig sein.

Darüber hinaus hat sich die [Microservices](https://martinfowler.com/articles/microservices.html)-Architektur zu einem wichtigen Ansatz für verteilte unternehmenskritische Anwendungen entwickelt. In einer auf Microservice basierenden Architektur wird die Anwendung auf einer Sammlung von Diensten erstellt, die unabhängig entwickelt, getestet, bereitgestellt und mit Versionsangabe versehen werden können.

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieser Leitfaden ist eine Einführung in das Entwickeln von auf Microservices basierenden Anwendung und das Verwalten derselben mithilfe von Containern. Er erläutert das Architekturdesign und Implementierungsansätze mithilfe von .NET Core und Docker-Containern. Um den Einstieg in Container und Microservices einfacher zu gestalten, konzentriert sich der Leitfaden auf eine auf Containern und Microservice basierende Verweisanwendung, die Sie erforschen können. Die Beispielanwendung ist im [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)-GitHub-Repository verfügbar.

Dieser Leitfaden enthält in erster Linie grundlegende Entwicklungs- und Architekturrichtlinien auf Ebene der Entwicklungsumgebung mit einem Schwerpunkt auf zwei Technologien: Docker und .NET Core. Dieser Leitfaden ist dafür gedacht, dass Sie ihn lesen, wenn Sie über das Design Ihrer Anwendung nachdenken, ohne sich auf die Infrastruktur (Cloud oder lokal) Ihrer Produktionsumgebung zu konzentrieren. Die Entscheidung über Ihre Infrastruktur treffen Sie später, wenn Sie Ihre produktionsbereiten Anwendungen erstellen. Deshalb ignoriert dieser Leitfaden die Infrastruktur und konzentriert sich auf die Entwicklungsumgebung.

Der nächste Schritt nach dem Durcharbeiten dieses Leitfadens ist der, mehr über produktionsbereite Microservices in Microsoft Azure zu erfahren.

## <a name="what-this-guide-does-not-cover"></a>Was in diesem Leitfaden nicht behandelt wird

Dieser Leitfaden konzentriert sich nicht auf den Lebenszyklus der Anwendung, DevOps, CI/CD-Pipelines oder Teamarbeit. Der komplementäre Leitfaden [Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools)](https://aka.ms/dockerlifecycleebook) konzentriert sich auf dieses Thema. Der aktuelle Leitfaden enthält ebenfalls keine Details zu der Implementierung in die Azure-Infrastruktur, z.B. Informationen zu bestimmten Koordinatoren.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Containerisierter Docker-Anwendungslebenszyklus mit Microsoft-Plattform und -Tools** (herunterladbares E-Book): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieser Leitfaden wurde für Entwickler und Lösungsarchitekten geschrieben, die mit der Entwicklung von auf Docker basierenden Anwendungen und mit der auf Microservices basierenden Architektur noch nicht vertraut sind. Dieser Leitfaden ist für Sie geeignet, wenn Sie mehr über das Entwickeln, Entwerfen und Implementieren von Machbarkeitsstudienanwendungen mit den Entwicklungstechnologien von Microsoft (mit Schwerpunkt auf .NET Core) und mit Docker-Containern erfahren möchten.

Außerdem kann dieser Leitfaden hilfreich für Sie sein, wenn Sie ein technischer Entscheidungsträger sind, z.B. ein Unternehmensarchitekt, der einen Überblick über die Architektur und Technologie erhalten möchte, bevor über einen Ansatz für neue und moderne verteilte Anwendungen entschieden wird.

### <a name="how-to-use-this-guide"></a>So verwenden Sie diesen Leitfaden

Im ersten Teil dieses Leitfadens werden Docker-Container vorgestellt. Außerdem wird erläutert, wie zwischen .NET Core und .NET Framework als Entwicklungsframework gewählt werden kann und ein Überblick über Microservices bereitgestellt. Dieser Inhalt ist an Architekten und technische Entscheidungsträger gerichtet, die sich einen Überblick verschaffen möchten, aber sich nicht auf die Details zur Implementierung des Codes konzentrieren müssen.

Der zweite Teil dieses Leitfadens beginnt mit dem Abschnitt [Development Process for Docker Based Applications (Entwicklungsprozess für auf Docker basierende Anwendungen)](#ch_dev_process_for_docker_based_apps). Der Schwerpunkt liegt auf den Mustern für die Entwicklung und Microservices, um Anwendungen mithilfe von .NET Core und Docker zu implementieren. Dieser Abschnitt ist am besten für Entwickler und Architekten geeignet, die sich auf den Code, auf Muster und auf Implementierungsdetails konzentrieren möchten.

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a>Verknüpfte auf Microservice und Containern basierende Verweisanwendung: eShopOnContainers

Bei der eShopOnContainers-Anwendung handelt es sich um eine Verweis-App für .NET Core und Microservices, die für die Bereitstellung mithilfe von Docker-Containern entwickelt wurde. Die Anwendung besteht aus mehreren Subsystemen, einschließlich mehrerer Front-Ends der E-Store-UI (eine Web-App und eine native mobile App). Sie enthält ebenfalls den Back-End-Microservice und Container für alle erforderlichen serverseitigen Vorgänge.

Der Quellcode dieser auf Microservice und Containern basierenden Anwendung ist Open Source und verfügbar im [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)-GitHub-Repository.

## <a name="send-us-your-feedback"></a>Senden Sie uns Ihr Feedback!

Dieser Leitfaden wurde geschrieben, um Ihnen die Architektur von Containeranwendungen und Microservices in .NET näherzubringen. Der Leitfaden und die verknüpfte Verweisanwendung werden weiterentwickelt. Wir freuen uns über Ihr Feedback! Wenn Sie Kommentare dazu haben, wie dieser Leitfaden verbessert werden kann, senden Sie diese bitte an:

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

>[!div class="step-by-step"]
[Weiter] (container-docker-introduction/index.md)
