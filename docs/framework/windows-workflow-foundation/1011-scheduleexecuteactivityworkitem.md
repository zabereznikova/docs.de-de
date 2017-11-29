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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 498752bfc896891a43a6a2e7a8245c508795c1ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="60eee-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="60eee-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="60eee-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="60eee-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60eee-104">ID</span><span class="sxs-lookup"><span data-stu-id="60eee-104">ID</span></span>|<span data-ttu-id="60eee-105">1011</span><span class="sxs-lookup"><span data-stu-id="60eee-105">1011</span></span>|  
|<span data-ttu-id="60eee-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="60eee-106">Keywords</span></span>|<span data-ttu-id="60eee-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="60eee-107">WFRuntime</span></span>|  
|<span data-ttu-id="60eee-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="60eee-108">Level</span></span>|<span data-ttu-id="60eee-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="60eee-109">Verbose</span></span>|  
|<span data-ttu-id="60eee-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="60eee-110">Channel</span></span>|<span data-ttu-id="60eee-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="60eee-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60eee-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60eee-112">Description</span></span>  
 <span data-ttu-id="60eee-113">Gibt an, dass eine ExecuteActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="60eee-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60eee-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="60eee-114">Message</span></span>  
 <span data-ttu-id="60eee-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="60eee-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60eee-116">Details</span><span class="sxs-lookup"><span data-stu-id="60eee-116">Details</span></span>  
  
|<span data-ttu-id="60eee-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="60eee-117">Data Item Name</span></span>|<span data-ttu-id="60eee-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="60eee-118">Data Item Type</span></span>|<span data-ttu-id="60eee-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60eee-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60eee-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="60eee-120">Activity</span></span>|<span data-ttu-id="60eee-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="60eee-121">xs:string</span></span>|<span data-ttu-id="60eee-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60eee-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="60eee-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="60eee-123">DisplayName</span></span>|<span data-ttu-id="60eee-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="60eee-124">xs:string</span></span>|<span data-ttu-id="60eee-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60eee-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="60eee-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="60eee-126">InstanceId</span></span>|<span data-ttu-id="60eee-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="60eee-127">xs:string</span></span>|<span data-ttu-id="60eee-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60eee-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="60eee-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="60eee-129">AppDomain</span></span>|<span data-ttu-id="60eee-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="60eee-130">xs:string</span></span>|<span data-ttu-id="60eee-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="60eee-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
