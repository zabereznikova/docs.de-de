---
title: Dienstorientierte Architektur
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Dienstorientierte Architektur"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a>Dienstorientierte Architektur 

Dienstorientierte Architektur (SOA) wurde ein Überbelastung Begriff und verfügt über verschiedene Bedeutungen für verschiedene Benutzer vorgesehen. Jedoch als einen gemeinsamen Nenner SOA bedeutet, dass Sie Strukturieren Ihrer Anwendung durch zerlegen es in mehrere Dienste (meist als HTTP-Dienste), die als unterschiedliche Typen wie Subsysteme oder Ebenen klassifiziert werden können.

Diese Dienste können nun als Docker-Container bereitgestellt werden die löst Bereitstellungsprobleme, da alle Abhängigkeiten in den Container-Abbild einbezogen werden. Wenn Sie jedoch zentrale Skalieren von SOA-Anwendungen werden müssen Sie möglicherweise die Skalierbarkeit und Verfügbarkeit Herausforderungen bei der Bereitstellung auf der Grundlage von einzelnen Docker-Hosts. Dies ist, bei denen sich Software- oder ein Orchestrator-clustering Docker beitragen, Sie, wie in späteren Abschnitten beschrieben, in denen wir Bereitstellung Ansätze zum Microservices beschreiben.

Docker-Containern sind nützlich, (aber nicht erforderlich) für herkömmliche dienstorientierten Architekturen und die erweiterten Microservices-Architekturen.

Microservices abgeleitet SOA, aber SOA unterscheidet sich vom Microservices-Architektur. Funktionen wie große zentralen Brokern, zentralen Orchestrators auf Ebene der Organisation und die [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) SOA, das typisch sind. Aber in den meisten Fällen sind diese Antimuster in der Microservice-Community. Einige Benutzer in der Tat argumentieren, "die Architektur Microservice SOA richtig ist."

Dieses Handbuch bezieht sich auf Microservices, da ein SOA-Ansatzes kleiner als die Anforderungen und Techniken, mit denen in einer Architektur mit Microservice normativen ist. Wenn Sie wissen, wie eine Microservice-basierte Anwendung erstellen, wissen Sie auch wie eine einfachere dienstorientierten Anwendung erstellt.




>[!div class="step-by-step"]
[Vorherigen] (Docker-Anwendung-Status-data.md) [weiter] (Microservices architecture.md)
