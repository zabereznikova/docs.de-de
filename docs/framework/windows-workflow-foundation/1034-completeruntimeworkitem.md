---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: 837adc9e143060284f2373a049bc9ad9c8cee336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294286"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="d5419-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="d5419-102">1034 - CompleteRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="d5419-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d5419-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5419-104">id</span><span class="sxs-lookup"><span data-stu-id="d5419-104">ID</span></span>|<span data-ttu-id="d5419-105">1034</span><span class="sxs-lookup"><span data-stu-id="d5419-105">1034</span></span>|  
|<span data-ttu-id="d5419-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="d5419-106">Keywords</span></span>|<span data-ttu-id="d5419-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d5419-107">WFRuntime</span></span>|  
|<span data-ttu-id="d5419-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d5419-108">Level</span></span>|<span data-ttu-id="d5419-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="d5419-109">Verbose</span></span>|  
|<span data-ttu-id="d5419-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d5419-110">Channel</span></span>|<span data-ttu-id="d5419-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d5419-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d5419-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5419-112">Description</span></span>  

 <span data-ttu-id="d5419-113">Gibt an, dass ein RuntimeWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d5419-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d5419-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="d5419-114">Message</span></span>  

 <span data-ttu-id="d5419-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein Laufzeitarbeitselement abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d5419-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d5419-116">Details</span><span class="sxs-lookup"><span data-stu-id="d5419-116">Details</span></span>  
  
|<span data-ttu-id="d5419-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d5419-117">Data Item Name</span></span>|<span data-ttu-id="d5419-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d5419-118">Data Item Type</span></span>|<span data-ttu-id="d5419-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5419-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d5419-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="d5419-120">Activity</span></span>|<span data-ttu-id="d5419-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5419-121">xs:string</span></span>|<span data-ttu-id="d5419-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d5419-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d5419-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d5419-123">DisplayName</span></span>|<span data-ttu-id="d5419-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5419-124">xs:string</span></span>|<span data-ttu-id="d5419-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d5419-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d5419-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d5419-126">InstanceId</span></span>|<span data-ttu-id="d5419-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5419-127">xs:string</span></span>|<span data-ttu-id="d5419-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d5419-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d5419-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d5419-129">AppDomain</span></span>|<span data-ttu-id="d5419-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5419-130">xs:string</span></span>|<span data-ttu-id="d5419-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d5419-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
