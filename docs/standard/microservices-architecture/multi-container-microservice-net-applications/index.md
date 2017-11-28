---
title: Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 46d2859fa3b739b1a2a8b1502d4e418fab204648
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren

*Das Entwickeln von Containeranwendungen mit Microservice bedeutet, dass Sie Anwendungen mit mehreren Containern erstellen. Eine Anwendung mit mehreren Containern kann jedoch auch einfacher sein, beispielsweise eine Anwendung mit drei Ebenen und muss nicht mithilfe einer Microservice-Architektur erstellt werden.*

Zuvor wurde die Frage gestellt, ob Docker erforderlich ist, um eine Microservice-Architektur zu erstellen. Die Antwort ist ein klares Nein. Docker ist ein Hilfsmittel, das bedeutende Vorteile bietet. Container und Docker sind jedoch keine festen Anforderungen für Microservices. Sie können beispielsweise eine auf Microservices basierende Anwendung mit oder ohne Docker erstellen, wenn Sie Azure Service Fabric verwenden. Dies unterstützt das Ausführen von Microservices als einfache Prozesse oder als Docker-Container.

Wenn Sie jedoch eine auf Microservices und Docker-Containern basierte Anwendung entwerfen und entwickeln können, können Sie auch ein anderes, einfacheres Anwendungsmodell entwerfen und entwickeln. Sie können beispielsweise eine Anwendung mit drei Ebenen entwerfen, für die mehrere Container erforderlich sind. Deshalb, und weil Microservice-Architekturen ein wichtiger Trend innerhalb der Container-Welt sind, konzentriert sich dieser Abschnitt auf die Implementierung von Microservice-Architekturen mithilfe von Docker-Containern.


>[!div class="step-by-step"]
[Zurück] (../containerize-net-framework-applications/index.md) [Weiter] (microservice-application-design.md)
