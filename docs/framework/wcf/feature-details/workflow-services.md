---
title: Workflowdienste
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: c7a5c6245702497fcd75341b3ff7ba08dc190fa5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600126"
---
# <a name="workflow-services"></a><span data-ttu-id="d9b14-102">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="d9b14-102">Workflow Services</span></span>
<span data-ttu-id="d9b14-103">Mit [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] können Sie einen workflowbasierten Dienst vollständig deklarativ in XAML beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d9b14-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="d9b14-104">Sie können einen Workflow definieren, der den Dienst implementiert, und Endpunkte beschreiben, die der Dienst verfügbar macht – alles in XAML.</span><span class="sxs-lookup"><span data-stu-id="d9b14-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="d9b14-105">In den Themen in diesem Abschnitt wird ausführlich das Programmiermodell beschrieben, das das deklarative Schreiben von Diensten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d9b14-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9b14-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d9b14-106">In This Section</span></span>  
 [<span data-ttu-id="d9b14-107">Übersicht über Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="d9b14-107">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="d9b14-108">Beschreibt die Komponenten, die am Erstellen und Hosten eines Workflowdiensts beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="d9b14-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="d9b14-109">Messagingaktivitäten</span><span class="sxs-lookup"><span data-stu-id="d9b14-109">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="d9b14-110">Erläutert die Aktivitäten, mit denen Workflows Nachrichten senden und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="d9b14-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="d9b14-111">Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten</span><span class="sxs-lookup"><span data-stu-id="d9b14-111">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="d9b14-112">Beschreibt, wie Sie Messagingaktivitäten verwenden, um einen Workflowdienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b14-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="d9b14-113">Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung</span><span class="sxs-lookup"><span data-stu-id="d9b14-113">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="d9b14-114">Erläutert, wie Sie einen Dienst aus einer Workflowanwendung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d9b14-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="d9b14-115">Ungs</span><span class="sxs-lookup"><span data-stu-id="d9b14-115">Correlation</span></span>](correlation.md)  
 <span data-ttu-id="d9b14-116">Erläutert, wie Nachrichten bei der Korrelation einander und Instanzen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b14-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="d9b14-117">Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="d9b14-117">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="d9b14-118">Beschreibt, wie Sie einen Dienst so konfigurieren, dass dieser nicht in der richtigen Reihenfolge angeordnete Nachrichten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d9b14-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="d9b14-119">Entwickeln von Vertrag zuerst-Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="d9b14-119">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="d9b14-120">Beschreibt das Erstellen eines Workflowdiensts auf Grundlage eines vorhandenen Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="d9b14-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="d9b14-121">Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="d9b14-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="d9b14-122">Erläutert anhand eines Beispiels Schritt für Schritt, wie ein Workflowdienst unter Verwendung eines vorhandenen Dienstvertrags erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d9b14-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="d9b14-123">Übersicht über das Hosten von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="d9b14-123">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="d9b14-124">Beschreibt die verschiedenen Aspekte, die beim Hosten eines Workflowdiensts gelten.</span><span class="sxs-lookup"><span data-stu-id="d9b14-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="d9b14-125">Verwenden von Verträgen im Workflow</span><span class="sxs-lookup"><span data-stu-id="d9b14-125">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="d9b14-126">Beschreibt die verschiedenen Vertragstypen und die damit verbundenen Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d9b14-126">Describes the different types of contracts and contract inference.</span></span>
