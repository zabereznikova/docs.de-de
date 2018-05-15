---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="425b9-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="425b9-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="425b9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="425b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="425b9-104">ID</span><span class="sxs-lookup"><span data-stu-id="425b9-104">ID</span></span>|<span data-ttu-id="425b9-105">1010</span><span class="sxs-lookup"><span data-stu-id="425b9-105">1010</span></span>|  
|<span data-ttu-id="425b9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="425b9-106">Keywords</span></span>|<span data-ttu-id="425b9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="425b9-107">WFRuntime</span></span>|  
|<span data-ttu-id="425b9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="425b9-108">Level</span></span>|<span data-ttu-id="425b9-109">Information</span><span class="sxs-lookup"><span data-stu-id="425b9-109">Information</span></span>|  
|<span data-ttu-id="425b9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="425b9-110">Channel</span></span>|<span data-ttu-id="425b9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="425b9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="425b9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="425b9-112">Description</span></span>  
 <span data-ttu-id="425b9-113">Gibt an, dass die Ausführung einer Aktivität beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="425b9-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="425b9-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="425b9-114">Message</span></span>  
 <span data-ttu-id="425b9-115">Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde mit dem Status '%4' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="425b9-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="425b9-116">Details</span><span class="sxs-lookup"><span data-stu-id="425b9-116">Details</span></span>  
  
|<span data-ttu-id="425b9-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="425b9-117">Data Item Name</span></span>|<span data-ttu-id="425b9-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="425b9-118">Data Item Type</span></span>|<span data-ttu-id="425b9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="425b9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="425b9-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="425b9-120">Activity</span></span>|<span data-ttu-id="425b9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="425b9-121">xs:string</span></span>|<span data-ttu-id="425b9-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="425b9-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="425b9-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="425b9-123">DisplayName</span></span>|<span data-ttu-id="425b9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="425b9-124">xs:string</span></span>|<span data-ttu-id="425b9-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="425b9-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="425b9-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="425b9-126">InstanceId</span></span>|<span data-ttu-id="425b9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="425b9-127">xs:string</span></span>|<span data-ttu-id="425b9-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="425b9-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="425b9-129">Zustand</span><span class="sxs-lookup"><span data-stu-id="425b9-129">State</span></span>|<span data-ttu-id="425b9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="425b9-130">xs:string</span></span>|<span data-ttu-id="425b9-131">Der Status der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="425b9-131">The state of the activity.</span></span>|  
|<span data-ttu-id="425b9-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="425b9-132">AppDomain</span></span>|<span data-ttu-id="425b9-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="425b9-133">xs:string</span></span>|<span data-ttu-id="425b9-134">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="425b9-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
