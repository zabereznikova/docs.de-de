---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6930aeed8c3cd224d5d37dcecf357195e78390ed
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="b526c-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="b526c-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="b526c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b526c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b526c-104">ID</span><span class="sxs-lookup"><span data-stu-id="b526c-104">ID</span></span>|<span data-ttu-id="b526c-105">1003</span><span class="sxs-lookup"><span data-stu-id="b526c-105">1003</span></span>|  
|<span data-ttu-id="b526c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b526c-106">Keywords</span></span>|<span data-ttu-id="b526c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b526c-107">WFRuntime</span></span>|  
|<span data-ttu-id="b526c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b526c-108">Level</span></span>|<span data-ttu-id="b526c-109">Information</span><span class="sxs-lookup"><span data-stu-id="b526c-109">Information</span></span>|  
|<span data-ttu-id="b526c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b526c-110">Channel</span></span>|<span data-ttu-id="b526c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b526c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b526c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b526c-112">Description</span></span>  
 <span data-ttu-id="b526c-113">Gibt an, dass eine Workflowinstanz mit dem Status 'Canceled' abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b526c-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b526c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b526c-114">Message</span></span>  
 <span data-ttu-id="b526c-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Canceled' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b526c-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b526c-116">Details</span><span class="sxs-lookup"><span data-stu-id="b526c-116">Details</span></span>  
  
|<span data-ttu-id="b526c-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b526c-117">Data Item Name</span></span>|<span data-ttu-id="b526c-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b526c-118">Data Item Type</span></span>|<span data-ttu-id="b526c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b526c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b526c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="b526c-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="b526c-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="b526c-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="b526c-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b526c-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b526c-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b526c-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
