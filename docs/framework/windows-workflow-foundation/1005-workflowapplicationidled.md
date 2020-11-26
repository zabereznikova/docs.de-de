---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 3b7210246b7fb754145c8aa6128da3183cea9f91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239860"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="f0a01-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="f0a01-102">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="f0a01-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f0a01-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0a01-104">id</span><span class="sxs-lookup"><span data-stu-id="f0a01-104">ID</span></span>|<span data-ttu-id="f0a01-105">1005</span><span class="sxs-lookup"><span data-stu-id="f0a01-105">1005</span></span>|  
|<span data-ttu-id="f0a01-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="f0a01-106">Keywords</span></span>|<span data-ttu-id="f0a01-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f0a01-107">WFRuntime</span></span>|  
|<span data-ttu-id="f0a01-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f0a01-108">Level</span></span>|<span data-ttu-id="f0a01-109">Information</span><span class="sxs-lookup"><span data-stu-id="f0a01-109">Information</span></span>|  
|<span data-ttu-id="f0a01-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f0a01-110">Channel</span></span>|<span data-ttu-id="f0a01-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f0a01-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0a01-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0a01-112">Description</span></span>  

 <span data-ttu-id="f0a01-113">Gibt an, dass sich eine Workflowanwendung im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="f0a01-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0a01-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="f0a01-114">Message</span></span>  

 <span data-ttu-id="f0a01-115">WorkflowApplication-ID: '%1 ' ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="f0a01-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0a01-116">Details</span><span class="sxs-lookup"><span data-stu-id="f0a01-116">Details</span></span>  
  
|<span data-ttu-id="f0a01-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f0a01-117">Data Item Name</span></span>|<span data-ttu-id="f0a01-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f0a01-118">Data Item Type</span></span>|<span data-ttu-id="f0a01-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0a01-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0a01-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f0a01-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f0a01-121">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="f0a01-121">The workflow application id</span></span>|  
|<span data-ttu-id="f0a01-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0a01-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f0a01-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f0a01-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
