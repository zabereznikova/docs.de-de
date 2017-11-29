---
title: 1010 - ActivityCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1378ddd1550db614c9eddc44f79b19ff94ed585c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="35b0e-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="35b0e-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="35b0e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="35b0e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35b0e-104">ID</span><span class="sxs-lookup"><span data-stu-id="35b0e-104">ID</span></span>|<span data-ttu-id="35b0e-105">1010</span><span class="sxs-lookup"><span data-stu-id="35b0e-105">1010</span></span>|  
|<span data-ttu-id="35b0e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="35b0e-106">Keywords</span></span>|<span data-ttu-id="35b0e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="35b0e-107">WFRuntime</span></span>|  
|<span data-ttu-id="35b0e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="35b0e-108">Level</span></span>|<span data-ttu-id="35b0e-109">Information</span><span class="sxs-lookup"><span data-stu-id="35b0e-109">Information</span></span>|  
|<span data-ttu-id="35b0e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="35b0e-110">Channel</span></span>|<span data-ttu-id="35b0e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="35b0e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35b0e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35b0e-112">Description</span></span>  
 <span data-ttu-id="35b0e-113">Gibt an, dass die Ausführung einer Aktivität beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="35b0e-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35b0e-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="35b0e-114">Message</span></span>  
 <span data-ttu-id="35b0e-115">Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde mit dem Status '%4' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="35b0e-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35b0e-116">Details</span><span class="sxs-lookup"><span data-stu-id="35b0e-116">Details</span></span>  
  
|<span data-ttu-id="35b0e-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="35b0e-117">Data Item Name</span></span>|<span data-ttu-id="35b0e-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="35b0e-118">Data Item Type</span></span>|<span data-ttu-id="35b0e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35b0e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35b0e-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="35b0e-120">Activity</span></span>|<span data-ttu-id="35b0e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b0e-121">xs:string</span></span>|<span data-ttu-id="35b0e-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="35b0e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="35b0e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="35b0e-123">DisplayName</span></span>|<span data-ttu-id="35b0e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b0e-124">xs:string</span></span>|<span data-ttu-id="35b0e-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="35b0e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="35b0e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="35b0e-126">InstanceId</span></span>|<span data-ttu-id="35b0e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b0e-127">xs:string</span></span>|<span data-ttu-id="35b0e-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="35b0e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="35b0e-129">Zustand</span><span class="sxs-lookup"><span data-stu-id="35b0e-129">State</span></span>|<span data-ttu-id="35b0e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b0e-130">xs:string</span></span>|<span data-ttu-id="35b0e-131">Der Status der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="35b0e-131">The state of the activity.</span></span>|  
|<span data-ttu-id="35b0e-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35b0e-132">AppDomain</span></span>|<span data-ttu-id="35b0e-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="35b0e-133">xs:string</span></span>|<span data-ttu-id="35b0e-134">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="35b0e-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
