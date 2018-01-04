---
title: 1150 - CompensationState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28621fceab89a2302decafb1c97cdebf406888df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1150---compensationstate"></a><span data-ttu-id="6f4d3-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="6f4d3-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="6f4d3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6f4d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f4d3-104">ID</span><span class="sxs-lookup"><span data-stu-id="6f4d3-104">ID</span></span>|<span data-ttu-id="6f4d3-105">1150</span><span class="sxs-lookup"><span data-stu-id="6f4d3-105">1150</span></span>|  
|<span data-ttu-id="6f4d3-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6f4d3-106">Keywords</span></span>|<span data-ttu-id="6f4d3-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="6f4d3-107">WFActivities</span></span>|  
|<span data-ttu-id="6f4d3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6f4d3-108">Level</span></span>|<span data-ttu-id="6f4d3-109">Information</span><span class="sxs-lookup"><span data-stu-id="6f4d3-109">Information</span></span>|  
|<span data-ttu-id="6f4d3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6f4d3-110">Channel</span></span>|<span data-ttu-id="6f4d3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6f4d3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6f4d3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f4d3-112">Description</span></span>  
 <span data-ttu-id="6f4d3-113">Gibt eine Statusänderung in einer CompensableActivity an.</span><span class="sxs-lookup"><span data-stu-id="6f4d3-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6f4d3-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="6f4d3-114">Message</span></span>  
 <span data-ttu-id="6f4d3-115">CompensableActivity '%1' hat den Status '%2'.</span><span class="sxs-lookup"><span data-stu-id="6f4d3-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6f4d3-116">Details</span><span class="sxs-lookup"><span data-stu-id="6f4d3-116">Details</span></span>  
  
|<span data-ttu-id="6f4d3-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6f4d3-117">Data Item Name</span></span>|<span data-ttu-id="6f4d3-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6f4d3-118">Data Item Type</span></span>|<span data-ttu-id="6f4d3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f4d3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6f4d3-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6f4d3-120">DisplayName</span></span>|<span data-ttu-id="6f4d3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f4d3-121">xs:string</span></span>|<span data-ttu-id="6f4d3-122">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6f4d3-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="6f4d3-123">Zustand</span><span class="sxs-lookup"><span data-stu-id="6f4d3-123">State</span></span>|<span data-ttu-id="6f4d3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f4d3-124">xs:string</span></span>|<span data-ttu-id="6f4d3-125">Der Kompensationsstatus.</span><span class="sxs-lookup"><span data-stu-id="6f4d3-125">The compensation state.</span></span>|  
|<span data-ttu-id="6f4d3-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6f4d3-126">AppDomain</span></span>|<span data-ttu-id="6f4d3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f4d3-127">xs:string</span></span>|<span data-ttu-id="6f4d3-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6f4d3-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
