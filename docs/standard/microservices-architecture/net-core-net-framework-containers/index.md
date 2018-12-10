---
title: Wahl zwischen .NET Core und .NET Framework für Docker-Container
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Wahl zwischen .NET Core und .NET Framework für Docker-Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: e71739b06275d4ee786d246004930d7b66fbc72b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151420"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="3262e-103">Wahl zwischen .NET Core und .NET Framework für Docker-Container</span><span class="sxs-lookup"><span data-stu-id="3262e-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="3262e-104">Bei der Erstellung von serverseitigen Containeranwendungen von Docker mit .NET werden zwei Frameworks unterstützt: [.NET Framework und .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="3262e-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="3262e-105">Sie nutzen viele Komponenten der .NET-Plattform, und Sie können Code über beide hinweg nutzen.</span><span class="sxs-lookup"><span data-stu-id="3262e-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="3262e-106">Allerdings gibt es auch grundlegende Unterschiede zwischen beiden, daher richtet sich die Entscheidung, welches Framework Sie verwenden, nach dem, was Sie erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="3262e-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="3262e-107">Dieser Abschnitt bietet Ihnen Unterstützung bei der Entscheidung, wann jedes Framework ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3262e-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3262e-108">[Zurück](../container-docker-introduction/docker-containers-images-registries.md)
>[Weiter](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="3262e-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>