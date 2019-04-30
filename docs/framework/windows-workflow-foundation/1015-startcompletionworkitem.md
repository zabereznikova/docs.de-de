---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032265"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="475ad-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="475ad-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="475ad-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="475ad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="475ad-104">ID</span><span class="sxs-lookup"><span data-stu-id="475ad-104">ID</span></span>|<span data-ttu-id="475ad-105">1015</span><span class="sxs-lookup"><span data-stu-id="475ad-105">1015</span></span>|  
|<span data-ttu-id="475ad-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="475ad-106">Keywords</span></span>|<span data-ttu-id="475ad-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="475ad-107">WFRuntime</span></span>|  
|<span data-ttu-id="475ad-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="475ad-108">Level</span></span>|<span data-ttu-id="475ad-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="475ad-109">Verbose</span></span>|  
|<span data-ttu-id="475ad-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="475ad-110">Channel</span></span>|<span data-ttu-id="475ad-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="475ad-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="475ad-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="475ad-112">Description</span></span>  
 <span data-ttu-id="475ad-113">Gibt an, dass ein CompletionWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="475ad-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="475ad-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="475ad-114">Message</span></span>  
 <span data-ttu-id="475ad-115">Die Ausführung einer CompletionWorkItem für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="475ad-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="475ad-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="475ad-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="475ad-117">Details</span><span class="sxs-lookup"><span data-stu-id="475ad-117">Details</span></span>  
  
|<span data-ttu-id="475ad-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="475ad-118">Data Item Name</span></span>|<span data-ttu-id="475ad-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="475ad-119">Data Item Type</span></span>|<span data-ttu-id="475ad-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="475ad-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="475ad-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="475ad-121">ParentActivity</span></span>|<span data-ttu-id="475ad-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-122">xs:string</span></span>|<span data-ttu-id="475ad-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="475ad-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="475ad-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="475ad-124">ParentDisplayName</span></span>|<span data-ttu-id="475ad-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-125">xs:string</span></span>|<span data-ttu-id="475ad-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="475ad-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="475ad-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="475ad-127">ParentInstanceId</span></span>|<span data-ttu-id="475ad-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-128">xs:string</span></span>|<span data-ttu-id="475ad-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="475ad-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="475ad-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="475ad-130">CompletedActivity</span></span>|<span data-ttu-id="475ad-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-131">xs:string</span></span>|<span data-ttu-id="475ad-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="475ad-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="475ad-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="475ad-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="475ad-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-134">xs:string</span></span>|<span data-ttu-id="475ad-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="475ad-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="475ad-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="475ad-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="475ad-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-137">xs:string</span></span>|<span data-ttu-id="475ad-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="475ad-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="475ad-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="475ad-139">AppDomain</span></span>|<span data-ttu-id="475ad-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="475ad-140">xs:string</span></span>|<span data-ttu-id="475ad-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="475ad-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
