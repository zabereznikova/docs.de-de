---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7457b65f81e9e26b9de6055df474a83ce4264846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="f9004-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="f9004-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f9004-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f9004-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9004-104">ID</span><span class="sxs-lookup"><span data-stu-id="f9004-104">ID</span></span>|<span data-ttu-id="f9004-105">1015</span><span class="sxs-lookup"><span data-stu-id="f9004-105">1015</span></span>|  
|<span data-ttu-id="f9004-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f9004-106">Keywords</span></span>|<span data-ttu-id="f9004-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f9004-107">WFRuntime</span></span>|  
|<span data-ttu-id="f9004-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f9004-108">Level</span></span>|<span data-ttu-id="f9004-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="f9004-109">Verbose</span></span>|  
|<span data-ttu-id="f9004-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f9004-110">Channel</span></span>|<span data-ttu-id="f9004-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f9004-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f9004-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9004-112">Description</span></span>  
 <span data-ttu-id="f9004-113">Gibt an, dass ein CompletionWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="f9004-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f9004-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f9004-114">Message</span></span>  
 <span data-ttu-id="f9004-115">Die Ausführung einer CompletionWorkItem für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="f9004-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="f9004-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="f9004-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f9004-117">Details</span><span class="sxs-lookup"><span data-stu-id="f9004-117">Details</span></span>  
  
|<span data-ttu-id="f9004-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f9004-118">Data Item Name</span></span>|<span data-ttu-id="f9004-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f9004-119">Data Item Type</span></span>|<span data-ttu-id="f9004-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9004-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f9004-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="f9004-121">ParentActivity</span></span>|<span data-ttu-id="f9004-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-122">xs:string</span></span>|<span data-ttu-id="f9004-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f9004-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="f9004-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="f9004-124">ParentDisplayName</span></span>|<span data-ttu-id="f9004-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-125">xs:string</span></span>|<span data-ttu-id="f9004-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f9004-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="f9004-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="f9004-127">ParentInstanceId</span></span>|<span data-ttu-id="f9004-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-128">xs:string</span></span>|<span data-ttu-id="f9004-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f9004-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="f9004-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="f9004-130">CompletedActivity</span></span>|<span data-ttu-id="f9004-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-131">xs:string</span></span>|<span data-ttu-id="f9004-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f9004-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="f9004-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f9004-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="f9004-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-134">xs:string</span></span>|<span data-ttu-id="f9004-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f9004-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="f9004-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f9004-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="f9004-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-137">xs:string</span></span>|<span data-ttu-id="f9004-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f9004-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="f9004-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f9004-139">AppDomain</span></span>|<span data-ttu-id="f9004-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f9004-140">xs:string</span></span>|<span data-ttu-id="f9004-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f9004-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
