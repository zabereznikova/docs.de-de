---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239769"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="444ce-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="444ce-102">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="444ce-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="444ce-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="444ce-104">id</span><span class="sxs-lookup"><span data-stu-id="444ce-104">ID</span></span>|<span data-ttu-id="444ce-105">1009</span><span class="sxs-lookup"><span data-stu-id="444ce-105">1009</span></span>|  
|<span data-ttu-id="444ce-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="444ce-106">Keywords</span></span>|<span data-ttu-id="444ce-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="444ce-107">WFRuntime</span></span>|  
|<span data-ttu-id="444ce-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="444ce-108">Level</span></span>|<span data-ttu-id="444ce-109">Information</span><span class="sxs-lookup"><span data-stu-id="444ce-109">Information</span></span>|  
|<span data-ttu-id="444ce-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="444ce-110">Channel</span></span>|<span data-ttu-id="444ce-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="444ce-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="444ce-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="444ce-112">Description</span></span>  

 <span data-ttu-id="444ce-113">Gibt an, dass die Ausführung einer Aktivität geplant wird.</span><span class="sxs-lookup"><span data-stu-id="444ce-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="444ce-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="444ce-114">Message</span></span>  

 <span data-ttu-id="444ce-115">Die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat die untergeordnete Aktivität '%4', DisplayName: '%5', InstanceId: '%6' geplant.</span><span class="sxs-lookup"><span data-stu-id="444ce-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="444ce-116">Details</span><span class="sxs-lookup"><span data-stu-id="444ce-116">Details</span></span>  
  
|<span data-ttu-id="444ce-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="444ce-117">Data Item Name</span></span>|<span data-ttu-id="444ce-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="444ce-118">Data Item Type</span></span>|<span data-ttu-id="444ce-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="444ce-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="444ce-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="444ce-120">ParentActivity</span></span>|<span data-ttu-id="444ce-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-121">xs:string</span></span>|<span data-ttu-id="444ce-122">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="444ce-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="444ce-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="444ce-123">ParentDisplayName</span></span>|<span data-ttu-id="444ce-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-124">xs:string</span></span>|<span data-ttu-id="444ce-125">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="444ce-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="444ce-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="444ce-126">ParentInstanceId</span></span>|<span data-ttu-id="444ce-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-127">xs:string</span></span>|<span data-ttu-id="444ce-128">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="444ce-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="444ce-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="444ce-129">ChildActivity</span></span>|<span data-ttu-id="444ce-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-130">xs:string</span></span>|<span data-ttu-id="444ce-131">Der Typname der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="444ce-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="444ce-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="444ce-132">ChildDisplayName</span></span>|<span data-ttu-id="444ce-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-133">xs:string</span></span>|<span data-ttu-id="444ce-134">Der Anzeigename der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="444ce-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="444ce-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="444ce-135">ChildInstanceId</span></span>|<span data-ttu-id="444ce-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-136">xs:string</span></span>|<span data-ttu-id="444ce-137">Die Instanz-ID der geplanten untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="444ce-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="444ce-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="444ce-138">AppDomain</span></span>|<span data-ttu-id="444ce-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="444ce-139">xs:string</span></span>|<span data-ttu-id="444ce-140">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="444ce-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
