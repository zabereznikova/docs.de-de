---
title: Entwerfen von Docker-Anwendungen
description: Referenz zu einem tiefgreifenden Leitfaden zur Architektur von Microservices, da dieses Thema in diesem Leitfaden nicht ausführlich behandelt wird.
ms.date: 02/15/2019
ms.openlocfilehash: b9539ff4edf405ab890d83be59a248ffa2360c99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674037"
---
# <a name="design-docker-applications"></a>Entwerfen von Docker-Anwendungen

In Kapitel 1 wurden die grundlegenden Konzepte zu Containern und Docker vorgestellt. Diese Informationen bilden die erforderliche Basis für Ihren Einstieg. Unternehmensanwendungen können allerdings komplex sein und bestehen oftmals aus mehreren Diensten statt aus einem einzelnen Dienst oder Container. Für diese optionalen Anwendungsfälle müssen Sie weitere Entwurfsansätze, wie etwa die dienstorientierte Architektur (Service-Oriented Architecture, SOA) und die höher entwickelten Konzepte für Microservices und Containerorchestrierung kennen. Der Umfang dieses Dokuments ist nicht auf Microservices beschränkt, sondern befasst sich mit dem Lebenszyklus beliebiger Docker-Anwendungen, daher wird die Microservicearchitektur nicht tiefgreifend behandelt, da Sie Container und Cocker auch in Kombination mit gewöhnlicher SOA, mit Hintergrundaufgaben oder Aufträgen oder sogar mit monolithischen Ansätzen zur Anwendungsbereitstellung verwenden können.

**Weitere Informationen** Weitere, ausführliche Informationen zu Unternehmensanwendungen und Microservicearchitektur finden Sie in dem Leitfaden [.NET-Microservices:  .NET-Microservices-Architektur für .NET-Containeranwendungen](../../microservices/index.md) (NET-Microservices: Architektur für containerbasierte .NET-Anwendungen), den Sie auch von <https://aka.ms/MicroservicesEbook> herunterladen können.

Bevor wir uns allerdings mit dem Anwendungslebenszyklus und DevOps befassen, müssen wir wissen, wie Sie Ihre Anwendung entwerfen und konstruieren möchten und welche Entwurfsoptionen sich Ihnen bieten.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](common-container-design-principles.md)
