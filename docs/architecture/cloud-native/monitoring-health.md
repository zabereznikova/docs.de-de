---
title: Überwachung und Integrität
description: Überwachung und Integrität
ms.date: 05/13/2020
ms.openlocfilehash: 28e98bbdb39a68d8961d4f3ab48cde5a07a4762b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613797"
---
# <a name="monitoring-and-health"></a><span data-ttu-id="935c2-103">Überwachung und Integrität</span><span class="sxs-lookup"><span data-stu-id="935c2-103">Monitoring and health</span></span>

<span data-ttu-id="935c2-104">Bei der Verwendung von Webdiensten und cloudbasierten Anwendungen werden gute devops-Verfahren Hand behandelt.</span><span class="sxs-lookup"><span data-stu-id="935c2-104">Microservices and cloud-native applications go hand in hand with good DevOps practices.</span></span> <span data-ttu-id="935c2-105">Devops ist viele Dinge, aber vielleicht eine der besseren Definitionen von Cloud Advocate und devops Evangelist Donovan Brown:</span><span class="sxs-lookup"><span data-stu-id="935c2-105">DevOps is many things to many people but perhaps one of the better definitions comes from cloud advocate and DevOps evangelist Donovan Brown:</span></span>

<span data-ttu-id="935c2-106">"Devops ist die Kombination aus Personen, Prozessen und Produkten, die Continuous Delivery des Werts für unsere Endbenutzer ermöglicht."</span><span class="sxs-lookup"><span data-stu-id="935c2-106">"DevOps is the union of people, process, and products to enable continuous delivery of value to our end users."</span></span>

<span data-ttu-id="935c2-107">Leider gibt es bei knappe-Definitionen immer genügend Platz, um weitere Dinge zu sagen.</span><span class="sxs-lookup"><span data-stu-id="935c2-107">Unfortunately, with terse definitions, there's always room to say more things.</span></span> <span data-ttu-id="935c2-108">Eine der Hauptkomponenten von devops ist die Sicherstellung, dass die Anwendungen, die in der Produktionsumgebung ausgeführt werden, ordnungsgemäß und effizient funktionieren.</span><span class="sxs-lookup"><span data-stu-id="935c2-108">One of the key components of DevOps is ensuring that the applications running in production are functioning properly and efficiently.</span></span> <span data-ttu-id="935c2-109">Zum Messen der Integrität der Anwendung in der Produktion ist es erforderlich, die verschiedenen Protokolle und Metriken zu überwachen, die von den Servern, Hosts und der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="935c2-109">To gauge the health of the application in production, it's necessary to monitor the various logs and metrics being produced from the servers, hosts, and the application proper.</span></span> <span data-ttu-id="935c2-110">Die Anzahl der verschiedenen Dienste, die zur Unterstützung einer Cloud-native Anwendung ausgeführt werden, macht die Überwachung der Integrität einzelner Komponenten und der Anwendung als eine entscheidende Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="935c2-110">The number of different services running in support of a cloud-native application makes monitoring the health of individual components and the application as a whole a critical challenge.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="935c2-111">[Zurück](resilient-communications.md)
>[Weiter](observability-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="935c2-111">[Previous](resilient-communications.md)
[Next](observability-patterns.md)</span></span>
