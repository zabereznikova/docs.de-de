---
title: Entwerfen von Docker-Anwendungen
description: Referenz zu einem tiefgreifenden Leitfaden zur Architektur von Microservices, da dieses Thema in diesem Leitfaden nicht ausführlich behandelt wird.
ms.date: 08/06/2020
ms.openlocfilehash: b63d4344abb358a393587bdacf91f6091b531af0
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915976"
---
# <a name="design-docker-applications"></a>Entwerfen von Docker-Anwendungen

In Kapitel 1 wurden die grundlegenden Konzepte zu Containern und Docker vorgestellt. Diese Informationen bilden die erforderliche Basis für Ihren Einstieg. Unternehmensanwendungen können allerdings komplex sein und bestehen oftmals aus mehreren Diensten statt aus einem einzelnen Dienst oder Container. Für diese optionalen Anwendungsfälle müssen Sie weitere Entwurfsansätze, wie etwa die dienstorientierte Architektur (Service-Oriented Architecture, SOA) und die höher entwickelten Konzepte für Microservices und Containerorchestrierung kennen. Der Umfang dieses Dokuments ist nicht auf Microservices beschränkt, sondern befasst sich mit dem Lebenszyklus beliebiger Docker-Anwendungen, daher wird die Microservicearchitektur nicht tiefgreifend behandelt, da Sie Container und Cocker auch in Kombination mit gewöhnlicher SOA, mit Hintergrundaufgaben oder Aufträgen oder sogar mit monolithischen Ansätzen zur Anwendungsbereitstellung verwenden können.

**Weitere Informationen** Weitere, ausführliche Informationen zu Unternehmensanwendungen und Microservicearchitektur finden Sie in dem Leitfaden [.NET-Microservices:  .NET-Microservices-Architektur für .NET-Containeranwendungen](../../microservices/index.md) (NET-Microservices: Architektur für containerbasierte .NET-Anwendungen), den Sie auch von <https://aka.ms/MicroservicesEbook> herunterladen können.

Bevor Sie sich jedoch mit dem Anwendungslebenszyklus und DevOps befassen, müssen Sie wissen, wie Sie Ihre Anwendung entwerfen und erstellen möchten und welche Entwurfsoptionen verfügbar sind.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](common-container-design-principles.md)
