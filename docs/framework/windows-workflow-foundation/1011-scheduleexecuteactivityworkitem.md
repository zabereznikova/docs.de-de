---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: dc209fc41dc6b076dfb897880f753be51f7fb0ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239691"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="eaa71-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="eaa71-102">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="eaa71-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eaa71-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eaa71-104">id</span><span class="sxs-lookup"><span data-stu-id="eaa71-104">ID</span></span>|<span data-ttu-id="eaa71-105">1011</span><span class="sxs-lookup"><span data-stu-id="eaa71-105">1011</span></span>|  
|<span data-ttu-id="eaa71-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="eaa71-106">Keywords</span></span>|<span data-ttu-id="eaa71-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="eaa71-107">WFRuntime</span></span>|  
|<span data-ttu-id="eaa71-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="eaa71-108">Level</span></span>|<span data-ttu-id="eaa71-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="eaa71-109">Verbose</span></span>|  
|<span data-ttu-id="eaa71-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="eaa71-110">Channel</span></span>|<span data-ttu-id="eaa71-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="eaa71-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eaa71-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eaa71-112">Description</span></span>  

 <span data-ttu-id="eaa71-113">Gibt an, dass eine ExecuteActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="eaa71-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eaa71-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="eaa71-114">Message</span></span>  

 <span data-ttu-id="eaa71-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="eaa71-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eaa71-116">Details</span><span class="sxs-lookup"><span data-stu-id="eaa71-116">Details</span></span>  
  
|<span data-ttu-id="eaa71-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="eaa71-117">Data Item Name</span></span>|<span data-ttu-id="eaa71-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="eaa71-118">Data Item Type</span></span>|<span data-ttu-id="eaa71-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eaa71-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eaa71-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="eaa71-120">Activity</span></span>|<span data-ttu-id="eaa71-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="eaa71-121">xs:string</span></span>|<span data-ttu-id="eaa71-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="eaa71-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="eaa71-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="eaa71-123">DisplayName</span></span>|<span data-ttu-id="eaa71-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="eaa71-124">xs:string</span></span>|<span data-ttu-id="eaa71-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="eaa71-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="eaa71-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="eaa71-126">InstanceId</span></span>|<span data-ttu-id="eaa71-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="eaa71-127">xs:string</span></span>|<span data-ttu-id="eaa71-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="eaa71-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="eaa71-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eaa71-129">AppDomain</span></span>|<span data-ttu-id="eaa71-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="eaa71-130">xs:string</span></span>|<span data-ttu-id="eaa71-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eaa71-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
