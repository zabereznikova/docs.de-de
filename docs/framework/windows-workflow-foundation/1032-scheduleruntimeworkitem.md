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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4de69b1fc2647d7723db8aebb02942938db7478f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="eabf1-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="eabf1-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="eabf1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eabf1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eabf1-104">ID</span><span class="sxs-lookup"><span data-stu-id="eabf1-104">ID</span></span>|<span data-ttu-id="eabf1-105">1032</span><span class="sxs-lookup"><span data-stu-id="eabf1-105">1032</span></span>|  
|<span data-ttu-id="eabf1-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="eabf1-106">Keywords</span></span>|<span data-ttu-id="eabf1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="eabf1-107">WFRuntime</span></span>|  
|<span data-ttu-id="eabf1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="eabf1-108">Level</span></span>|<span data-ttu-id="eabf1-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="eabf1-109">Verbose</span></span>|  
|<span data-ttu-id="eabf1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="eabf1-110">Channel</span></span>|<span data-ttu-id="eabf1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="eabf1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eabf1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eabf1-112">Description</span></span>  
 <span data-ttu-id="eabf1-113">Gibt an, dass ein RuntimeWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="eabf1-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eabf1-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="eabf1-114">Message</span></span>  
 <span data-ttu-id="eabf1-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine Laufzeitarbeitsaufgabe geplant.</span><span class="sxs-lookup"><span data-stu-id="eabf1-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eabf1-116">Details</span><span class="sxs-lookup"><span data-stu-id="eabf1-116">Details</span></span>  
  
|<span data-ttu-id="eabf1-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="eabf1-117">Data Item Name</span></span>|<span data-ttu-id="eabf1-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="eabf1-118">Data Item Type</span></span>|<span data-ttu-id="eabf1-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eabf1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eabf1-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="eabf1-120">Activity</span></span>|<span data-ttu-id="eabf1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="eabf1-121">xs:string</span></span>|<span data-ttu-id="eabf1-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="eabf1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="eabf1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="eabf1-123">DisplayName</span></span>|<span data-ttu-id="eabf1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="eabf1-124">xs:string</span></span>|<span data-ttu-id="eabf1-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="eabf1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="eabf1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="eabf1-126">InstanceId</span></span>|<span data-ttu-id="eabf1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="eabf1-127">xs:string</span></span>|<span data-ttu-id="eabf1-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="eabf1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="eabf1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eabf1-129">AppDomain</span></span>|<span data-ttu-id="eabf1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="eabf1-130">xs:string</span></span>|<span data-ttu-id="eabf1-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eabf1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
