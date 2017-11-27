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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea6b31a83df6e15fe34f9e4be31a4eb53bc5bb51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="e6395-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="e6395-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="e6395-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e6395-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6395-104">ID</span><span class="sxs-lookup"><span data-stu-id="e6395-104">ID</span></span>|<span data-ttu-id="e6395-105">1041</span><span class="sxs-lookup"><span data-stu-id="e6395-105">1041</span></span>|  
|<span data-ttu-id="e6395-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e6395-106">Keywords</span></span>|<span data-ttu-id="e6395-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e6395-107">WFRuntime</span></span>|  
|<span data-ttu-id="e6395-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e6395-108">Level</span></span>|<span data-ttu-id="e6395-109">Information</span><span class="sxs-lookup"><span data-stu-id="e6395-109">Information</span></span>|  
|<span data-ttu-id="e6395-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e6395-110">Channel</span></span>|<span data-ttu-id="e6395-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e6395-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e6395-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6395-112">Description</span></span>  
 <span data-ttu-id="e6395-113">Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6395-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="e6395-114">Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e6395-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e6395-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="e6395-115">Message</span></span>  
 <span data-ttu-id="e6395-116">WorkflowApplication-Id: "%1" ist im Leerlauf und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e6395-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="e6395-117">Die folgende Aktion durchzuführenden: %2.</span><span class="sxs-lookup"><span data-stu-id="e6395-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e6395-118">Details</span><span class="sxs-lookup"><span data-stu-id="e6395-118">Details</span></span>  
  
|<span data-ttu-id="e6395-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e6395-119">Data Item Name</span></span>|<span data-ttu-id="e6395-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e6395-120">Data Item Type</span></span>|<span data-ttu-id="e6395-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6395-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e6395-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="e6395-122">WorkflowApplicationId</span></span>|<span data-ttu-id="e6395-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e6395-123">xs:string</span></span>|<span data-ttu-id="e6395-124">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="e6395-124">The workflow application id</span></span>|  
|<span data-ttu-id="e6395-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="e6395-125">ActionTaken</span></span>|<span data-ttu-id="e6395-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e6395-126">xs:string</span></span>|<span data-ttu-id="e6395-127">Die Aktion, die für die Workflowanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e6395-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="e6395-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e6395-128">AppDomain</span></span>|<span data-ttu-id="e6395-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="e6395-129">xs:string</span></span>|<span data-ttu-id="e6395-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e6395-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
