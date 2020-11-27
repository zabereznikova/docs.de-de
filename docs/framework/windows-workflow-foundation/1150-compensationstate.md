---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 2adb317521b8659c2419e4c04aabf4cf4499b36f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285108"
---
# <a name="1150---compensationstate"></a><span data-ttu-id="b08ab-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="b08ab-102">1150 - CompensationState</span></span>

## <a name="properties"></a><span data-ttu-id="b08ab-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b08ab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b08ab-104">id</span><span class="sxs-lookup"><span data-stu-id="b08ab-104">ID</span></span>|<span data-ttu-id="b08ab-105">1150</span><span class="sxs-lookup"><span data-stu-id="b08ab-105">1150</span></span>|  
|<span data-ttu-id="b08ab-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="b08ab-106">Keywords</span></span>|<span data-ttu-id="b08ab-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="b08ab-107">WFActivities</span></span>|  
|<span data-ttu-id="b08ab-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b08ab-108">Level</span></span>|<span data-ttu-id="b08ab-109">Information</span><span class="sxs-lookup"><span data-stu-id="b08ab-109">Information</span></span>|  
|<span data-ttu-id="b08ab-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b08ab-110">Channel</span></span>|<span data-ttu-id="b08ab-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b08ab-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b08ab-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b08ab-112">Description</span></span>  

 <span data-ttu-id="b08ab-113">Gibt eine Statusänderung in einer CompensableActivity an.</span><span class="sxs-lookup"><span data-stu-id="b08ab-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b08ab-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="b08ab-114">Message</span></span>  

 <span data-ttu-id="b08ab-115">CompensableActivity '%1' hat den Status '%2'.</span><span class="sxs-lookup"><span data-stu-id="b08ab-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b08ab-116">Details</span><span class="sxs-lookup"><span data-stu-id="b08ab-116">Details</span></span>  
  
|<span data-ttu-id="b08ab-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b08ab-117">Data Item Name</span></span>|<span data-ttu-id="b08ab-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b08ab-118">Data Item Type</span></span>|<span data-ttu-id="b08ab-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b08ab-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b08ab-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b08ab-120">DisplayName</span></span>|<span data-ttu-id="b08ab-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b08ab-121">xs:string</span></span>|<span data-ttu-id="b08ab-122">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b08ab-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="b08ab-123">State</span><span class="sxs-lookup"><span data-stu-id="b08ab-123">State</span></span>|<span data-ttu-id="b08ab-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b08ab-124">xs:string</span></span>|<span data-ttu-id="b08ab-125">Der Kompensationsstatus.</span><span class="sxs-lookup"><span data-stu-id="b08ab-125">The compensation state.</span></span>|  
|<span data-ttu-id="b08ab-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b08ab-126">AppDomain</span></span>|<span data-ttu-id="b08ab-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b08ab-127">xs:string</span></span>|<span data-ttu-id="b08ab-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b08ab-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
