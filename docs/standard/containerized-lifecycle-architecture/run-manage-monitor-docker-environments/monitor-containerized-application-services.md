---
title: Überwachen von Containeranwendungsdiensten
description: Erfahren Sie, einige wichtige Aspekte der Überwachung von Container-Architekturen
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641224"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="ddce8-103">Überwachen von Containeranwendungsdiensten</span><span class="sxs-lookup"><span data-stu-id="ddce8-103">Monitor containerized application services</span></span>

<span data-ttu-id="ddce8-104">Es ist wichtig für Anwendungen, die in mehreren Containern und Microservices aufgeteilt werden, eine andere Methode zum Überwachen und Analysieren das Verhalten der gesamten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ddce8-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="ddce8-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="ddce8-105">Azure Monitor</span></span>

<span data-ttu-id="ddce8-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) ist ein erweiterbarer Analysedienst, der überwacht Ihre live-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ddce8-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="ddce8-107">Es hilft Ihnen zu erkennen und Diagnostizieren von Leistungsproblemen und zu verstehen, was Benutzer mit Ihrer app tun.</span><span class="sxs-lookup"><span data-stu-id="ddce8-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="ddce8-108">Es ist für Entwickler, mit der Absicht der Ihnen hilft, um kontinuierlich die Leistung zu verbessern und die Nutzbarkeit von Ihre Dienste oder Anwendungen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ddce8-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="ddce8-109">Azure Monitor, die mit/Webdienste und eigenständige apps auf einer Vielzahl von Plattformen wie .NET, Java, Node.js und viele andere Plattformen, die lokal gehostet oder in der Cloud funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ddce8-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ddce8-110">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ddce8-110">Additional resources</span></span>

- <span data-ttu-id="ddce8-111">**Übersicht über Azure Monitor** \\</span><span class="sxs-lookup"><span data-stu-id="ddce8-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="ddce8-112">**Was ist Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="ddce8-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="ddce8-113">**Was ist Azure Monitor-Metriken?**</span><span class="sxs-lookup"><span data-stu-id="ddce8-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="ddce8-114">**Containerüberwachungslösung in Azure Monitor** \\</span><span class="sxs-lookup"><span data-stu-id="ddce8-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="ddce8-115">Sicherheits-und Sicherung</span><span class="sxs-lookup"><span data-stu-id="ddce8-115">Security and backup services</span></span>

<span data-ttu-id="ddce8-116">Es gibt viele Support arbeiten mit vielen Details, die Sie an, um sicherzustellen, dass Ihre Anwendungen und Infrastruktur in anspruchsvoller Bedingung um geschäftsanforderungen zu unterstützen sind, und die Situation jedoch komplizierter im Bereich Microservices, weshalb Sie eine Möglichkeit haben Sie umfassender und detaillierte Ansichten aus, wenn Sie Maßnahmen ergreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="ddce8-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="ddce8-117">Azure verfügt über die Tools zum Verwalten und einen einheitlichen Überblick über vier wichtige Bestandteile Ihrer Cloudressourcen und lokale Ressourcen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="ddce8-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="ddce8-118">**Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ddce8-118">**Security**.</span></span> <span data-ttu-id="ddce8-119">Mit [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span><span class="sxs-lookup"><span data-stu-id="ddce8-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="ddce8-120">Erhalten Sie umfassende Transparenz und Kontrolle über die Sicherheit Ihrer virtuellen Computer, apps und Workloads.</span><span class="sxs-lookup"><span data-stu-id="ddce8-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="ddce8-121">Zentralisierung der Verwaltung Ihrer Sicherheitsrichtlinien, und integrieren Sie vorhandene Prozesse und Tools.</span><span class="sxs-lookup"><span data-stu-id="ddce8-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="ddce8-122">Echte Bedrohungen mit erweiterten Analysen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ddce8-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="ddce8-123">**Sicherung**.</span><span class="sxs-lookup"><span data-stu-id="ddce8-123">**Backup**.</span></span> <span data-ttu-id="ddce8-124">Mit [Azure Backup](https://azure.microsoft.com/services/backup/).</span><span class="sxs-lookup"><span data-stu-id="ddce8-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="ddce8-125">Vermeiden Sie kostspielige geschäftsunterbrechungen, halten Sie complianceziele ein, und schützen Sie Ihre Daten vor Ransomware und menschlichen Fehlern.</span><span class="sxs-lookup"><span data-stu-id="ddce8-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="ddce8-126">Halten Sie Ihre gesicherten Daten, die während der Übertragung und im Ruhezustand verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="ddce8-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="ddce8-127">Sicherstellen des Zugriffs basierend auf einer mehrstufigen Authentifizierung, um nicht autorisierte Verwendung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ddce8-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="ddce8-128">**Auf lokale Ressourcen**.</span><span class="sxs-lookup"><span data-stu-id="ddce8-128">**On-premises resources**.</span></span> <span data-ttu-id="ddce8-129">Mit [einer wirklich konsistenten hybridcloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span><span class="sxs-lookup"><span data-stu-id="ddce8-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ddce8-130">[Zurück](manage-production-docker-environments.md)
>[Weiter](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="ddce8-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
