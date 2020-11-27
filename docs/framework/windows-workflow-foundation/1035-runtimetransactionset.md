---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294273"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="7a66e-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="7a66e-102">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="7a66e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7a66e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a66e-104">id</span><span class="sxs-lookup"><span data-stu-id="7a66e-104">ID</span></span>|<span data-ttu-id="7a66e-105">1035</span><span class="sxs-lookup"><span data-stu-id="7a66e-105">1035</span></span>|  
|<span data-ttu-id="7a66e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="7a66e-106">Keywords</span></span>|<span data-ttu-id="7a66e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7a66e-107">WFRuntime</span></span>|  
|<span data-ttu-id="7a66e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7a66e-108">Level</span></span>|<span data-ttu-id="7a66e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="7a66e-109">Verbose</span></span>|  
|<span data-ttu-id="7a66e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7a66e-110">Channel</span></span>|<span data-ttu-id="7a66e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7a66e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7a66e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a66e-112">Description</span></span>  

 <span data-ttu-id="7a66e-113">Gibt an, dass eine Aktivität die Laufzeittransaktion festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="7a66e-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7a66e-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="7a66e-114">Message</span></span>  

 <span data-ttu-id="7a66e-115">Die Lauf Zeit Transaktion wurde von Aktivität ' %1 ', Display Name: ' %2 ', InstanceId: ' %3 ' festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7a66e-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="7a66e-116">Die Ausführung ist auf Aktivität ' %4 ', Display Name: ' %5 ', InstanceId: ' %6 ' isoliert.</span><span class="sxs-lookup"><span data-stu-id="7a66e-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7a66e-117">Details</span><span class="sxs-lookup"><span data-stu-id="7a66e-117">Details</span></span>  
  
|<span data-ttu-id="7a66e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7a66e-118">Data Item Name</span></span>|<span data-ttu-id="7a66e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7a66e-119">Data Item Type</span></span>|<span data-ttu-id="7a66e-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a66e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7a66e-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="7a66e-121">Activity</span></span>|<span data-ttu-id="7a66e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-122">xs:string</span></span>|<span data-ttu-id="7a66e-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7a66e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="7a66e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7a66e-124">DisplayName</span></span>|<span data-ttu-id="7a66e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-125">xs:string</span></span>|<span data-ttu-id="7a66e-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7a66e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="7a66e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7a66e-127">InstanceId</span></span>|<span data-ttu-id="7a66e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-128">xs:string</span></span>|<span data-ttu-id="7a66e-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7a66e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7a66e-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="7a66e-130">IsolatedActivity</span></span>|<span data-ttu-id="7a66e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-131">xs:string</span></span>|<span data-ttu-id="7a66e-132">Der Typname der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="7a66e-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="7a66e-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7a66e-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="7a66e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-134">xs:string</span></span>|<span data-ttu-id="7a66e-135">Der Anzeigename der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="7a66e-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="7a66e-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7a66e-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="7a66e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-137">xs:string</span></span>|<span data-ttu-id="7a66e-138">Die Instanz-ID der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="7a66e-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="7a66e-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7a66e-139">AppDomain</span></span>|<span data-ttu-id="7a66e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="7a66e-140">xs:string</span></span>|<span data-ttu-id="7a66e-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7a66e-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
