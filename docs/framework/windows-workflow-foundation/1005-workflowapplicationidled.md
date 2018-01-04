---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc9f8f72000fe283baa5bb2814e41051c1424983
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="0e22b-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="0e22b-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="0e22b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0e22b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e22b-104">ID</span><span class="sxs-lookup"><span data-stu-id="0e22b-104">ID</span></span>|<span data-ttu-id="0e22b-105">1005</span><span class="sxs-lookup"><span data-stu-id="0e22b-105">1005</span></span>|  
|<span data-ttu-id="0e22b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0e22b-106">Keywords</span></span>|<span data-ttu-id="0e22b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0e22b-107">WFRuntime</span></span>|  
|<span data-ttu-id="0e22b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0e22b-108">Level</span></span>|<span data-ttu-id="0e22b-109">Information</span><span class="sxs-lookup"><span data-stu-id="0e22b-109">Information</span></span>|  
|<span data-ttu-id="0e22b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0e22b-110">Channel</span></span>|<span data-ttu-id="0e22b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0e22b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e22b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e22b-112">Description</span></span>  
 <span data-ttu-id="0e22b-113">Gibt an, dass sich eine Workflowanwendung im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="0e22b-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e22b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0e22b-114">Message</span></span>  
 <span data-ttu-id="0e22b-115">WorkflowApplication-ID: '%1 ' ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="0e22b-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e22b-116">Details</span><span class="sxs-lookup"><span data-stu-id="0e22b-116">Details</span></span>  
  
|<span data-ttu-id="0e22b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0e22b-117">Data Item Name</span></span>|<span data-ttu-id="0e22b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0e22b-118">Data Item Type</span></span>|<span data-ttu-id="0e22b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e22b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e22b-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0e22b-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0e22b-121">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="0e22b-121">The workflow application id</span></span>|  
|<span data-ttu-id="0e22b-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e22b-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0e22b-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0e22b-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
