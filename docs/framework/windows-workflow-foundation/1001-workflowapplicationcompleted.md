---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 12b20ef893db12892636d73eeea2976f12bfccf9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="8a18d-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="8a18d-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="8a18d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8a18d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a18d-104">ID</span><span class="sxs-lookup"><span data-stu-id="8a18d-104">ID</span></span>|<span data-ttu-id="8a18d-105">1001</span><span class="sxs-lookup"><span data-stu-id="8a18d-105">1001</span></span>|  
|<span data-ttu-id="8a18d-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8a18d-106">Keywords</span></span>|<span data-ttu-id="8a18d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8a18d-107">WFRuntime</span></span>|  
|<span data-ttu-id="8a18d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8a18d-108">Level</span></span>|<span data-ttu-id="8a18d-109">Information</span><span class="sxs-lookup"><span data-stu-id="8a18d-109">Information</span></span>|  
|<span data-ttu-id="8a18d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8a18d-110">Channel</span></span>|<span data-ttu-id="8a18d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8a18d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a18d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a18d-112">Description</span></span>  
 <span data-ttu-id="8a18d-113">Gibt an, dass eine Workflowanwendung im Closed-Zustand beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8a18d-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a18d-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8a18d-114">Message</span></span>  
 <span data-ttu-id="8a18d-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Closed' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8a18d-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a18d-116">Details</span><span class="sxs-lookup"><span data-stu-id="8a18d-116">Details</span></span>  
  
|<span data-ttu-id="8a18d-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8a18d-117">Data Item Name</span></span>|<span data-ttu-id="8a18d-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8a18d-118">Data Item Type</span></span>|<span data-ttu-id="8a18d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a18d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a18d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8a18d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8a18d-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="8a18d-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="8a18d-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a18d-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8a18d-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8a18d-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
