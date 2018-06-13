---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509971"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="4c96b-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="4c96b-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="4c96b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4c96b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c96b-104">ID</span><span class="sxs-lookup"><span data-stu-id="4c96b-104">ID</span></span>|<span data-ttu-id="4c96b-105">1009</span><span class="sxs-lookup"><span data-stu-id="4c96b-105">1009</span></span>|  
|<span data-ttu-id="4c96b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4c96b-106">Keywords</span></span>|<span data-ttu-id="4c96b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4c96b-107">WFRuntime</span></span>|  
|<span data-ttu-id="4c96b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4c96b-108">Level</span></span>|<span data-ttu-id="4c96b-109">Information</span><span class="sxs-lookup"><span data-stu-id="4c96b-109">Information</span></span>|  
|<span data-ttu-id="4c96b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4c96b-110">Channel</span></span>|<span data-ttu-id="4c96b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4c96b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4c96b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c96b-112">Description</span></span>  
 <span data-ttu-id="4c96b-113">Gibt an, dass die Ausführung einer Aktivität geplant wird.</span><span class="sxs-lookup"><span data-stu-id="4c96b-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4c96b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4c96b-114">Message</span></span>  
 <span data-ttu-id="4c96b-115">Die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat die untergeordnete Aktivität '%4', DisplayName: '%5', InstanceId: '%6' geplant.</span><span class="sxs-lookup"><span data-stu-id="4c96b-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c96b-116">Details</span><span class="sxs-lookup"><span data-stu-id="4c96b-116">Details</span></span>  
  
|<span data-ttu-id="4c96b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4c96b-117">Data Item Name</span></span>|<span data-ttu-id="4c96b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4c96b-118">Data Item Type</span></span>|<span data-ttu-id="4c96b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c96b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4c96b-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="4c96b-120">ParentActivity</span></span>|<span data-ttu-id="4c96b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-121">xs:string</span></span>|<span data-ttu-id="4c96b-122">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4c96b-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="4c96b-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="4c96b-123">ParentDisplayName</span></span>|<span data-ttu-id="4c96b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-124">xs:string</span></span>|<span data-ttu-id="4c96b-125">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4c96b-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="4c96b-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="4c96b-126">ParentInstanceId</span></span>|<span data-ttu-id="4c96b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-127">xs:string</span></span>|<span data-ttu-id="4c96b-128">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4c96b-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="4c96b-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="4c96b-129">ChildActivity</span></span>|<span data-ttu-id="4c96b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-130">xs:string</span></span>|<span data-ttu-id="4c96b-131">Der Typname der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4c96b-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="4c96b-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="4c96b-132">ChildDisplayName</span></span>|<span data-ttu-id="4c96b-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-133">xs:string</span></span>|<span data-ttu-id="4c96b-134">Der Anzeigename der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4c96b-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="4c96b-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="4c96b-135">ChildInstanceId</span></span>|<span data-ttu-id="4c96b-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-136">xs:string</span></span>|<span data-ttu-id="4c96b-137">Die Instanz-ID der geplanten untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4c96b-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="4c96b-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4c96b-138">AppDomain</span></span>|<span data-ttu-id="4c96b-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c96b-139">xs:string</span></span>|<span data-ttu-id="4c96b-140">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4c96b-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
