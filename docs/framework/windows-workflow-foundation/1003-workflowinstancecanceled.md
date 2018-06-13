---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509768"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="402f9-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="402f9-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="402f9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="402f9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="402f9-104">ID</span><span class="sxs-lookup"><span data-stu-id="402f9-104">ID</span></span>|<span data-ttu-id="402f9-105">1003</span><span class="sxs-lookup"><span data-stu-id="402f9-105">1003</span></span>|  
|<span data-ttu-id="402f9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="402f9-106">Keywords</span></span>|<span data-ttu-id="402f9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="402f9-107">WFRuntime</span></span>|  
|<span data-ttu-id="402f9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="402f9-108">Level</span></span>|<span data-ttu-id="402f9-109">Information</span><span class="sxs-lookup"><span data-stu-id="402f9-109">Information</span></span>|  
|<span data-ttu-id="402f9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="402f9-110">Channel</span></span>|<span data-ttu-id="402f9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="402f9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="402f9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="402f9-112">Description</span></span>  
 <span data-ttu-id="402f9-113">Gibt an, dass eine Workflowinstanz mit dem Status 'Canceled' abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="402f9-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="402f9-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="402f9-114">Message</span></span>  
 <span data-ttu-id="402f9-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Canceled' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="402f9-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="402f9-116">Details</span><span class="sxs-lookup"><span data-stu-id="402f9-116">Details</span></span>  
  
|<span data-ttu-id="402f9-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="402f9-117">Data Item Name</span></span>|<span data-ttu-id="402f9-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="402f9-118">Data Item Type</span></span>|<span data-ttu-id="402f9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="402f9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="402f9-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="402f9-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="402f9-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="402f9-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="402f9-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="402f9-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="402f9-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="402f9-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
