---
title: Azure Logic apps Server Lose apps
description: Azure Logic apps ermöglichen das entwickeln automatisierter skalierbarer Workflows, die apps und Daten in Clouddienste und lokale Systeme integrieren.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577453"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="ef82b-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="ef82b-103">Azure Logic Apps</span></span>

<span data-ttu-id="ef82b-104">[Azure Logic apps](https://docs.microsoft.com/azure/logic-apps) bietet eine Server lose Engine zum Erstellen automatisierter Workflows zum Integrieren von apps und Daten zwischen Cloud-Diensten und lokalen Systemen.</span><span class="sxs-lookup"><span data-stu-id="ef82b-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="ef82b-105">Workflows werden mithilfe eines visuellen Designers erstellt.</span><span class="sxs-lookup"><span data-stu-id="ef82b-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="ef82b-106">Sie können Workflows auf der Grundlage von Ereignissen oder Timern initiieren und Connectors für Integrationsanwendungen nutzen und die B2B-Kommunikation (Business-to-Business) vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ef82b-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="ef82b-107">Logic apps nahtlos in Azure Functions integriert.</span><span class="sxs-lookup"><span data-stu-id="ef82b-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic apps Logo](./media/logic-apps-logo.png)

<span data-ttu-id="ef82b-109">Logic Apps können mehr tun, als nur Ihre Clouddienste (z. b. Funktionen) mit cloudressourcen (wie Warteschlangen und Datenbanken) zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="ef82b-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="ef82b-110">Sie können auch lokale Workflows mit dem lokalen Gateway orchestrieren.</span><span class="sxs-lookup"><span data-stu-id="ef82b-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="ef82b-111">Beispielsweise können Sie die Logik-App verwenden, um eine lokale gespeicherte SQL-Prozedur als Reaktion auf ein cloudbasiertes Ereignis oder eine bedingte Logik in Ihrem Workflow zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="ef82b-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="ef82b-112">Erfahren Sie mehr über das [Herstellen einer Verbindung mit lokalen Datenquellen mit dem lokalen Azure-Daten Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span><span class="sxs-lookup"><span data-stu-id="ef82b-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Logic apps-Architektur](./media/logic-apps-architecture.png)

<span data-ttu-id="ef82b-114">Wie Azure Functions starten Sie Logik-App-Workflows mit einem-Triggern.</span><span class="sxs-lookup"><span data-stu-id="ef82b-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="ef82b-115">Es gibt viele Trigger, aus denen Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="ef82b-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="ef82b-116">Die folgende Erfassung zeigt nur einige der gängigsten, die von Hunderten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ef82b-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Logic apps Trigger](./media/logic-app-triggers.png)

<span data-ttu-id="ef82b-118">Nachdem die APP ausgelöst wurde, können Sie den visuellen Designer verwenden, um Schritte, Schleifen, Bedingungen und Aktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef82b-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="ef82b-119">Alle Daten, die in einem vorherigen Schritt erfasst wurden, können in nachfolgenden Schritten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef82b-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="ef82b-120">Der folgende Workflow lädt URLs aus einer cosmosdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ef82b-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="ef82b-121">Es findet diejenigen, die einen Host von `t.co` haben, und sucht dann auf Twitter nach diesen.</span><span class="sxs-lookup"><span data-stu-id="ef82b-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="ef82b-122">Wenn entsprechende tweets gefunden werden, aktualisiert Sie die Dokumente mit den zugehörigen Tweets, indem eine Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ef82b-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![Logik-App-Workflow](./media/logic-app-workflow.png)

<span data-ttu-id="ef82b-124">Das Logic Apps Dashboard zeigt den Verlauf der Ausführung Ihrer Workflows und ob jede Ausführung erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ef82b-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="ef82b-125">Sie können zu jeder beliebigen Testlauf navigieren und die Daten überprüfen, die von den einzelnen Schritten zur Problembehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef82b-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="ef82b-126">Logic Apps bietet auch vorhandene Vorlagen, die Sie bearbeiten können und die sich gut für komplexe Unternehmens Workflows eignen.</span><span class="sxs-lookup"><span data-stu-id="ef82b-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="ef82b-127">Weitere Informationen finden Sie unter [Azure Logic apps](https://docs.microsoft.com/azure/logic-apps).</span><span class="sxs-lookup"><span data-stu-id="ef82b-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ef82b-128">[Zurück](application-insights.md)
>[Weiter](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="ef82b-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
