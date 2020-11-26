---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: be97991be9b61908a23486da0ef255ebfbdc5485
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239951"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="bc91f-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="bc91f-102">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="bc91f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bc91f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc91f-104">id</span><span class="sxs-lookup"><span data-stu-id="bc91f-104">ID</span></span>|<span data-ttu-id="bc91f-105">1001</span><span class="sxs-lookup"><span data-stu-id="bc91f-105">1001</span></span>|  
|<span data-ttu-id="bc91f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="bc91f-106">Keywords</span></span>|<span data-ttu-id="bc91f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bc91f-107">WFRuntime</span></span>|  
|<span data-ttu-id="bc91f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bc91f-108">Level</span></span>|<span data-ttu-id="bc91f-109">Information</span><span class="sxs-lookup"><span data-stu-id="bc91f-109">Information</span></span>|  
|<span data-ttu-id="bc91f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bc91f-110">Channel</span></span>|<span data-ttu-id="bc91f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bc91f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bc91f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc91f-112">Description</span></span>  

 <span data-ttu-id="bc91f-113">Gibt an, dass eine Workflowanwendung im Closed-Zustand beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bc91f-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bc91f-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="bc91f-114">Message</span></span>  

 <span data-ttu-id="bc91f-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Closed' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bc91f-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bc91f-116">Details</span><span class="sxs-lookup"><span data-stu-id="bc91f-116">Details</span></span>  
  
|<span data-ttu-id="bc91f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bc91f-117">Data Item Name</span></span>|<span data-ttu-id="bc91f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bc91f-118">Data Item Type</span></span>|<span data-ttu-id="bc91f-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc91f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bc91f-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="bc91f-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="bc91f-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="bc91f-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="bc91f-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bc91f-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bc91f-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bc91f-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
