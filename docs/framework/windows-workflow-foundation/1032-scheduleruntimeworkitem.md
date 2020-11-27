---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: da35201f2b3e3bc07e0b9139b0584ce37011e168
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294312"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="30513-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="30513-102">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="30513-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="30513-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30513-104">id</span><span class="sxs-lookup"><span data-stu-id="30513-104">ID</span></span>|<span data-ttu-id="30513-105">1032</span><span class="sxs-lookup"><span data-stu-id="30513-105">1032</span></span>|  
|<span data-ttu-id="30513-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="30513-106">Keywords</span></span>|<span data-ttu-id="30513-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="30513-107">WFRuntime</span></span>|  
|<span data-ttu-id="30513-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="30513-108">Level</span></span>|<span data-ttu-id="30513-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="30513-109">Verbose</span></span>|  
|<span data-ttu-id="30513-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="30513-110">Channel</span></span>|<span data-ttu-id="30513-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="30513-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30513-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30513-112">Description</span></span>  

 <span data-ttu-id="30513-113">Gibt an, dass ein RuntimeWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="30513-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30513-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="30513-114">Message</span></span>  

 <span data-ttu-id="30513-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein Laufzeitarbeitselement geplant.</span><span class="sxs-lookup"><span data-stu-id="30513-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30513-116">Details</span><span class="sxs-lookup"><span data-stu-id="30513-116">Details</span></span>  
  
|<span data-ttu-id="30513-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="30513-117">Data Item Name</span></span>|<span data-ttu-id="30513-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="30513-118">Data Item Type</span></span>|<span data-ttu-id="30513-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30513-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30513-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="30513-120">Activity</span></span>|<span data-ttu-id="30513-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="30513-121">xs:string</span></span>|<span data-ttu-id="30513-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="30513-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="30513-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="30513-123">DisplayName</span></span>|<span data-ttu-id="30513-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="30513-124">xs:string</span></span>|<span data-ttu-id="30513-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="30513-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="30513-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="30513-126">InstanceId</span></span>|<span data-ttu-id="30513-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="30513-127">xs:string</span></span>|<span data-ttu-id="30513-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="30513-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="30513-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30513-129">AppDomain</span></span>|<span data-ttu-id="30513-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="30513-130">xs:string</span></span>|<span data-ttu-id="30513-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="30513-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
