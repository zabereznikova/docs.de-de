---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 46a3dc8d313ec72ac90abc2e2e333b274dad2e4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294299"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="bde7e-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="bde7e-102">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="bde7e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bde7e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bde7e-104">id</span><span class="sxs-lookup"><span data-stu-id="bde7e-104">ID</span></span>|<span data-ttu-id="bde7e-105">1033</span><span class="sxs-lookup"><span data-stu-id="bde7e-105">1033</span></span>|  
|<span data-ttu-id="bde7e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="bde7e-106">Keywords</span></span>|<span data-ttu-id="bde7e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bde7e-107">WFRuntime</span></span>|  
|<span data-ttu-id="bde7e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bde7e-108">Level</span></span>|<span data-ttu-id="bde7e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="bde7e-109">Verbose</span></span>|  
|<span data-ttu-id="bde7e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bde7e-110">Channel</span></span>|<span data-ttu-id="bde7e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bde7e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bde7e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bde7e-112">Description</span></span>  

 <span data-ttu-id="bde7e-113">Gibt an, dass ein RuntimeWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="bde7e-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bde7e-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="bde7e-114">Message</span></span>  

 <span data-ttu-id="bde7e-115">Die Ausführung eines Laufzeitarbeitselements für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="bde7e-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bde7e-116">Details</span><span class="sxs-lookup"><span data-stu-id="bde7e-116">Details</span></span>  
  
|<span data-ttu-id="bde7e-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bde7e-117">Data Item Name</span></span>|<span data-ttu-id="bde7e-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bde7e-118">Data Item Type</span></span>|<span data-ttu-id="bde7e-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bde7e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bde7e-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="bde7e-120">Activity</span></span>|<span data-ttu-id="bde7e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bde7e-121">xs:string</span></span>|<span data-ttu-id="bde7e-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bde7e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bde7e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bde7e-123">DisplayName</span></span>|<span data-ttu-id="bde7e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bde7e-124">xs:string</span></span>|<span data-ttu-id="bde7e-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bde7e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bde7e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bde7e-126">InstanceId</span></span>|<span data-ttu-id="bde7e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bde7e-127">xs:string</span></span>|<span data-ttu-id="bde7e-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bde7e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bde7e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bde7e-129">AppDomain</span></span>|<span data-ttu-id="bde7e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bde7e-130">xs:string</span></span>|<span data-ttu-id="bde7e-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bde7e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
