---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a03809be5e5d61c505e295e2f769a0298f770f7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="1447c-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="1447c-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="1447c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1447c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1447c-104">ID</span><span class="sxs-lookup"><span data-stu-id="1447c-104">ID</span></span>|<span data-ttu-id="1447c-105">1006</span><span class="sxs-lookup"><span data-stu-id="1447c-105">1006</span></span>|  
|<span data-ttu-id="1447c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1447c-106">Keywords</span></span>|<span data-ttu-id="1447c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1447c-107">WFRuntime</span></span>|  
|<span data-ttu-id="1447c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1447c-108">Level</span></span>|<span data-ttu-id="1447c-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="1447c-109">Error</span></span>|  
|<span data-ttu-id="1447c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1447c-110">Channel</span></span>|<span data-ttu-id="1447c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1447c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1447c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1447c-112">Description</span></span>  
 <span data-ttu-id="1447c-113">Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1447c-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1447c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1447c-114">Message</span></span>  
 <span data-ttu-id="1447c-115">WorkflowInstance-Id: "%1" hat eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1447c-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="1447c-116">Die Ausnahme stammt von der Aktivität '%2', DisplayName: "%3".</span><span class="sxs-lookup"><span data-stu-id="1447c-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="1447c-117">Die folgende Aktion durchzuführenden: %4.</span><span class="sxs-lookup"><span data-stu-id="1447c-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1447c-118">Details</span><span class="sxs-lookup"><span data-stu-id="1447c-118">Details</span></span>  
  
|<span data-ttu-id="1447c-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1447c-119">Data Item Name</span></span>|<span data-ttu-id="1447c-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1447c-120">Data Item Type</span></span>|<span data-ttu-id="1447c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1447c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1447c-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="1447c-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="1447c-123">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="1447c-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="1447c-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="1447c-124">Exception</span></span>|`xs:string`|<span data-ttu-id="1447c-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="1447c-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="1447c-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1447c-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1447c-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1447c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
