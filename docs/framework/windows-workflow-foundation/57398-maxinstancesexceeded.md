---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512550"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="e77d3-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="e77d3-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="e77d3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e77d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e77d3-104">ID</span><span class="sxs-lookup"><span data-stu-id="e77d3-104">ID</span></span>|<span data-ttu-id="e77d3-105">57398</span><span class="sxs-lookup"><span data-stu-id="e77d3-105">57398</span></span>|  
|<span data-ttu-id="e77d3-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e77d3-106">Keywords</span></span>|<span data-ttu-id="e77d3-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e77d3-107">WFServices</span></span>|  
|<span data-ttu-id="e77d3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e77d3-108">Level</span></span>|<span data-ttu-id="e77d3-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="e77d3-109">Warning</span></span>|  
|<span data-ttu-id="e77d3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e77d3-110">Channel</span></span>|<span data-ttu-id="e77d3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e77d3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e77d3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e77d3-112">Description</span></span>  
 <span data-ttu-id="e77d3-113">Gibt an, dass das System die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="e77d3-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e77d3-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="e77d3-114">Message</span></span>  
 <span data-ttu-id="e77d3-115">Das System hat die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht.</span><span class="sxs-lookup"><span data-stu-id="e77d3-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="e77d3-116">Die Grenze für diese Drosselung war auf %1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e77d3-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="e77d3-117">Der Drosselungswert kann geändert werden, indem das Attribut "maxConcurrentInstances" im serviceThrottle-Element oder die "MaxConcurrentInstances"-Eigenschaft im Verhalten "ServiceThrottlingBehavior" geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e77d3-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e77d3-118">Details</span><span class="sxs-lookup"><span data-stu-id="e77d3-118">Details</span></span>  
  
|<span data-ttu-id="e77d3-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e77d3-119">Data Item Name</span></span>|<span data-ttu-id="e77d3-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e77d3-120">Data Item Type</span></span>|<span data-ttu-id="e77d3-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e77d3-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e77d3-122">Name</span><span class="sxs-lookup"><span data-stu-id="e77d3-122">Name</span></span>|<span data-ttu-id="e77d3-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e77d3-123">xs:string</span></span>|<span data-ttu-id="e77d3-124">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="e77d3-124">The name of the item.</span></span>|  
|<span data-ttu-id="e77d3-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e77d3-125">AppDomain</span></span>|<span data-ttu-id="e77d3-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e77d3-126">xs:string</span></span>|<span data-ttu-id="e77d3-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e77d3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
