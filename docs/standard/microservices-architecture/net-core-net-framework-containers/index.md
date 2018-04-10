---
title: Wahl zwischen .NET Core und .NET Framework für Docker-Container
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Wahl zwischen .NET Core und .NET Framework für Docker-Container
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 60d21de06262a14f9be6a1a5ce80edf15ddf1b59
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="c9fdb-104">Wahl zwischen .NET Core und .NET Framework für Docker-Container</span><span class="sxs-lookup"><span data-stu-id="c9fdb-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="c9fdb-105">Bei der Erstellung von serverseitigen Containeranwendungen von Docker mit .NET werden zwei Implementierungen unterstützt: [.NET Framework](https://www.microsoft.com/net/download/framework) und [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="c9fdb-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="c9fdb-106">Sie nutzen viele .NET Standard-Komponenten, und Sie können Code über beide hinweg nutzen.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="c9fdb-107">Allerdings gibt es auch grundlegende Unterschiede zwischen den beiden Komponenten, daher richtet sich die Entscheidung, welche Sie verwenden, nach dem, was Sie erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="c9fdb-108">Dieser Abschnitt bietet Ihnen Unterstützung bei der Entscheidung, wann jede Implementierung ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c9fdb-109">[Zurück] (../container-docker-introduction/docker-containers-images-registries.md) [Weiter] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="c9fdb-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
