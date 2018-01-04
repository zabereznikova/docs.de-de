---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81cc73a5ab58e90f1a0ee5bdaf9a491d20206fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="d6e79-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="d6e79-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d6e79-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d6e79-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6e79-104">ID</span><span class="sxs-lookup"><span data-stu-id="d6e79-104">ID</span></span>|<span data-ttu-id="d6e79-105">1032</span><span class="sxs-lookup"><span data-stu-id="d6e79-105">1032</span></span>|  
|<span data-ttu-id="d6e79-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d6e79-106">Keywords</span></span>|<span data-ttu-id="d6e79-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d6e79-107">WFRuntime</span></span>|  
|<span data-ttu-id="d6e79-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d6e79-108">Level</span></span>|<span data-ttu-id="d6e79-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="d6e79-109">Verbose</span></span>|  
|<span data-ttu-id="d6e79-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d6e79-110">Channel</span></span>|<span data-ttu-id="d6e79-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d6e79-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6e79-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6e79-112">Description</span></span>  
 <span data-ttu-id="d6e79-113">Gibt an, dass ein RuntimeWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="d6e79-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d6e79-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d6e79-114">Message</span></span>  
 <span data-ttu-id="d6e79-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine Laufzeitarbeitsaufgabe geplant.</span><span class="sxs-lookup"><span data-stu-id="d6e79-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d6e79-116">Details</span><span class="sxs-lookup"><span data-stu-id="d6e79-116">Details</span></span>  
  
|<span data-ttu-id="d6e79-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d6e79-117">Data Item Name</span></span>|<span data-ttu-id="d6e79-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d6e79-118">Data Item Type</span></span>|<span data-ttu-id="d6e79-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6e79-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d6e79-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="d6e79-120">Activity</span></span>|<span data-ttu-id="d6e79-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d6e79-121">xs:string</span></span>|<span data-ttu-id="d6e79-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d6e79-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d6e79-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d6e79-123">DisplayName</span></span>|<span data-ttu-id="d6e79-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d6e79-124">xs:string</span></span>|<span data-ttu-id="d6e79-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d6e79-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d6e79-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d6e79-126">InstanceId</span></span>|<span data-ttu-id="d6e79-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d6e79-127">xs:string</span></span>|<span data-ttu-id="d6e79-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d6e79-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d6e79-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d6e79-129">AppDomain</span></span>|<span data-ttu-id="d6e79-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d6e79-130">xs:string</span></span>|<span data-ttu-id="d6e79-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d6e79-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
