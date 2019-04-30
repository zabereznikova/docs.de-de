---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982266"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="3ae8e-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="3ae8e-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3ae8e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3ae8e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ae8e-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ae8e-104">ID</span></span>|<span data-ttu-id="3ae8e-105">1014</span><span class="sxs-lookup"><span data-stu-id="3ae8e-105">1014</span></span>|  
|<span data-ttu-id="3ae8e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3ae8e-106">Keywords</span></span>|<span data-ttu-id="3ae8e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3ae8e-107">WFRuntime</span></span>|  
|<span data-ttu-id="3ae8e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3ae8e-108">Level</span></span>|<span data-ttu-id="3ae8e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="3ae8e-109">Verbose</span></span>|  
|<span data-ttu-id="3ae8e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3ae8e-110">Channel</span></span>|<span data-ttu-id="3ae8e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3ae8e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ae8e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ae8e-112">Description</span></span>  
 <span data-ttu-id="3ae8e-113">Gibt an, dass ein CompletionWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ae8e-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3ae8e-114">Message</span></span>  
 <span data-ttu-id="3ae8e-115">Wurde eine CompletionWorkItem geplant für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3ae8e-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ae8e-117">Details</span><span class="sxs-lookup"><span data-stu-id="3ae8e-117">Details</span></span>  
  
|<span data-ttu-id="3ae8e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3ae8e-118">Data Item Name</span></span>|<span data-ttu-id="3ae8e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3ae8e-119">Data Item Type</span></span>|<span data-ttu-id="3ae8e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ae8e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ae8e-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="3ae8e-121">ParentActivity</span></span>|<span data-ttu-id="3ae8e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-122">xs:string</span></span>|<span data-ttu-id="3ae8e-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="3ae8e-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="3ae8e-124">ParentDisplayName</span></span>|<span data-ttu-id="3ae8e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-125">xs:string</span></span>|<span data-ttu-id="3ae8e-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="3ae8e-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="3ae8e-127">ParentInstanceId</span></span>|<span data-ttu-id="3ae8e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-128">xs:string</span></span>|<span data-ttu-id="3ae8e-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="3ae8e-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="3ae8e-130">CompletedActivity</span></span>|<span data-ttu-id="3ae8e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-131">xs:string</span></span>|<span data-ttu-id="3ae8e-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="3ae8e-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3ae8e-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="3ae8e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-134">xs:string</span></span>|<span data-ttu-id="3ae8e-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="3ae8e-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3ae8e-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="3ae8e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-137">xs:string</span></span>|<span data-ttu-id="3ae8e-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="3ae8e-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ae8e-139">AppDomain</span></span>|<span data-ttu-id="3ae8e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae8e-140">xs:string</span></span>|<span data-ttu-id="3ae8e-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3ae8e-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
