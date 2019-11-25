---
title: 'Azure Logic Apps: Serverlose Apps'
description: Azure Logic Apps ermöglicht das Erstellen automatisierter skalierbarer Workflows, die Apps und Daten übergreifend in Clouddienste und lokale Systeme integrieren.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577453"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="de68f-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="de68f-103">Azure Logic Apps</span></span>

<span data-ttu-id="de68f-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) bietet eine serverlose Engine zum Erstellen automatisierter Workflows zur Integration von Anwendungen und Daten zwischen Clouddiensten und lokalen Systemen.</span><span class="sxs-lookup"><span data-stu-id="de68f-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="de68f-105">Workflows werden mithilfe eines visuellen Designers erstellt.</span><span class="sxs-lookup"><span data-stu-id="de68f-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="de68f-106">Sie können Workflows auf der Grundlage von Ereignissen oder Timern auslösen, Connectors für Integrationsanwendungen nutzen und B2B-Kommunikation (Business-to-Business) ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="de68f-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="de68f-107">Logic Apps ist nahtlos in Azure Functions integriert.</span><span class="sxs-lookup"><span data-stu-id="de68f-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps-Logo](./media/logic-apps-logo.png)

<span data-ttu-id="de68f-109">Logic Apps können weitaus mehr, als nur Ihre Clouddienste (z.B. Funktionen) mit Cloudressourcen (wie Warteschlangen und Datenbanken) zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="de68f-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="de68f-110">Sie können auch lokale Workflows mit dem lokalen Gateway orchestrieren.</span><span class="sxs-lookup"><span data-stu-id="de68f-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="de68f-111">Beispielsweise können Sie die Logik-App verwenden, um eine lokal gespeicherte SQL-Prozedur als Reaktion auf ein cloudbasiertes Ereignis oder bedingte Logik in Ihrem Workflow auszulösen.</span><span class="sxs-lookup"><span data-stu-id="de68f-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="de68f-112">Erfahren Sie mehr über das [Herstellen einer Verbindung mit lokalen Datenquellen mit dem lokalen Azure-Datengateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span><span class="sxs-lookup"><span data-stu-id="de68f-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Logic Apps-Architektur](./media/logic-apps-architecture.png)

<span data-ttu-id="de68f-114">Wie Azure Functions starten Sie Logik-App-Workflows mit einem Trigger.</span><span class="sxs-lookup"><span data-stu-id="de68f-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="de68f-115">Es gibt viele Trigger, aus denen Sie wählen können.</span><span class="sxs-lookup"><span data-stu-id="de68f-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="de68f-116">Die folgende Abbildung zeigt nur einige der beliebtesten von Hunderten, die verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="de68f-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Logic Apps-Trigger](./media/logic-app-triggers.png)

<span data-ttu-id="de68f-118">Nachdem die App ausgelöst wurde, können Sie den visuellen Designer verwenden, um Schritte, Schleifen, Bedingungen und Aktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de68f-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="de68f-119">Alle Daten, die in einem vorherigen Schritt erfasst wurden, können in nachfolgenden Schritten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de68f-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="de68f-120">Der folgende Workflow lädt URLs aus einer CosmosDB-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="de68f-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="de68f-121">Er findet URLs mit dem Host `t.co` und sucht dann auf Twitter nach diesen.</span><span class="sxs-lookup"><span data-stu-id="de68f-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="de68f-122">Wenn entsprechende Tweets gefunden werden, aktualisiert er die Dokumente mit den zugehörigen Tweets, indem eine Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="de68f-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![Logik-App-Workflow](./media/logic-app-workflow.png)

<span data-ttu-id="de68f-124">Das Logic Apps-Dashboard zeigt den Verlauf der Ausführung Ihrer Workflows an und ob jede Ausführung erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="de68f-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="de68f-125">Sie können zu jeder beliebigen Ausführung navigieren und die von den einzelnen Schritten verwendeten Daten zur Problembehandlung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="de68f-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="de68f-126">Logic Apps bietet auch vorhandene Vorlagen, die Sie bearbeiten können und die sich gut für komplexe Unternehmensworkflows eignen.</span><span class="sxs-lookup"><span data-stu-id="de68f-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="de68f-127">Weitere Informationen finden Sie unter [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span><span class="sxs-lookup"><span data-stu-id="de68f-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="de68f-128">[Zurück](application-insights.md)
>[Weiter](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="de68f-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
