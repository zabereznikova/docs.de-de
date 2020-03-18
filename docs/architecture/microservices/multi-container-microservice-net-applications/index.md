---
title: Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Grundlegendes zur externen Architektur für das Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren
ms.date: 10/02/2018
ms.openlocfilehash: 8c2f828e9913a0efcdf580371124b0f624daeffe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70295228"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren

*Das Entwickeln von Containeranwendungen mit Microservice bedeutet, dass Sie Anwendungen mit mehreren Containern erstellen. Eine Anwendung mit mehreren Containern kann jedoch auch einfacher sein, beispielsweise eine Anwendung mit drei Ebenen und muss nicht mithilfe einer Microservice-Architektur erstellt werden.*

Zuvor wurde die Frage aufgeworfen, ob Docker erforderlich ist, um eine Microservice-Architektur zu erstellen. Die Antwort ist ein klares Nein. Docker ist ein Hilfsmittel, das bedeutende Vorteile bietet. Container und Docker sind jedoch keine festen Anforderungen für Microservices. Sie können beispielsweise eine auf Microservices basierende Anwendung mit oder ohne Docker erstellen, wenn Sie Azure Service Fabric verwenden. Dies unterstützt das Ausführen von Microservices als einfache Prozesse oder als Docker-Container.

Wenn Sie jedoch eine auf Microservices und Docker-Containern basierte Anwendung entwerfen und entwickeln können, können Sie auch ein anderes, einfacheres Anwendungsmodell entwerfen und entwickeln. Sie können beispielsweise eine Anwendung mit drei Ebenen entwerfen, für die mehrere Container erforderlich sind. Deshalb, und weil Microservice-Architekturen ein wichtiger Trend innerhalb der Container-Welt sind, konzentriert sich dieser Abschnitt auf die Implementierung von Microservice-Architekturen mithilfe von Docker-Containern.

>[!div class="step-by-step"]
>[Zurück](../docker-application-development-process/docker-app-development-workflow.md)
>[Weiter](microservice-application-design.md)
