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
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="48417-104">Entwerfen und Entwickeln von .NET-Anwendungen, die auf mehreren Containern und Microservice basieren</span><span class="sxs-lookup"><span data-stu-id="48417-104">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="48417-105">*Das Entwickeln von Containeranwendungen mit Microservice bedeutet, dass Sie Anwendungen mit mehreren Containern erstellen. Eine Anwendung mit mehreren Containern kann jedoch auch einfacher sein, beispielsweise eine Anwendung mit drei Ebenen und muss nicht mithilfe einer Microservice-Architektur erstellt werden.*</span><span class="sxs-lookup"><span data-stu-id="48417-105">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="48417-106">Zuvor wurde die Frage gestellt, ob Docker erforderlich ist, um eine Microservice-Architektur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="48417-106">Earlier we raised the question “Is Docker necessary when building a microservice architecture?”</span></span> <span data-ttu-id="48417-107">Die Antwort ist ein klares Nein.</span><span class="sxs-lookup"><span data-stu-id="48417-107">The answer is a clear no.</span></span> <span data-ttu-id="48417-108">Docker ist ein Hilfsmittel, das bedeutende Vorteile bietet. Container und Docker sind jedoch keine festen Anforderungen für Microservices.</span><span class="sxs-lookup"><span data-stu-id="48417-108">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="48417-109">Sie können beispielsweise eine auf Microservices basierende Anwendung mit oder ohne Docker erstellen, wenn Sie Azure Service Fabric verwenden. Dies unterstützt das Ausführen von Microservices als einfache Prozesse oder als Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="48417-109">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="48417-110">Wenn Sie jedoch eine auf Microservices und Docker-Containern basierte Anwendung entwerfen und entwickeln können, können Sie auch ein anderes, einfacheres Anwendungsmodell entwerfen und entwickeln.</span><span class="sxs-lookup"><span data-stu-id="48417-110">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="48417-111">Sie können beispielsweise eine Anwendung mit drei Ebenen entwerfen, für die mehrere Container erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="48417-111">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="48417-112">Deshalb, und weil Microservice-Architekturen ein wichtiger Trend innerhalb der Container-Welt sind, konzentriert sich dieser Abschnitt auf die Implementierung von Microservice-Architekturen mithilfe von Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="48417-112">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="48417-113">[Zurück] (../containerize-net-framework-applications/index.md) [Weiter] (microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="48417-113">[Previous] (../containerize-net-framework-applications/index.md) [Next] (microservice-application-design.md)</span></span>
