---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924851"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="137a3-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="137a3-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="137a3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="137a3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="137a3-104">ID</span><span class="sxs-lookup"><span data-stu-id="137a3-104">ID</span></span>|<span data-ttu-id="137a3-105">1035</span><span class="sxs-lookup"><span data-stu-id="137a3-105">1035</span></span>|  
|<span data-ttu-id="137a3-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="137a3-106">Keywords</span></span>|<span data-ttu-id="137a3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="137a3-107">WFRuntime</span></span>|  
|<span data-ttu-id="137a3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="137a3-108">Level</span></span>|<span data-ttu-id="137a3-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="137a3-109">Verbose</span></span>|  
|<span data-ttu-id="137a3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="137a3-110">Channel</span></span>|<span data-ttu-id="137a3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="137a3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="137a3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="137a3-112">Description</span></span>  
 <span data-ttu-id="137a3-113">Gibt an, dass eine Aktivität die Laufzeittransaktion festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="137a3-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="137a3-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="137a3-114">Message</span></span>  
 <span data-ttu-id="137a3-115">Die laufzeittransaktion festgelegt wurde, durch die Aktivität '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="137a3-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="137a3-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="137a3-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="137a3-117">Details</span><span class="sxs-lookup"><span data-stu-id="137a3-117">Details</span></span>  
  
|<span data-ttu-id="137a3-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="137a3-118">Data Item Name</span></span>|<span data-ttu-id="137a3-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="137a3-119">Data Item Type</span></span>|<span data-ttu-id="137a3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="137a3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="137a3-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="137a3-121">Activity</span></span>|<span data-ttu-id="137a3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-122">xs:string</span></span>|<span data-ttu-id="137a3-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="137a3-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="137a3-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="137a3-124">DisplayName</span></span>|<span data-ttu-id="137a3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-125">xs:string</span></span>|<span data-ttu-id="137a3-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="137a3-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="137a3-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="137a3-127">InstanceId</span></span>|<span data-ttu-id="137a3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-128">xs:string</span></span>|<span data-ttu-id="137a3-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="137a3-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="137a3-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="137a3-130">IsolatedActivity</span></span>|<span data-ttu-id="137a3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-131">xs:string</span></span>|<span data-ttu-id="137a3-132">Der Typname der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="137a3-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="137a3-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="137a3-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="137a3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-134">xs:string</span></span>|<span data-ttu-id="137a3-135">Der Anzeigename der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="137a3-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="137a3-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="137a3-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="137a3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-137">xs:string</span></span>|<span data-ttu-id="137a3-138">Die Instanz-ID der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="137a3-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="137a3-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="137a3-139">AppDomain</span></span>|<span data-ttu-id="137a3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="137a3-140">xs:string</span></span>|<span data-ttu-id="137a3-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="137a3-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
