---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510033"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="2d9ce-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="2d9ce-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="2d9ce-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d9ce-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d9ce-104">ID</span><span class="sxs-lookup"><span data-stu-id="2d9ce-104">ID</span></span>|<span data-ttu-id="2d9ce-105">1035</span><span class="sxs-lookup"><span data-stu-id="2d9ce-105">1035</span></span>|  
|<span data-ttu-id="2d9ce-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2d9ce-106">Keywords</span></span>|<span data-ttu-id="2d9ce-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2d9ce-107">WFRuntime</span></span>|  
|<span data-ttu-id="2d9ce-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2d9ce-108">Level</span></span>|<span data-ttu-id="2d9ce-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="2d9ce-109">Verbose</span></span>|  
|<span data-ttu-id="2d9ce-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2d9ce-110">Channel</span></span>|<span data-ttu-id="2d9ce-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2d9ce-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2d9ce-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d9ce-112">Description</span></span>  
 <span data-ttu-id="2d9ce-113">Gibt an, dass eine Aktivität die Laufzeittransaktion festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2d9ce-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="2d9ce-114">Message</span></span>  
 <span data-ttu-id="2d9ce-115">Die laufzeittransaktion festgelegt wurde, von der Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="2d9ce-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2d9ce-116">Ausführung isoliert Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2d9ce-117">Details</span><span class="sxs-lookup"><span data-stu-id="2d9ce-117">Details</span></span>  
  
|<span data-ttu-id="2d9ce-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2d9ce-118">Data Item Name</span></span>|<span data-ttu-id="2d9ce-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2d9ce-119">Data Item Type</span></span>|<span data-ttu-id="2d9ce-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d9ce-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2d9ce-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="2d9ce-121">Activity</span></span>|<span data-ttu-id="2d9ce-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-122">xs:string</span></span>|<span data-ttu-id="2d9ce-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2d9ce-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2d9ce-124">DisplayName</span></span>|<span data-ttu-id="2d9ce-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-125">xs:string</span></span>|<span data-ttu-id="2d9ce-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2d9ce-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2d9ce-127">InstanceId</span></span>|<span data-ttu-id="2d9ce-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-128">xs:string</span></span>|<span data-ttu-id="2d9ce-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2d9ce-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="2d9ce-130">IsolatedActivity</span></span>|<span data-ttu-id="2d9ce-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-131">xs:string</span></span>|<span data-ttu-id="2d9ce-132">Der Typname der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2d9ce-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2d9ce-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="2d9ce-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-134">xs:string</span></span>|<span data-ttu-id="2d9ce-135">Der Anzeigename der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2d9ce-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2d9ce-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="2d9ce-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-137">xs:string</span></span>|<span data-ttu-id="2d9ce-138">Die Instanz-ID der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2d9ce-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2d9ce-139">AppDomain</span></span>|<span data-ttu-id="2d9ce-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d9ce-140">xs:string</span></span>|<span data-ttu-id="2d9ce-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2d9ce-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
