---
title: 1004 - WorkflowInstanceAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564e94d94dc5e3579dc4a80d734db78e90db91fb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="48bd5-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="48bd5-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="48bd5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48bd5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48bd5-104">ID</span><span class="sxs-lookup"><span data-stu-id="48bd5-104">ID</span></span>|<span data-ttu-id="48bd5-105">1004</span><span class="sxs-lookup"><span data-stu-id="48bd5-105">1004</span></span>|  
|<span data-ttu-id="48bd5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48bd5-106">Keywords</span></span>|<span data-ttu-id="48bd5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48bd5-107">WFRuntime</span></span>|  
|<span data-ttu-id="48bd5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="48bd5-108">Level</span></span>|<span data-ttu-id="48bd5-109">Information</span><span class="sxs-lookup"><span data-stu-id="48bd5-109">Information</span></span>|  
|<span data-ttu-id="48bd5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="48bd5-110">Channel</span></span>|<span data-ttu-id="48bd5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48bd5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48bd5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48bd5-112">Description</span></span>  
 <span data-ttu-id="48bd5-113">Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="48bd5-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48bd5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="48bd5-114">Message</span></span>  
 <span data-ttu-id="48bd5-115">WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="48bd5-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48bd5-116">Details</span><span class="sxs-lookup"><span data-stu-id="48bd5-116">Details</span></span>  
  
|<span data-ttu-id="48bd5-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="48bd5-117">Data Item Name</span></span>|<span data-ttu-id="48bd5-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="48bd5-118">Data Item Type</span></span>|<span data-ttu-id="48bd5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48bd5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48bd5-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="48bd5-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="48bd5-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="48bd5-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="48bd5-122">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="48bd5-122">Exception</span></span>|`xs:string`|<span data-ttu-id="48bd5-123">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="48bd5-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="48bd5-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48bd5-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="48bd5-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48bd5-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
