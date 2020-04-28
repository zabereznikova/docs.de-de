---
title: Skalieren von cloudbasierten Anwendungen
description: Skalieren Sie Native Cloud-Anwendungen mit Azure Kubernetes Service und Azure Functions, um die Benutzer Nachfrage auf kostengünstige Weise zu erfüllen.
ms.date: 04/13/2020
ms.openlocfilehash: 91d925778e9dfcf8a1ec2486fe8961037409f207
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199938"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="6a277-103">Skalieren von cloudbasierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6a277-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6a277-104">Einer der häufigsten Vorteile der Umstellung auf eine Cloud-Hostingumgebung ist die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="6a277-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="6a277-105">Skalierbarkeit oder die Fähigkeit einer Anwendung, eine zusätzliche Benutzer Auslastung zu akzeptieren, ohne die Leistung für jeden Benutzer zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="6a277-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="6a277-106">Dies wird am häufigsten erreicht, indem eine Anwendung in kleine Teile aufgeteilt wird, denen jeweils die benötigten Ressourcen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="6a277-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="6a277-107">Cloudanbieter ermöglichen eine enorme Skalierbarkeit, und zwar jederzeit und überall auf der Welt.</span><span class="sxs-lookup"><span data-stu-id="6a277-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="6a277-108">In diesem Kapitel werden Technologien erläutert, mit denen die Skalierung von cloudbasierten Anwendungen auf die Benutzer Nachfrage skaliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6a277-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="6a277-109">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="6a277-109">These technologies include:</span></span>

- <span data-ttu-id="6a277-110">Container</span><span class="sxs-lookup"><span data-stu-id="6a277-110">Containers</span></span>
- <span data-ttu-id="6a277-111">Orchestratoren</span><span class="sxs-lookup"><span data-stu-id="6a277-111">Orchestrators</span></span>
- <span data-ttu-id="6a277-112">Serverloses Computing</span><span class="sxs-lookup"><span data-stu-id="6a277-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6a277-113">[Zurück](centralized-configuration.md)
>[Weiter](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="6a277-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
