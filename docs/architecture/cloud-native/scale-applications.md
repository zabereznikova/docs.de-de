---
title: Skalieren von cloudbasierten Anwendungen
description: Skalieren Sie Native Cloud-Anwendungen mit Azure Kubernetes Service und Azure Functions, um die Benutzer Nachfrage auf kostengünstige Weise zu erfüllen.
ms.date: 09/23/2019
ms.openlocfilehash: 5f4aac5804c5498c331787083c943a6ea1b69748
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841030"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="961de-103">Skalieren von cloudbasierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="961de-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="961de-104">Einer der häufigsten Vorteile der Umstellung auf eine Cloud-Hostingumgebung ist die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="961de-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="961de-105">Die Skalierbarkeit oder die Fähigkeit einer Anwendung, eine zusätzliche Benutzer Auslastung zu akzeptieren, ohne dass die Leistung für jeden Benutzer übermäßig beeinträchtigt wird, wird meistens erreicht, indem Anwendungen in kleine Teile aufgeteilt werden, die jeweils die erforderlichen Ressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="961de-105">Scalability, or the ability for an application to accept additional user load without unduly degrading performance for each user, is most often achieved by breaking up applications into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="961de-106">In diesem Kapitel werden die Technologien vorgestellt, mit denen die Skalierung von cloudbasierten Anwendungen auf die Benutzer Nachfrage skaliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="961de-106">In this chapter, we introduce the technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="961de-107">Zu diesen Technologien gehören:</span><span class="sxs-lookup"><span data-stu-id="961de-107">These technologies include:</span></span>

- <span data-ttu-id="961de-108">Container</span><span class="sxs-lookup"><span data-stu-id="961de-108">Containers</span></span>
- <span data-ttu-id="961de-109">Orchestratoren</span><span class="sxs-lookup"><span data-stu-id="961de-109">Orchestrators</span></span>
- <span data-ttu-id="961de-110">Server Loses Computing</span><span class="sxs-lookup"><span data-stu-id="961de-110">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="961de-111">[Zurück](centralized-configuration.md)
>[Weiter](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="961de-111">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
