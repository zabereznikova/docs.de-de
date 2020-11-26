---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: bd8abf173ab6588d4a35ba59c6cd14fb53445e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239899"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="b816a-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="b816a-102">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="b816a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b816a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b816a-104">id</span><span class="sxs-lookup"><span data-stu-id="b816a-104">ID</span></span>|<span data-ttu-id="b816a-105">1003</span><span class="sxs-lookup"><span data-stu-id="b816a-105">1003</span></span>|  
|<span data-ttu-id="b816a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="b816a-106">Keywords</span></span>|<span data-ttu-id="b816a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b816a-107">WFRuntime</span></span>|  
|<span data-ttu-id="b816a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b816a-108">Level</span></span>|<span data-ttu-id="b816a-109">Information</span><span class="sxs-lookup"><span data-stu-id="b816a-109">Information</span></span>|  
|<span data-ttu-id="b816a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b816a-110">Channel</span></span>|<span data-ttu-id="b816a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b816a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b816a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b816a-112">Description</span></span>  

 <span data-ttu-id="b816a-113">Gibt an, dass eine Workflowinstanz mit dem Status 'Canceled' abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b816a-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b816a-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="b816a-114">Message</span></span>  

 <span data-ttu-id="b816a-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Canceled' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b816a-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b816a-116">Details</span><span class="sxs-lookup"><span data-stu-id="b816a-116">Details</span></span>  
  
|<span data-ttu-id="b816a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b816a-117">Data Item Name</span></span>|<span data-ttu-id="b816a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b816a-118">Data Item Type</span></span>|<span data-ttu-id="b816a-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b816a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b816a-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="b816a-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="b816a-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="b816a-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="b816a-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b816a-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b816a-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b816a-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
