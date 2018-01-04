---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83c99ddf9c5d4a8fa468303fb198abc349ace6d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="e418f-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="e418f-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e418f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e418f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e418f-104">ID</span><span class="sxs-lookup"><span data-stu-id="e418f-104">ID</span></span>|<span data-ttu-id="e418f-105">1026</span><span class="sxs-lookup"><span data-stu-id="e418f-105">1026</span></span>|  
|<span data-ttu-id="e418f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e418f-106">Keywords</span></span>|<span data-ttu-id="e418f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e418f-107">WFRuntime</span></span>|  
|<span data-ttu-id="e418f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e418f-108">Level</span></span>|<span data-ttu-id="e418f-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="e418f-109">Verbose</span></span>|  
|<span data-ttu-id="e418f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e418f-110">Channel</span></span>|<span data-ttu-id="e418f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e418f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e418f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e418f-112">Description</span></span>  
 <span data-ttu-id="e418f-113">Gibt an, dass ein TransactionContextWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="e418f-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e418f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="e418f-114">Message</span></span>  
 <span data-ttu-id="e418f-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="e418f-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e418f-116">Details</span><span class="sxs-lookup"><span data-stu-id="e418f-116">Details</span></span>  
  
|<span data-ttu-id="e418f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e418f-117">Data Item Name</span></span>|<span data-ttu-id="e418f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e418f-118">Data Item Type</span></span>|<span data-ttu-id="e418f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e418f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e418f-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="e418f-120">Activity</span></span>|<span data-ttu-id="e418f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e418f-121">xs:string</span></span>|<span data-ttu-id="e418f-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e418f-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e418f-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e418f-123">DisplayName</span></span>|<span data-ttu-id="e418f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e418f-124">xs:string</span></span>|<span data-ttu-id="e418f-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e418f-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e418f-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e418f-126">InstanceId</span></span>|<span data-ttu-id="e418f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e418f-127">xs:string</span></span>|<span data-ttu-id="e418f-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e418f-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e418f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e418f-129">AppDomain</span></span>|<span data-ttu-id="e418f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e418f-130">xs:string</span></span>|<span data-ttu-id="e418f-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e418f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
