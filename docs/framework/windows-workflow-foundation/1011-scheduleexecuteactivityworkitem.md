---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec89acb9d83a28ac280db7c3d536bfe63669fa97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="77e33-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="77e33-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="77e33-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77e33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77e33-104">ID</span><span class="sxs-lookup"><span data-stu-id="77e33-104">ID</span></span>|<span data-ttu-id="77e33-105">1011</span><span class="sxs-lookup"><span data-stu-id="77e33-105">1011</span></span>|  
|<span data-ttu-id="77e33-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="77e33-106">Keywords</span></span>|<span data-ttu-id="77e33-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="77e33-107">WFRuntime</span></span>|  
|<span data-ttu-id="77e33-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="77e33-108">Level</span></span>|<span data-ttu-id="77e33-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="77e33-109">Verbose</span></span>|  
|<span data-ttu-id="77e33-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="77e33-110">Channel</span></span>|<span data-ttu-id="77e33-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="77e33-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="77e33-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77e33-112">Description</span></span>  
 <span data-ttu-id="77e33-113">Gibt an, dass eine ExecuteActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="77e33-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="77e33-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="77e33-114">Message</span></span>  
 <span data-ttu-id="77e33-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="77e33-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="77e33-116">Details</span><span class="sxs-lookup"><span data-stu-id="77e33-116">Details</span></span>  
  
|<span data-ttu-id="77e33-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="77e33-117">Data Item Name</span></span>|<span data-ttu-id="77e33-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="77e33-118">Data Item Type</span></span>|<span data-ttu-id="77e33-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77e33-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="77e33-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="77e33-120">Activity</span></span>|<span data-ttu-id="77e33-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="77e33-121">xs:string</span></span>|<span data-ttu-id="77e33-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="77e33-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="77e33-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="77e33-123">DisplayName</span></span>|<span data-ttu-id="77e33-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="77e33-124">xs:string</span></span>|<span data-ttu-id="77e33-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="77e33-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="77e33-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="77e33-126">InstanceId</span></span>|<span data-ttu-id="77e33-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="77e33-127">xs:string</span></span>|<span data-ttu-id="77e33-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="77e33-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="77e33-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="77e33-129">AppDomain</span></span>|<span data-ttu-id="77e33-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="77e33-130">xs:string</span></span>|<span data-ttu-id="77e33-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="77e33-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
