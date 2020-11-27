---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: bd490aad24fba4550bc778799cd6f836dcfd466c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289177"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="a473c-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="a473c-102">57398 - MaxInstancesExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="a473c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a473c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a473c-104">id</span><span class="sxs-lookup"><span data-stu-id="a473c-104">ID</span></span>|<span data-ttu-id="a473c-105">57398</span><span class="sxs-lookup"><span data-stu-id="a473c-105">57398</span></span>|  
|<span data-ttu-id="a473c-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="a473c-106">Keywords</span></span>|<span data-ttu-id="a473c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="a473c-107">WFServices</span></span>|  
|<span data-ttu-id="a473c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a473c-108">Level</span></span>|<span data-ttu-id="a473c-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="a473c-109">Warning</span></span>|  
|<span data-ttu-id="a473c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a473c-110">Channel</span></span>|<span data-ttu-id="a473c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a473c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a473c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a473c-112">Description</span></span>  

 <span data-ttu-id="a473c-113">Gibt an, dass das System die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="a473c-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a473c-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="a473c-114">Message</span></span>  

 <span data-ttu-id="a473c-115">Das System hat die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht.</span><span class="sxs-lookup"><span data-stu-id="a473c-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="a473c-116">Die Grenze für diese Drosselung war auf %1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a473c-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="a473c-117">Der Drosselungswert kann geändert werden, indem das Attribut "maxConcurrentInstances" im serviceThrottle-Element oder die "MaxConcurrentInstances"-Eigenschaft im Verhalten "ServiceThrottlingBehavior" geändert wird.</span><span class="sxs-lookup"><span data-stu-id="a473c-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a473c-118">Details</span><span class="sxs-lookup"><span data-stu-id="a473c-118">Details</span></span>  
  
|<span data-ttu-id="a473c-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a473c-119">Data Item Name</span></span>|<span data-ttu-id="a473c-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a473c-120">Data Item Type</span></span>|<span data-ttu-id="a473c-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a473c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a473c-122">Name</span><span class="sxs-lookup"><span data-stu-id="a473c-122">Name</span></span>|<span data-ttu-id="a473c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a473c-123">xs:string</span></span>|<span data-ttu-id="a473c-124">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="a473c-124">The name of the item.</span></span>|  
|<span data-ttu-id="a473c-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a473c-125">AppDomain</span></span>|<span data-ttu-id="a473c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a473c-126">xs:string</span></span>|<span data-ttu-id="a473c-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a473c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
