---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275556"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="32bf8-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="32bf8-102">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="32bf8-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="32bf8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32bf8-104">id</span><span class="sxs-lookup"><span data-stu-id="32bf8-104">ID</span></span>|<span data-ttu-id="32bf8-105">1014</span><span class="sxs-lookup"><span data-stu-id="32bf8-105">1014</span></span>|  
|<span data-ttu-id="32bf8-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="32bf8-106">Keywords</span></span>|<span data-ttu-id="32bf8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="32bf8-107">WFRuntime</span></span>|  
|<span data-ttu-id="32bf8-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="32bf8-108">Level</span></span>|<span data-ttu-id="32bf8-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="32bf8-109">Verbose</span></span>|  
|<span data-ttu-id="32bf8-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="32bf8-110">Channel</span></span>|<span data-ttu-id="32bf8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="32bf8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32bf8-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32bf8-112">Description</span></span>  

 <span data-ttu-id="32bf8-113">Gibt an, dass ein CompletionWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="32bf8-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32bf8-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="32bf8-114">Message</span></span>  

 <span data-ttu-id="32bf8-115">Für die übergeordnete Aktivität ' %1 ', Display Name: ' %2 ', InstanceId: ' %3 ' wurde eine completionworkitem geplant.</span><span class="sxs-lookup"><span data-stu-id="32bf8-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="32bf8-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="32bf8-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="32bf8-117">Details</span><span class="sxs-lookup"><span data-stu-id="32bf8-117">Details</span></span>  
  
|<span data-ttu-id="32bf8-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="32bf8-118">Data Item Name</span></span>|<span data-ttu-id="32bf8-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="32bf8-119">Data Item Type</span></span>|<span data-ttu-id="32bf8-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32bf8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32bf8-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="32bf8-121">ParentActivity</span></span>|<span data-ttu-id="32bf8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-122">xs:string</span></span>|<span data-ttu-id="32bf8-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="32bf8-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="32bf8-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="32bf8-124">ParentDisplayName</span></span>|<span data-ttu-id="32bf8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-125">xs:string</span></span>|<span data-ttu-id="32bf8-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="32bf8-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="32bf8-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="32bf8-127">ParentInstanceId</span></span>|<span data-ttu-id="32bf8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-128">xs:string</span></span>|<span data-ttu-id="32bf8-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="32bf8-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="32bf8-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="32bf8-130">CompletedActivity</span></span>|<span data-ttu-id="32bf8-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-131">xs:string</span></span>|<span data-ttu-id="32bf8-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="32bf8-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="32bf8-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="32bf8-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="32bf8-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-134">xs:string</span></span>|<span data-ttu-id="32bf8-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="32bf8-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="32bf8-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="32bf8-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="32bf8-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-137">xs:string</span></span>|<span data-ttu-id="32bf8-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="32bf8-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="32bf8-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="32bf8-139">AppDomain</span></span>|<span data-ttu-id="32bf8-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="32bf8-140">xs:string</span></span>|<span data-ttu-id="32bf8-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="32bf8-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
