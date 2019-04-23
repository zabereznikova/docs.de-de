---
title: Wahl zwischen .NET Core und .NET Framework für Docker-Container
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Wahl zwischen .NET Core und .NET Framework für Docker-Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: e71739b06275d4ee786d246004930d7b66fbc72b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019606"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="06a1b-103">Wahl zwischen .NET Core und .NET Framework für Docker-Container</span><span class="sxs-lookup"><span data-stu-id="06a1b-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="06a1b-104">Bei der Erstellung von serverseitigen Containeranwendungen von Docker mit .NET werden zwei Frameworks unterstützt: [.NET Framework und .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="06a1b-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="06a1b-105">Sie nutzen viele Komponenten der .NET-Plattform, und Sie können Code über beide hinweg nutzen.</span><span class="sxs-lookup"><span data-stu-id="06a1b-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="06a1b-106">Allerdings gibt es auch grundlegende Unterschiede zwischen beiden, daher richtet sich die Entscheidung, welches Framework Sie verwenden, nach dem, was Sie erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="06a1b-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="06a1b-107">Dieser Abschnitt bietet Ihnen Unterstützung bei der Entscheidung, wann jedes Framework ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="06a1b-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06a1b-108">[Zurück](../container-docker-introduction/docker-containers-images-registries.md)
>[Weiter](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="06a1b-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>