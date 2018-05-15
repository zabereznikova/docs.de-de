---
title: Wahl zwischen .NET Core und .NET Framework für Docker-Container
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Wahl zwischen .NET Core und .NET Framework für Docker-Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: b483214e7bd039a71ae642aa26e69d63222af8ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="b734e-103">Wahl zwischen .NET Core und .NET Framework für Docker-Container</span><span class="sxs-lookup"><span data-stu-id="b734e-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="b734e-104">Bei der Erstellung von serverseitigen Containeranwendungen von Docker mit .NET werden zwei Implementierungen unterstützt: [.NET Framework](https://www.microsoft.com/net/download/framework) und [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="b734e-104">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="b734e-105">Sie nutzen viele .NET Standard-Komponenten, und Sie können Code über beide hinweg nutzen.</span><span class="sxs-lookup"><span data-stu-id="b734e-105">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="b734e-106">Allerdings gibt es auch grundlegende Unterschiede zwischen den beiden Komponenten, daher richtet sich die Entscheidung, welche Sie verwenden, nach dem, was Sie erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="b734e-106">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="b734e-107">Dieser Abschnitt bietet Ihnen Unterstützung bei der Entscheidung, wann jede Implementierung ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b734e-107">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b734e-108">[Zurück] (../container-docker-introduction/docker-containers-images-registries.md) [Weiter] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="b734e-108">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
