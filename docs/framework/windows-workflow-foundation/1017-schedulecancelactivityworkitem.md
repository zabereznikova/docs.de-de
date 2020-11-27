---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 6aed9773aa45251075520a0f955e9d71234f1357
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275618"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="f148a-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f148a-102">1017 - ScheduleCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f148a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f148a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f148a-104">id</span><span class="sxs-lookup"><span data-stu-id="f148a-104">ID</span></span>|<span data-ttu-id="f148a-105">1017</span><span class="sxs-lookup"><span data-stu-id="f148a-105">1017</span></span>|  
|<span data-ttu-id="f148a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="f148a-106">Keywords</span></span>|<span data-ttu-id="f148a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f148a-107">WFRuntime</span></span>|  
|<span data-ttu-id="f148a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f148a-108">Level</span></span>|<span data-ttu-id="f148a-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="f148a-109">Verbose</span></span>|  
|<span data-ttu-id="f148a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f148a-110">Channel</span></span>|<span data-ttu-id="f148a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f148a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f148a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f148a-112">Description</span></span>  

 <span data-ttu-id="f148a-113">Gibt an, dass ein CancelActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="f148a-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f148a-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="f148a-114">Message</span></span>  

 <span data-ttu-id="f148a-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CancelActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="f148a-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f148a-116">Details</span><span class="sxs-lookup"><span data-stu-id="f148a-116">Details</span></span>  
  
|<span data-ttu-id="f148a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f148a-117">Data Item Name</span></span>|<span data-ttu-id="f148a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f148a-118">Data Item Type</span></span>|<span data-ttu-id="f148a-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f148a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f148a-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="f148a-120">Activity</span></span>|<span data-ttu-id="f148a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f148a-121">xs:string</span></span>|<span data-ttu-id="f148a-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f148a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f148a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f148a-123">DisplayName</span></span>|<span data-ttu-id="f148a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f148a-124">xs:string</span></span>|<span data-ttu-id="f148a-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f148a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f148a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f148a-126">InstanceId</span></span>|<span data-ttu-id="f148a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f148a-127">xs:string</span></span>|<span data-ttu-id="f148a-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f148a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f148a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f148a-129">AppDomain</span></span>|<span data-ttu-id="f148a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f148a-130">xs:string</span></span>|<span data-ttu-id="f148a-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f148a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
