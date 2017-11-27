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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7394ebbcb14850af89d906b0b573c4f677346825
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="9097f-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="9097f-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="9097f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9097f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9097f-104">ID</span><span class="sxs-lookup"><span data-stu-id="9097f-104">ID</span></span>|<span data-ttu-id="9097f-105">1004</span><span class="sxs-lookup"><span data-stu-id="9097f-105">1004</span></span>|  
|<span data-ttu-id="9097f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9097f-106">Keywords</span></span>|<span data-ttu-id="9097f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9097f-107">WFRuntime</span></span>|  
|<span data-ttu-id="9097f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9097f-108">Level</span></span>|<span data-ttu-id="9097f-109">Information</span><span class="sxs-lookup"><span data-stu-id="9097f-109">Information</span></span>|  
|<span data-ttu-id="9097f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9097f-110">Channel</span></span>|<span data-ttu-id="9097f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9097f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9097f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9097f-112">Description</span></span>  
 <span data-ttu-id="9097f-113">Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="9097f-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9097f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9097f-114">Message</span></span>  
 <span data-ttu-id="9097f-115">WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="9097f-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9097f-116">Details</span><span class="sxs-lookup"><span data-stu-id="9097f-116">Details</span></span>  
  
|<span data-ttu-id="9097f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9097f-117">Data Item Name</span></span>|<span data-ttu-id="9097f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9097f-118">Data Item Type</span></span>|<span data-ttu-id="9097f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9097f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9097f-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="9097f-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="9097f-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="9097f-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="9097f-122">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="9097f-122">Exception</span></span>|`xs:string`|<span data-ttu-id="9097f-123">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="9097f-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="9097f-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9097f-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9097f-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9097f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
