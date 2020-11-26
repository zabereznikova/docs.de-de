---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238937"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="8eeb0-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="8eeb0-102">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="8eeb0-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8eeb0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8eeb0-104">id</span><span class="sxs-lookup"><span data-stu-id="8eeb0-104">ID</span></span>|<span data-ttu-id="8eeb0-105">1041</span><span class="sxs-lookup"><span data-stu-id="8eeb0-105">1041</span></span>|  
|<span data-ttu-id="8eeb0-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="8eeb0-106">Keywords</span></span>|<span data-ttu-id="8eeb0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8eeb0-107">WFRuntime</span></span>|  
|<span data-ttu-id="8eeb0-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8eeb0-108">Level</span></span>|<span data-ttu-id="8eeb0-109">Information</span><span class="sxs-lookup"><span data-stu-id="8eeb0-109">Information</span></span>|  
|<span data-ttu-id="8eeb0-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8eeb0-110">Channel</span></span>|<span data-ttu-id="8eeb0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8eeb0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8eeb0-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8eeb0-112">Description</span></span>  

 <span data-ttu-id="8eeb0-113">Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="8eeb0-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="8eeb0-114">Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8eeb0-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8eeb0-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="8eeb0-115">Message</span></span>  

 <span data-ttu-id="8eeb0-116">WorkflowApplication-ID: ' %1 ' ist im Leerlauf und dauerhaft.</span><span class="sxs-lookup"><span data-stu-id="8eeb0-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="8eeb0-117">Die folgende Aktion wird ausgeführt: %2.</span><span class="sxs-lookup"><span data-stu-id="8eeb0-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8eeb0-118">Details</span><span class="sxs-lookup"><span data-stu-id="8eeb0-118">Details</span></span>  
  
|<span data-ttu-id="8eeb0-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8eeb0-119">Data Item Name</span></span>|<span data-ttu-id="8eeb0-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8eeb0-120">Data Item Type</span></span>|<span data-ttu-id="8eeb0-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8eeb0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8eeb0-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="8eeb0-122">WorkflowApplicationId</span></span>|<span data-ttu-id="8eeb0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="8eeb0-123">xs:string</span></span>|<span data-ttu-id="8eeb0-124">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="8eeb0-124">The workflow application id</span></span>|  
|<span data-ttu-id="8eeb0-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="8eeb0-125">ActionTaken</span></span>|<span data-ttu-id="8eeb0-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8eeb0-126">xs:string</span></span>|<span data-ttu-id="8eeb0-127">Die Aktion, die für die Workflowanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8eeb0-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="8eeb0-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8eeb0-128">AppDomain</span></span>|<span data-ttu-id="8eeb0-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="8eeb0-129">xs:string</span></span>|<span data-ttu-id="8eeb0-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8eeb0-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
