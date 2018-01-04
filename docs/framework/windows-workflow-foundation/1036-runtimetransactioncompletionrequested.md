---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91fcac0bdfe885051941d100f1a2c131c547f19e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="aa79b-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="aa79b-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="aa79b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa79b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa79b-104">ID</span><span class="sxs-lookup"><span data-stu-id="aa79b-104">ID</span></span>|<span data-ttu-id="aa79b-105">1036</span><span class="sxs-lookup"><span data-stu-id="aa79b-105">1036</span></span>|  
|<span data-ttu-id="aa79b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="aa79b-106">Keywords</span></span>|<span data-ttu-id="aa79b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aa79b-107">WFRuntime</span></span>|  
|<span data-ttu-id="aa79b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="aa79b-108">Level</span></span>|<span data-ttu-id="aa79b-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="aa79b-109">Verbose</span></span>|  
|<span data-ttu-id="aa79b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="aa79b-110">Channel</span></span>|<span data-ttu-id="aa79b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aa79b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa79b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa79b-112">Description</span></span>  
 <span data-ttu-id="aa79b-113">Gibt an, dass eine Aktivität den Abschluss der Ablauftransaktion geplant hat.</span><span class="sxs-lookup"><span data-stu-id="aa79b-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa79b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="aa79b-114">Message</span></span>  
 <span data-ttu-id="aa79b-115">Die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat den Abschluss der Laufzeittransaktion geplant.</span><span class="sxs-lookup"><span data-stu-id="aa79b-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa79b-116">Details</span><span class="sxs-lookup"><span data-stu-id="aa79b-116">Details</span></span>  
  
|<span data-ttu-id="aa79b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="aa79b-117">Data Item Name</span></span>|<span data-ttu-id="aa79b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="aa79b-118">Data Item Type</span></span>|<span data-ttu-id="aa79b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa79b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa79b-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="aa79b-120">Activity</span></span>|<span data-ttu-id="aa79b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa79b-121">xs:string</span></span>|<span data-ttu-id="aa79b-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa79b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="aa79b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="aa79b-123">DisplayName</span></span>|<span data-ttu-id="aa79b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa79b-124">xs:string</span></span>|<span data-ttu-id="aa79b-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa79b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="aa79b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="aa79b-126">InstanceId</span></span>|<span data-ttu-id="aa79b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa79b-127">xs:string</span></span>|<span data-ttu-id="aa79b-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa79b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="aa79b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa79b-129">AppDomain</span></span>|<span data-ttu-id="aa79b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa79b-130">xs:string</span></span>|<span data-ttu-id="aa79b-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aa79b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
