---
title: Entwerfen von Docker-Anwendungen
description: Referenz zu einem tiefgreifenden Leitfaden zur Architektur von Microservices, da dieses Thema in diesem Leitfaden nicht ausführlich behandelt wird.
ms.date: 02/15/2019
ms.openlocfilehash: 535b6cefb7371014527032972ec27ebfe4b67ebc
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644689"
---
# <a name="design-docker-applications"></a>Entwerfen von Docker-Anwendungen

In Kapitel 1 wurden die grundlegenden Konzepte zu Containern und Docker vorgestellt. Diese Informationen bilden die erforderliche Basis für Ihren Einstieg. Unternehmensanwendungen können allerdings komplex sein und bestehen oftmals aus mehreren Diensten statt aus einem einzelnen Dienst oder Container. Für diese optionalen Anwendungsfälle müssen Sie weitere Entwurfsansätze, wie etwa die dienstorientierte Architektur (Service-Oriented Architecture, SOA) und die höher entwickelten Konzepte für Microservices und Containerorchestrierung kennen. Der Umfang dieses Dokuments ist nicht auf Microservices beschränkt, sondern befasst sich mit dem Lebenszyklus beliebiger Docker-Anwendungen, daher wird die Microservicearchitektur nicht tiefgreifend behandelt, da Sie Container und Cocker auch in Kombination mit gewöhnlicher SOA, mit Hintergrundaufgaben oder Aufträgen oder sogar mit monolithischen Ansätzen zur Anwendungsbereitstellung verwenden können.

**Weitere Informationen** Weitere, ausführliche Informationen zu Unternehmensanwendungen und Microservicearchitektur finden Sie in dem Leitfaden [NET Microservices: Architecture for Containerized .NET Applications](../../microservices-architecture/index.md) (NET-Microservices: Architektur für containerbasierte .NET-Anwendungen), den Sie auch von <https://aka.ms/MicroservicesEbook> herunterladen können.

Bevor wir uns allerdings mit dem Anwendungslebenszyklus und DevOps befassen, müssen wir wissen, wie Sie Ihre Anwendung entwerfen und konstruieren möchten und welche Entwurfsoptionen sich Ihnen bieten.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](common-container-design-principles.md)
