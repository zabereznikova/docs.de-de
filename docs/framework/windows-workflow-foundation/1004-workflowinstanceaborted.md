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
ms.workload: dotnet
ms.openlocfilehash: cc940e1781f821f12efb42c5198e77eb0451a164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="7877d-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="7877d-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="7877d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7877d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7877d-104">ID</span><span class="sxs-lookup"><span data-stu-id="7877d-104">ID</span></span>|<span data-ttu-id="7877d-105">1004</span><span class="sxs-lookup"><span data-stu-id="7877d-105">1004</span></span>|  
|<span data-ttu-id="7877d-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7877d-106">Keywords</span></span>|<span data-ttu-id="7877d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7877d-107">WFRuntime</span></span>|  
|<span data-ttu-id="7877d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7877d-108">Level</span></span>|<span data-ttu-id="7877d-109">Information</span><span class="sxs-lookup"><span data-stu-id="7877d-109">Information</span></span>|  
|<span data-ttu-id="7877d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7877d-110">Channel</span></span>|<span data-ttu-id="7877d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7877d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7877d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7877d-112">Description</span></span>  
 <span data-ttu-id="7877d-113">Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="7877d-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7877d-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="7877d-114">Message</span></span>  
 <span data-ttu-id="7877d-115">WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="7877d-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7877d-116">Details</span><span class="sxs-lookup"><span data-stu-id="7877d-116">Details</span></span>  
  
|<span data-ttu-id="7877d-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7877d-117">Data Item Name</span></span>|<span data-ttu-id="7877d-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7877d-118">Data Item Type</span></span>|<span data-ttu-id="7877d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7877d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7877d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="7877d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="7877d-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="7877d-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="7877d-122">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="7877d-122">Exception</span></span>|`xs:string`|<span data-ttu-id="7877d-123">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="7877d-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="7877d-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7877d-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7877d-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7877d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
