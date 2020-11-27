---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: c1558e19b0de2dc5d22d4356b0f80c35e5b4fbc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275504"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="6ca65-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="6ca65-102">1018 - StartCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="6ca65-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6ca65-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6ca65-104">id</span><span class="sxs-lookup"><span data-stu-id="6ca65-104">ID</span></span>|<span data-ttu-id="6ca65-105">1018</span><span class="sxs-lookup"><span data-stu-id="6ca65-105">1018</span></span>|  
|<span data-ttu-id="6ca65-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="6ca65-106">Keywords</span></span>|<span data-ttu-id="6ca65-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6ca65-107">WFRuntime</span></span>|  
|<span data-ttu-id="6ca65-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6ca65-108">Level</span></span>|<span data-ttu-id="6ca65-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="6ca65-109">Verbose</span></span>|  
|<span data-ttu-id="6ca65-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6ca65-110">Channel</span></span>|<span data-ttu-id="6ca65-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6ca65-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6ca65-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6ca65-112">Description</span></span>  

 <span data-ttu-id="6ca65-113">Gibt an, dass ein CancelActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="6ca65-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6ca65-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="6ca65-114">Message</span></span>  

 <span data-ttu-id="6ca65-115">Die Ausführung einer CancelActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="6ca65-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6ca65-116">Details</span><span class="sxs-lookup"><span data-stu-id="6ca65-116">Details</span></span>  
  
|<span data-ttu-id="6ca65-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6ca65-117">Data Item Name</span></span>|<span data-ttu-id="6ca65-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6ca65-118">Data Item Type</span></span>|<span data-ttu-id="6ca65-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6ca65-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6ca65-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="6ca65-120">Activity</span></span>|<span data-ttu-id="6ca65-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6ca65-121">xs:string</span></span>|<span data-ttu-id="6ca65-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6ca65-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="6ca65-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6ca65-123">DisplayName</span></span>|<span data-ttu-id="6ca65-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6ca65-124">xs:string</span></span>|<span data-ttu-id="6ca65-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6ca65-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="6ca65-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="6ca65-126">InstanceId</span></span>|<span data-ttu-id="6ca65-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6ca65-127">xs:string</span></span>|<span data-ttu-id="6ca65-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6ca65-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="6ca65-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6ca65-129">AppDomain</span></span>|<span data-ttu-id="6ca65-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6ca65-130">xs:string</span></span>|<span data-ttu-id="6ca65-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6ca65-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
