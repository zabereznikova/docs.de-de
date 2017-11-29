---
title: 1017 - ScheduleCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6d348ec18b4d5eff7156d1e9809eb793ac1681d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="b73eb-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b73eb-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b73eb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b73eb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b73eb-104">ID</span><span class="sxs-lookup"><span data-stu-id="b73eb-104">ID</span></span>|<span data-ttu-id="b73eb-105">1017</span><span class="sxs-lookup"><span data-stu-id="b73eb-105">1017</span></span>|  
|<span data-ttu-id="b73eb-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b73eb-106">Keywords</span></span>|<span data-ttu-id="b73eb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b73eb-107">WFRuntime</span></span>|  
|<span data-ttu-id="b73eb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b73eb-108">Level</span></span>|<span data-ttu-id="b73eb-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="b73eb-109">Verbose</span></span>|  
|<span data-ttu-id="b73eb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b73eb-110">Channel</span></span>|<span data-ttu-id="b73eb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b73eb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b73eb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b73eb-112">Description</span></span>  
 <span data-ttu-id="b73eb-113">Gibt an, dass ein CancelActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="b73eb-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b73eb-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b73eb-114">Message</span></span>  
 <span data-ttu-id="b73eb-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CancelActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="b73eb-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b73eb-116">Details</span><span class="sxs-lookup"><span data-stu-id="b73eb-116">Details</span></span>  
  
|<span data-ttu-id="b73eb-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b73eb-117">Data Item Name</span></span>|<span data-ttu-id="b73eb-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b73eb-118">Data Item Type</span></span>|<span data-ttu-id="b73eb-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b73eb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b73eb-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="b73eb-120">Activity</span></span>|<span data-ttu-id="b73eb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b73eb-121">xs:string</span></span>|<span data-ttu-id="b73eb-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b73eb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b73eb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b73eb-123">DisplayName</span></span>|<span data-ttu-id="b73eb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b73eb-124">xs:string</span></span>|<span data-ttu-id="b73eb-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b73eb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b73eb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b73eb-126">InstanceId</span></span>|<span data-ttu-id="b73eb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b73eb-127">xs:string</span></span>|<span data-ttu-id="b73eb-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b73eb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b73eb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b73eb-129">AppDomain</span></span>|<span data-ttu-id="b73eb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b73eb-130">xs:string</span></span>|<span data-ttu-id="b73eb-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b73eb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
