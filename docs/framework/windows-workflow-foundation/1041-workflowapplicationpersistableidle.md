---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="191ad-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="191ad-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="191ad-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="191ad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="191ad-104">ID</span><span class="sxs-lookup"><span data-stu-id="191ad-104">ID</span></span>|<span data-ttu-id="191ad-105">1041</span><span class="sxs-lookup"><span data-stu-id="191ad-105">1041</span></span>|  
|<span data-ttu-id="191ad-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="191ad-106">Keywords</span></span>|<span data-ttu-id="191ad-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="191ad-107">WFRuntime</span></span>|  
|<span data-ttu-id="191ad-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="191ad-108">Level</span></span>|<span data-ttu-id="191ad-109">Information</span><span class="sxs-lookup"><span data-stu-id="191ad-109">Information</span></span>|  
|<span data-ttu-id="191ad-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="191ad-110">Channel</span></span>|<span data-ttu-id="191ad-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="191ad-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="191ad-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="191ad-112">Description</span></span>  
 <span data-ttu-id="191ad-113">Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="191ad-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="191ad-114">Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="191ad-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="191ad-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="191ad-115">Message</span></span>  
 <span data-ttu-id="191ad-116">WorkflowApplication-Id: "%1" ist im Leerlauf und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="191ad-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="191ad-117">Die folgende Aktion durchzuführenden: %2.</span><span class="sxs-lookup"><span data-stu-id="191ad-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="191ad-118">Details</span><span class="sxs-lookup"><span data-stu-id="191ad-118">Details</span></span>  
  
|<span data-ttu-id="191ad-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="191ad-119">Data Item Name</span></span>|<span data-ttu-id="191ad-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="191ad-120">Data Item Type</span></span>|<span data-ttu-id="191ad-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="191ad-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="191ad-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="191ad-122">WorkflowApplicationId</span></span>|<span data-ttu-id="191ad-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="191ad-123">xs:string</span></span>|<span data-ttu-id="191ad-124">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="191ad-124">The workflow application id</span></span>|  
|<span data-ttu-id="191ad-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="191ad-125">ActionTaken</span></span>|<span data-ttu-id="191ad-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="191ad-126">xs:string</span></span>|<span data-ttu-id="191ad-127">Die Aktion, die für die Workflowanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="191ad-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="191ad-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="191ad-128">AppDomain</span></span>|<span data-ttu-id="191ad-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="191ad-129">xs:string</span></span>|<span data-ttu-id="191ad-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="191ad-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
