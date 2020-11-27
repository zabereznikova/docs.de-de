---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 7ba2ada1fbd5217592b4e4e3cffd813ffbe978ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275244"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="40ccc-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="40ccc-102">1026 - ScheduleTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="40ccc-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="40ccc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40ccc-104">id</span><span class="sxs-lookup"><span data-stu-id="40ccc-104">ID</span></span>|<span data-ttu-id="40ccc-105">1026</span><span class="sxs-lookup"><span data-stu-id="40ccc-105">1026</span></span>|  
|<span data-ttu-id="40ccc-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="40ccc-106">Keywords</span></span>|<span data-ttu-id="40ccc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="40ccc-107">WFRuntime</span></span>|  
|<span data-ttu-id="40ccc-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="40ccc-108">Level</span></span>|<span data-ttu-id="40ccc-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="40ccc-109">Verbose</span></span>|  
|<span data-ttu-id="40ccc-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="40ccc-110">Channel</span></span>|<span data-ttu-id="40ccc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="40ccc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="40ccc-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40ccc-112">Description</span></span>  

 <span data-ttu-id="40ccc-113">Gibt an, dass ein TransactionContextWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="40ccc-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="40ccc-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="40ccc-114">Message</span></span>  

 <span data-ttu-id="40ccc-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="40ccc-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="40ccc-116">Details</span><span class="sxs-lookup"><span data-stu-id="40ccc-116">Details</span></span>  
  
|<span data-ttu-id="40ccc-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="40ccc-117">Data Item Name</span></span>|<span data-ttu-id="40ccc-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="40ccc-118">Data Item Type</span></span>|<span data-ttu-id="40ccc-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40ccc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="40ccc-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="40ccc-120">Activity</span></span>|<span data-ttu-id="40ccc-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="40ccc-121">xs:string</span></span>|<span data-ttu-id="40ccc-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="40ccc-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="40ccc-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="40ccc-123">DisplayName</span></span>|<span data-ttu-id="40ccc-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="40ccc-124">xs:string</span></span>|<span data-ttu-id="40ccc-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="40ccc-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="40ccc-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="40ccc-126">InstanceId</span></span>|<span data-ttu-id="40ccc-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="40ccc-127">xs:string</span></span>|<span data-ttu-id="40ccc-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="40ccc-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="40ccc-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="40ccc-129">AppDomain</span></span>|<span data-ttu-id="40ccc-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="40ccc-130">xs:string</span></span>|<span data-ttu-id="40ccc-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="40ccc-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
