---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510366"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="1785d-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="1785d-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1785d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1785d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1785d-104">ID</span><span class="sxs-lookup"><span data-stu-id="1785d-104">ID</span></span>|<span data-ttu-id="1785d-105">1014</span><span class="sxs-lookup"><span data-stu-id="1785d-105">1014</span></span>|  
|<span data-ttu-id="1785d-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1785d-106">Keywords</span></span>|<span data-ttu-id="1785d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1785d-107">WFRuntime</span></span>|  
|<span data-ttu-id="1785d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1785d-108">Level</span></span>|<span data-ttu-id="1785d-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="1785d-109">Verbose</span></span>|  
|<span data-ttu-id="1785d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1785d-110">Channel</span></span>|<span data-ttu-id="1785d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1785d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1785d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1785d-112">Description</span></span>  
 <span data-ttu-id="1785d-113">Gibt an, dass ein CompletionWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="1785d-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1785d-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1785d-114">Message</span></span>  
 <span data-ttu-id="1785d-115">Wurde eine CompletionWorkItem geplant für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="1785d-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1785d-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="1785d-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1785d-117">Details</span><span class="sxs-lookup"><span data-stu-id="1785d-117">Details</span></span>  
  
|<span data-ttu-id="1785d-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1785d-118">Data Item Name</span></span>|<span data-ttu-id="1785d-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1785d-119">Data Item Type</span></span>|<span data-ttu-id="1785d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1785d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1785d-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="1785d-121">ParentActivity</span></span>|<span data-ttu-id="1785d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-122">xs:string</span></span>|<span data-ttu-id="1785d-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1785d-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="1785d-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="1785d-124">ParentDisplayName</span></span>|<span data-ttu-id="1785d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-125">xs:string</span></span>|<span data-ttu-id="1785d-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1785d-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="1785d-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="1785d-127">ParentInstanceId</span></span>|<span data-ttu-id="1785d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-128">xs:string</span></span>|<span data-ttu-id="1785d-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1785d-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="1785d-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="1785d-130">CompletedActivity</span></span>|<span data-ttu-id="1785d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-131">xs:string</span></span>|<span data-ttu-id="1785d-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1785d-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="1785d-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="1785d-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="1785d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-134">xs:string</span></span>|<span data-ttu-id="1785d-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1785d-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="1785d-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="1785d-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="1785d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-137">xs:string</span></span>|<span data-ttu-id="1785d-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1785d-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="1785d-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1785d-139">AppDomain</span></span>|<span data-ttu-id="1785d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="1785d-140">xs:string</span></span>|<span data-ttu-id="1785d-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1785d-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
