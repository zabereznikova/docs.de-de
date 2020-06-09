---
title: Übersicht über das Hosten von Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: 10ea35fc1988e1b3e6ceb44aca098e63bfc7d7e4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597292"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="62898-102">Übersicht über das Hosten von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="62898-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="62898-103">Workflowdienste müssen gehostet werden, damit sie ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="62898-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="62898-104">Der <xref:System.ServiceModel.WorkflowServiceHost> ist der vordefinierte Workflowhost, der mehrere Instanzen, Konfigurationen sowie WCF-Messaging unterstützt (obwohl die Verwendung von Messaging zum Hosten der Workflows nicht erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="62898-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="62898-105">Außerdem wird durch einen Satz von Dienstverhalten die Integration von Persistenz, Nachverfolgung und Instanzsteuerung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62898-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="62898-106">Ebenso wie der <xref:System.ServiceModel.ServiceHost> von WCF kann sich der <xref:System.ServiceModel.WorkflowServiceHost> in verwalteten .NET-Anwendungen selbst hosten, oder er wird in IIS/WAS (als XAMLX-Datei) im Internet gehostet.</span><span class="sxs-lookup"><span data-stu-id="62898-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="62898-107">In den Themen dieses Abschnitts wird beschrieben, wie Sie einen Workflowdienst hosten.</span><span class="sxs-lookup"><span data-stu-id="62898-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62898-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62898-108">In This Section</span></span>  
 [<span data-ttu-id="62898-109">Hosten von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="62898-109">Hosting Workflow Services</span></span>](hosting-workflow-services.md)  
 <span data-ttu-id="62898-110">Beschreibt das Hosten von Workflowdiensten.</span><span class="sxs-lookup"><span data-stu-id="62898-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="62898-111">Interne Funktionsweise des Workflowdiensthosts</span><span class="sxs-lookup"><span data-stu-id="62898-111">Workflow Service Host Internals</span></span>](workflow-service-host-internals.md)  
 <span data-ttu-id="62898-112">Beschreibt, wie <xref:System.ServiceModel.WorkflowServiceHost> eingehende Meldungen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="62898-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="62898-113">Erweiterbarkeit des Workflowdiensthosts</span><span class="sxs-lookup"><span data-stu-id="62898-113">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)  
 <span data-ttu-id="62898-114">Beschreibt, wie Sie die Funktionalität des Workflowdiensthosts erweitern.</span><span class="sxs-lookup"><span data-stu-id="62898-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="62898-115">Workflowsteuerungsendpunkt</span><span class="sxs-lookup"><span data-stu-id="62898-115">Workflow Control Endpoint</span></span>](workflow-control-endpoint.md)  
 <span data-ttu-id="62898-116">Beschreibt, wie Sie einen Endpunkt definieren, der Ihnen das Erstellen von Workflowinstanzen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="62898-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="62898-117">Vorgehensweise: Hosten eines Workflowdiensts mit Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="62898-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="62898-118">Veranschaulicht das Hosten eines vorhandenen Workflowdiensts in Windows Server AppFabric.</span><span class="sxs-lookup"><span data-stu-id="62898-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="62898-119">Konfigurieren von WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="62898-119">Configuring WorkflowServiceHost</span></span>](configuring-workflowservicehost.md)  
 <span data-ttu-id="62898-120">Beschreibt, wie Sie das Verhalten bei Persistenz, Nachverfolgung und Leerlauf sowie nicht behandeltes Ausnahmeverhalten steuern.</span><span class="sxs-lookup"><span data-stu-id="62898-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="62898-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="62898-121">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="62898-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="62898-122">Related Sections</span></span>  
 [<span data-ttu-id="62898-123">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="62898-123">Workflow Services</span></span>](workflow-services.md)
