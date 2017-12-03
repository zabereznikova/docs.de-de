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
ms.openlocfilehash: 803616fdd287491afa27d3ac23dfce99c5db08ca
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="1d544-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="1d544-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="1d544-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d544-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d544-104">ID</span><span class="sxs-lookup"><span data-stu-id="1d544-104">ID</span></span>|<span data-ttu-id="1d544-105">57398</span><span class="sxs-lookup"><span data-stu-id="1d544-105">57398</span></span>|  
|<span data-ttu-id="1d544-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1d544-106">Keywords</span></span>|<span data-ttu-id="1d544-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="1d544-107">WFServices</span></span>|  
|<span data-ttu-id="1d544-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1d544-108">Level</span></span>|<span data-ttu-id="1d544-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="1d544-109">Warning</span></span>|  
|<span data-ttu-id="1d544-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1d544-110">Channel</span></span>|<span data-ttu-id="1d544-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1d544-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d544-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d544-112">Description</span></span>  
 <span data-ttu-id="1d544-113">Gibt an, dass das System die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="1d544-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d544-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1d544-114">Message</span></span>  
 <span data-ttu-id="1d544-115">Das System hat die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht.</span><span class="sxs-lookup"><span data-stu-id="1d544-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="1d544-116">Die Grenze für diese Drosselung war auf %1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1d544-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="1d544-117">Der Drosselungswert kann geändert werden, indem das Attribut "maxConcurrentInstances" im serviceThrottle-Element oder die "MaxConcurrentInstances"-Eigenschaft im Verhalten "ServiceThrottlingBehavior" geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1d544-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d544-118">Details</span><span class="sxs-lookup"><span data-stu-id="1d544-118">Details</span></span>  
  
|<span data-ttu-id="1d544-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1d544-119">Data Item Name</span></span>|<span data-ttu-id="1d544-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1d544-120">Data Item Type</span></span>|<span data-ttu-id="1d544-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d544-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d544-122">Name</span><span class="sxs-lookup"><span data-stu-id="1d544-122">Name</span></span>|<span data-ttu-id="1d544-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d544-123">xs:string</span></span>|<span data-ttu-id="1d544-124">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="1d544-124">The name of the item.</span></span>|  
|<span data-ttu-id="1d544-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1d544-125">AppDomain</span></span>|<span data-ttu-id="1d544-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d544-126">xs:string</span></span>|<span data-ttu-id="1d544-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d544-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
