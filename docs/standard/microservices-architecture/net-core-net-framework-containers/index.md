---
title: Wahl zwischen .NET Core und .NET Framework für Docker-Container
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Wahl zwischen .NET Core und .NET Framework für Docker-Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 0f6689468eda1dd1b12c24927e650b2b01381274
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104441"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="9fa90-103">Wahl zwischen .NET Core und .NET Framework für Docker-Container</span><span class="sxs-lookup"><span data-stu-id="9fa90-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="9fa90-104">Bei der Erstellung von serverseitigen Containeranwendungen von Docker mit .NET werden zwei Implementierungen unterstützt: [.NET Framework](https://www.microsoft.com/net/download/framework) und [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="9fa90-104">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="9fa90-105">Sie nutzen viele .NET Standard-Komponenten, und Sie können Code über beide hinweg nutzen.</span><span class="sxs-lookup"><span data-stu-id="9fa90-105">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="9fa90-106">Allerdings gibt es auch grundlegende Unterschiede zwischen den beiden Komponenten, daher richtet sich die Entscheidung, welche Sie verwenden, nach dem, was Sie erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="9fa90-106">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="9fa90-107">Dieser Abschnitt bietet Ihnen Unterstützung bei der Entscheidung, wann jede Implementierung ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fa90-107">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="9fa90-108">[Zurück](../container-docker-introduction/docker-containers-images-registries.md)
[Weiter](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="9fa90-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
