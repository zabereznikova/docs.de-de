---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924630"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="160c5-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="160c5-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="160c5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="160c5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="160c5-104">ID</span><span class="sxs-lookup"><span data-stu-id="160c5-104">ID</span></span>|<span data-ttu-id="160c5-105">1026</span><span class="sxs-lookup"><span data-stu-id="160c5-105">1026</span></span>|  
|<span data-ttu-id="160c5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="160c5-106">Keywords</span></span>|<span data-ttu-id="160c5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="160c5-107">WFRuntime</span></span>|  
|<span data-ttu-id="160c5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="160c5-108">Level</span></span>|<span data-ttu-id="160c5-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="160c5-109">Verbose</span></span>|  
|<span data-ttu-id="160c5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="160c5-110">Channel</span></span>|<span data-ttu-id="160c5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="160c5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="160c5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="160c5-112">Description</span></span>  
 <span data-ttu-id="160c5-113">Gibt an, dass ein TransactionContextWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="160c5-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="160c5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="160c5-114">Message</span></span>  
 <span data-ttu-id="160c5-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="160c5-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="160c5-116">Details</span><span class="sxs-lookup"><span data-stu-id="160c5-116">Details</span></span>  
  
|<span data-ttu-id="160c5-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="160c5-117">Data Item Name</span></span>|<span data-ttu-id="160c5-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="160c5-118">Data Item Type</span></span>|<span data-ttu-id="160c5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="160c5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="160c5-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="160c5-120">Activity</span></span>|<span data-ttu-id="160c5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="160c5-121">xs:string</span></span>|<span data-ttu-id="160c5-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="160c5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="160c5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="160c5-123">DisplayName</span></span>|<span data-ttu-id="160c5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="160c5-124">xs:string</span></span>|<span data-ttu-id="160c5-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="160c5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="160c5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="160c5-126">InstanceId</span></span>|<span data-ttu-id="160c5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="160c5-127">xs:string</span></span>|<span data-ttu-id="160c5-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="160c5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="160c5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="160c5-129">AppDomain</span></span>|<span data-ttu-id="160c5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="160c5-130">xs:string</span></span>|<span data-ttu-id="160c5-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="160c5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
