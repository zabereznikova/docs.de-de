---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba48f19de1be3cfd2461e159b91fa365e24ee750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="322a5-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="322a5-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="322a5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="322a5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="322a5-104">ID</span><span class="sxs-lookup"><span data-stu-id="322a5-104">ID</span></span>|<span data-ttu-id="322a5-105">57398</span><span class="sxs-lookup"><span data-stu-id="322a5-105">57398</span></span>|  
|<span data-ttu-id="322a5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="322a5-106">Keywords</span></span>|<span data-ttu-id="322a5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="322a5-107">WFServices</span></span>|  
|<span data-ttu-id="322a5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="322a5-108">Level</span></span>|<span data-ttu-id="322a5-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="322a5-109">Warning</span></span>|  
|<span data-ttu-id="322a5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="322a5-110">Channel</span></span>|<span data-ttu-id="322a5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="322a5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="322a5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="322a5-112">Description</span></span>  
 <span data-ttu-id="322a5-113">Gibt an, dass das System die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="322a5-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="322a5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="322a5-114">Message</span></span>  
 <span data-ttu-id="322a5-115">Das System hat die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht.</span><span class="sxs-lookup"><span data-stu-id="322a5-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="322a5-116">Die Grenze für diese Drosselung war auf %1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="322a5-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="322a5-117">Der Drosselungswert kann geändert werden, indem das Attribut "maxConcurrentInstances" im serviceThrottle-Element oder die "MaxConcurrentInstances"-Eigenschaft im Verhalten "ServiceThrottlingBehavior" geändert wird.</span><span class="sxs-lookup"><span data-stu-id="322a5-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="322a5-118">Details</span><span class="sxs-lookup"><span data-stu-id="322a5-118">Details</span></span>  
  
|<span data-ttu-id="322a5-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="322a5-119">Data Item Name</span></span>|<span data-ttu-id="322a5-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="322a5-120">Data Item Type</span></span>|<span data-ttu-id="322a5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="322a5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="322a5-122">Name</span><span class="sxs-lookup"><span data-stu-id="322a5-122">Name</span></span>|<span data-ttu-id="322a5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="322a5-123">xs:string</span></span>|<span data-ttu-id="322a5-124">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="322a5-124">The name of the item.</span></span>|  
|<span data-ttu-id="322a5-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="322a5-125">AppDomain</span></span>|<span data-ttu-id="322a5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="322a5-126">xs:string</span></span>|<span data-ttu-id="322a5-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="322a5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
