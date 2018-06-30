---
title: Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 13abff090d42c5d59476612942560c126836dbb0
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104477"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="c12db-103">Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren</span><span class="sxs-lookup"><span data-stu-id="c12db-103">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="c12db-104">*Das Entwickeln von Containeranwendungen mit Microservice bedeutet, dass Sie Anwendungen mit mehreren Containern erstellen. Eine Anwendung mit mehreren Containern kann jedoch auch einfacher sein, beispielsweise eine Anwendung mit drei Ebenen und muss nicht mithilfe einer Microservice-Architektur erstellt werden.*</span><span class="sxs-lookup"><span data-stu-id="c12db-104">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="c12db-105">Zuvor wurde die Frage gestellt, ob Docker erforderlich ist, um eine Microservice-Architektur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c12db-105">Earlier we raised the question “Is Docker necessary when building a microservice architecture?”</span></span> <span data-ttu-id="c12db-106">Die Antwort ist ein klares Nein.</span><span class="sxs-lookup"><span data-stu-id="c12db-106">The answer is a clear no.</span></span> <span data-ttu-id="c12db-107">Docker ist ein Hilfsmittel, das bedeutende Vorteile bietet. Container und Docker sind jedoch keine festen Anforderungen für Microservices.</span><span class="sxs-lookup"><span data-stu-id="c12db-107">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="c12db-108">Sie können beispielsweise eine auf Microservices basierende Anwendung mit oder ohne Docker erstellen, wenn Sie Azure Service Fabric verwenden. Dies unterstützt das Ausführen von Microservices als einfache Prozesse oder als Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="c12db-108">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="c12db-109">Wenn Sie jedoch eine auf Microservices und Docker-Containern basierte Anwendung entwerfen und entwickeln können, können Sie auch ein anderes, einfacheres Anwendungsmodell entwerfen und entwickeln.</span><span class="sxs-lookup"><span data-stu-id="c12db-109">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="c12db-110">Sie können beispielsweise eine Anwendung mit drei Ebenen entwerfen, für die mehrere Container erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c12db-110">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="c12db-111">Deshalb, und weil Microservice-Architekturen ein wichtiger Trend innerhalb der Container-Welt sind, konzentriert sich dieser Abschnitt auf die Implementierung von Microservice-Architekturen mithilfe von Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="c12db-111">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c12db-112">[Zurück](../containerize-net-framework-applications/index.md)
[Weiter](microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="c12db-112">[Previous](../containerize-net-framework-applications/index.md)
[Next](microservice-application-design.md)</span></span>
