---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3fcd93dbc30b20f7822a54babde8277e32d8335
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="53058-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="53058-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="53058-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="53058-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53058-104">ID</span><span class="sxs-lookup"><span data-stu-id="53058-104">ID</span></span>|<span data-ttu-id="53058-105">1035</span><span class="sxs-lookup"><span data-stu-id="53058-105">1035</span></span>|  
|<span data-ttu-id="53058-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="53058-106">Keywords</span></span>|<span data-ttu-id="53058-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="53058-107">WFRuntime</span></span>|  
|<span data-ttu-id="53058-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="53058-108">Level</span></span>|<span data-ttu-id="53058-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="53058-109">Verbose</span></span>|  
|<span data-ttu-id="53058-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="53058-110">Channel</span></span>|<span data-ttu-id="53058-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="53058-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="53058-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53058-112">Description</span></span>  
 <span data-ttu-id="53058-113">Gibt an, dass eine Aktivität die Laufzeittransaktion festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="53058-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="53058-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="53058-114">Message</span></span>  
 <span data-ttu-id="53058-115">Die laufzeittransaktion festgelegt wurde, von der Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="53058-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="53058-116">Ausführung isoliert Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="53058-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="53058-117">Details</span><span class="sxs-lookup"><span data-stu-id="53058-117">Details</span></span>  
  
|<span data-ttu-id="53058-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="53058-118">Data Item Name</span></span>|<span data-ttu-id="53058-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="53058-119">Data Item Type</span></span>|<span data-ttu-id="53058-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53058-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="53058-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="53058-121">Activity</span></span>|<span data-ttu-id="53058-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-122">xs:string</span></span>|<span data-ttu-id="53058-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="53058-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="53058-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="53058-124">DisplayName</span></span>|<span data-ttu-id="53058-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-125">xs:string</span></span>|<span data-ttu-id="53058-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="53058-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="53058-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="53058-127">InstanceId</span></span>|<span data-ttu-id="53058-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-128">xs:string</span></span>|<span data-ttu-id="53058-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="53058-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="53058-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="53058-130">IsolatedActivity</span></span>|<span data-ttu-id="53058-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-131">xs:string</span></span>|<span data-ttu-id="53058-132">Der Typname der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="53058-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="53058-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="53058-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="53058-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-134">xs:string</span></span>|<span data-ttu-id="53058-135">Der Anzeigename der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="53058-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="53058-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="53058-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="53058-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-137">xs:string</span></span>|<span data-ttu-id="53058-138">Die Instanz-ID der Aktivität, für die die Transaktion isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="53058-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="53058-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="53058-139">AppDomain</span></span>|<span data-ttu-id="53058-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="53058-140">xs:string</span></span>|<span data-ttu-id="53058-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="53058-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
