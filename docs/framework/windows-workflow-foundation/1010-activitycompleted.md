---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: d0ebf32ec1d5fe5b34ffe650d5547891be0eb665
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239912"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="fafdb-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="fafdb-102">1010 - ActivityCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="fafdb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fafdb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fafdb-104">id</span><span class="sxs-lookup"><span data-stu-id="fafdb-104">ID</span></span>|<span data-ttu-id="fafdb-105">1010</span><span class="sxs-lookup"><span data-stu-id="fafdb-105">1010</span></span>|  
|<span data-ttu-id="fafdb-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="fafdb-106">Keywords</span></span>|<span data-ttu-id="fafdb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fafdb-107">WFRuntime</span></span>|  
|<span data-ttu-id="fafdb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fafdb-108">Level</span></span>|<span data-ttu-id="fafdb-109">Information</span><span class="sxs-lookup"><span data-stu-id="fafdb-109">Information</span></span>|  
|<span data-ttu-id="fafdb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fafdb-110">Channel</span></span>|<span data-ttu-id="fafdb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fafdb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fafdb-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fafdb-112">Description</span></span>  

 <span data-ttu-id="fafdb-113">Gibt an, dass die Ausführung einer Aktivität beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fafdb-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fafdb-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="fafdb-114">Message</span></span>  

 <span data-ttu-id="fafdb-115">Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde mit dem Status '%4' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fafdb-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fafdb-116">Details</span><span class="sxs-lookup"><span data-stu-id="fafdb-116">Details</span></span>  
  
|<span data-ttu-id="fafdb-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fafdb-117">Data Item Name</span></span>|<span data-ttu-id="fafdb-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fafdb-118">Data Item Type</span></span>|<span data-ttu-id="fafdb-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fafdb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fafdb-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="fafdb-120">Activity</span></span>|<span data-ttu-id="fafdb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fafdb-121">xs:string</span></span>|<span data-ttu-id="fafdb-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fafdb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fafdb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fafdb-123">DisplayName</span></span>|<span data-ttu-id="fafdb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fafdb-124">xs:string</span></span>|<span data-ttu-id="fafdb-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fafdb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fafdb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fafdb-126">InstanceId</span></span>|<span data-ttu-id="fafdb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fafdb-127">xs:string</span></span>|<span data-ttu-id="fafdb-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fafdb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fafdb-129">State</span><span class="sxs-lookup"><span data-stu-id="fafdb-129">State</span></span>|<span data-ttu-id="fafdb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fafdb-130">xs:string</span></span>|<span data-ttu-id="fafdb-131">Der Status der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fafdb-131">The state of the activity.</span></span>|  
|<span data-ttu-id="fafdb-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fafdb-132">AppDomain</span></span>|<span data-ttu-id="fafdb-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="fafdb-133">xs:string</span></span>|<span data-ttu-id="fafdb-134">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fafdb-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
