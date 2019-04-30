---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008370"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="86405-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="86405-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="86405-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="86405-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86405-104">ID</span><span class="sxs-lookup"><span data-stu-id="86405-104">ID</span></span>|<span data-ttu-id="86405-105">1010</span><span class="sxs-lookup"><span data-stu-id="86405-105">1010</span></span>|  
|<span data-ttu-id="86405-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="86405-106">Keywords</span></span>|<span data-ttu-id="86405-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="86405-107">WFRuntime</span></span>|  
|<span data-ttu-id="86405-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="86405-108">Level</span></span>|<span data-ttu-id="86405-109">Information</span><span class="sxs-lookup"><span data-stu-id="86405-109">Information</span></span>|  
|<span data-ttu-id="86405-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="86405-110">Channel</span></span>|<span data-ttu-id="86405-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="86405-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="86405-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86405-112">Description</span></span>  
 <span data-ttu-id="86405-113">Gibt an, dass die Ausführung einer Aktivität beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="86405-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="86405-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="86405-114">Message</span></span>  
 <span data-ttu-id="86405-115">Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde mit dem Status '%4' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="86405-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="86405-116">Details</span><span class="sxs-lookup"><span data-stu-id="86405-116">Details</span></span>  
  
|<span data-ttu-id="86405-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="86405-117">Data Item Name</span></span>|<span data-ttu-id="86405-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="86405-118">Data Item Type</span></span>|<span data-ttu-id="86405-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86405-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="86405-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="86405-120">Activity</span></span>|<span data-ttu-id="86405-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="86405-121">xs:string</span></span>|<span data-ttu-id="86405-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="86405-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="86405-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="86405-123">DisplayName</span></span>|<span data-ttu-id="86405-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="86405-124">xs:string</span></span>|<span data-ttu-id="86405-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="86405-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="86405-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="86405-126">InstanceId</span></span>|<span data-ttu-id="86405-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="86405-127">xs:string</span></span>|<span data-ttu-id="86405-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="86405-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="86405-129">Zustand</span><span class="sxs-lookup"><span data-stu-id="86405-129">State</span></span>|<span data-ttu-id="86405-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="86405-130">xs:string</span></span>|<span data-ttu-id="86405-131">Der Status der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="86405-131">The state of the activity.</span></span>|  
|<span data-ttu-id="86405-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="86405-132">AppDomain</span></span>|<span data-ttu-id="86405-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="86405-133">xs:string</span></span>|<span data-ttu-id="86405-134">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86405-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
