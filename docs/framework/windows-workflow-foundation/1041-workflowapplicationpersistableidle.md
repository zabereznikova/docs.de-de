---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509652"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="e4eb1-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="e4eb1-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="e4eb1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e4eb1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4eb1-104">ID</span><span class="sxs-lookup"><span data-stu-id="e4eb1-104">ID</span></span>|<span data-ttu-id="e4eb1-105">1041</span><span class="sxs-lookup"><span data-stu-id="e4eb1-105">1041</span></span>|  
|<span data-ttu-id="e4eb1-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e4eb1-106">Keywords</span></span>|<span data-ttu-id="e4eb1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e4eb1-107">WFRuntime</span></span>|  
|<span data-ttu-id="e4eb1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e4eb1-108">Level</span></span>|<span data-ttu-id="e4eb1-109">Information</span><span class="sxs-lookup"><span data-stu-id="e4eb1-109">Information</span></span>|  
|<span data-ttu-id="e4eb1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e4eb1-110">Channel</span></span>|<span data-ttu-id="e4eb1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e4eb1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e4eb1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4eb1-112">Description</span></span>  
 <span data-ttu-id="e4eb1-113">Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="e4eb1-114">Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e4eb1-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="e4eb1-115">Message</span></span>  
 <span data-ttu-id="e4eb1-116">WorkflowApplication-Id: "%1" ist im Leerlauf und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="e4eb1-117">Die folgende Aktion durchzuführenden: %2.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e4eb1-118">Details</span><span class="sxs-lookup"><span data-stu-id="e4eb1-118">Details</span></span>  
  
|<span data-ttu-id="e4eb1-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e4eb1-119">Data Item Name</span></span>|<span data-ttu-id="e4eb1-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e4eb1-120">Data Item Type</span></span>|<span data-ttu-id="e4eb1-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4eb1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e4eb1-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="e4eb1-122">WorkflowApplicationId</span></span>|<span data-ttu-id="e4eb1-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4eb1-123">xs:string</span></span>|<span data-ttu-id="e4eb1-124">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="e4eb1-124">The workflow application id</span></span>|  
|<span data-ttu-id="e4eb1-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="e4eb1-125">ActionTaken</span></span>|<span data-ttu-id="e4eb1-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4eb1-126">xs:string</span></span>|<span data-ttu-id="e4eb1-127">Die Aktion, die für die Workflowanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="e4eb1-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e4eb1-128">AppDomain</span></span>|<span data-ttu-id="e4eb1-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4eb1-129">xs:string</span></span>|<span data-ttu-id="e4eb1-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
