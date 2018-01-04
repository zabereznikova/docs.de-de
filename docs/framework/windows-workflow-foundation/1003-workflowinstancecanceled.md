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
ms.workload: dotnet
ms.openlocfilehash: b264450703090edfcf99f9584c16d33eb82a76e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="428c4-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="428c4-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="428c4-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="428c4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="428c4-104">ID</span><span class="sxs-lookup"><span data-stu-id="428c4-104">ID</span></span>|<span data-ttu-id="428c4-105">1003</span><span class="sxs-lookup"><span data-stu-id="428c4-105">1003</span></span>|  
|<span data-ttu-id="428c4-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="428c4-106">Keywords</span></span>|<span data-ttu-id="428c4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="428c4-107">WFRuntime</span></span>|  
|<span data-ttu-id="428c4-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="428c4-108">Level</span></span>|<span data-ttu-id="428c4-109">Information</span><span class="sxs-lookup"><span data-stu-id="428c4-109">Information</span></span>|  
|<span data-ttu-id="428c4-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="428c4-110">Channel</span></span>|<span data-ttu-id="428c4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="428c4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="428c4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="428c4-112">Description</span></span>  
 <span data-ttu-id="428c4-113">Gibt an, dass eine Workflowinstanz mit dem Status 'Canceled' abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="428c4-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="428c4-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="428c4-114">Message</span></span>  
 <span data-ttu-id="428c4-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Canceled' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="428c4-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="428c4-116">Details</span><span class="sxs-lookup"><span data-stu-id="428c4-116">Details</span></span>  
  
|<span data-ttu-id="428c4-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="428c4-117">Data Item Name</span></span>|<span data-ttu-id="428c4-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="428c4-118">Data Item Type</span></span>|<span data-ttu-id="428c4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="428c4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="428c4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="428c4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="428c4-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="428c4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="428c4-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="428c4-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="428c4-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="428c4-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
