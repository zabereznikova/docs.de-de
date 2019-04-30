---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924864"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="9809a-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="9809a-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9809a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9809a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9809a-104">ID</span><span class="sxs-lookup"><span data-stu-id="9809a-104">ID</span></span>|<span data-ttu-id="9809a-105">1032</span><span class="sxs-lookup"><span data-stu-id="9809a-105">1032</span></span>|  
|<span data-ttu-id="9809a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9809a-106">Keywords</span></span>|<span data-ttu-id="9809a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9809a-107">WFRuntime</span></span>|  
|<span data-ttu-id="9809a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9809a-108">Level</span></span>|<span data-ttu-id="9809a-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="9809a-109">Verbose</span></span>|  
|<span data-ttu-id="9809a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9809a-110">Channel</span></span>|<span data-ttu-id="9809a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9809a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9809a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9809a-112">Description</span></span>  
 <span data-ttu-id="9809a-113">Gibt an, dass ein RuntimeWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="9809a-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9809a-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9809a-114">Message</span></span>  
 <span data-ttu-id="9809a-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein Laufzeitarbeitselement geplant.</span><span class="sxs-lookup"><span data-stu-id="9809a-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9809a-116">Details</span><span class="sxs-lookup"><span data-stu-id="9809a-116">Details</span></span>  
  
|<span data-ttu-id="9809a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9809a-117">Data Item Name</span></span>|<span data-ttu-id="9809a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9809a-118">Data Item Type</span></span>|<span data-ttu-id="9809a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9809a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9809a-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="9809a-120">Activity</span></span>|<span data-ttu-id="9809a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9809a-121">xs:string</span></span>|<span data-ttu-id="9809a-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9809a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9809a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9809a-123">DisplayName</span></span>|<span data-ttu-id="9809a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9809a-124">xs:string</span></span>|<span data-ttu-id="9809a-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9809a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9809a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9809a-126">InstanceId</span></span>|<span data-ttu-id="9809a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9809a-127">xs:string</span></span>|<span data-ttu-id="9809a-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9809a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9809a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9809a-129">AppDomain</span></span>|<span data-ttu-id="9809a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9809a-130">xs:string</span></span>|<span data-ttu-id="9809a-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9809a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
