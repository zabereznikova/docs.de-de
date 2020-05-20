---
title: Skalieren von cloudbasierten Anwendungen
description: Skalieren Sie Native Cloud-Anwendungen mit Azure Kubernetes Service und Azure Functions, um die Benutzer Nachfrage auf kostengünstige Weise zu erfüllen.
ms.date: 05/13/2020
ms.openlocfilehash: d425976eed248461a9c2e4fe03596f9f6dfd2eba
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613732"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="dc4cb-103">Skalieren von cloudbasierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="dc4cb-103">Scaling cloud-native applications</span></span>

<span data-ttu-id="dc4cb-104">Einer der häufigsten Vorteile der Umstellung auf eine Cloud-Hostingumgebung ist die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="dc4cb-105">Skalierbarkeit oder die Fähigkeit einer Anwendung, eine zusätzliche Benutzer Auslastung zu akzeptieren, ohne die Leistung für jeden Benutzer zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="dc4cb-106">Dies wird am häufigsten erreicht, indem eine Anwendung in kleine Teile aufgeteilt wird, denen jeweils die benötigten Ressourcen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="dc4cb-107">Cloudanbieter ermöglichen eine enorme Skalierbarkeit, und zwar jederzeit und überall auf der Welt.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="dc4cb-108">In diesem Kapitel werden Technologien erläutert, mit denen die Skalierung von cloudbasierten Anwendungen auf die Benutzer Nachfrage skaliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="dc4cb-109">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="dc4cb-109">These technologies include:</span></span>

- <span data-ttu-id="dc4cb-110">Container</span><span class="sxs-lookup"><span data-stu-id="dc4cb-110">Containers</span></span>
- <span data-ttu-id="dc4cb-111">Orchestratoren</span><span class="sxs-lookup"><span data-stu-id="dc4cb-111">Orchestrators</span></span>
- <span data-ttu-id="dc4cb-112">Serverloses Computing</span><span class="sxs-lookup"><span data-stu-id="dc4cb-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc4cb-113">[Zurück](centralized-configuration.md)
>[Weiter](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="dc4cb-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
