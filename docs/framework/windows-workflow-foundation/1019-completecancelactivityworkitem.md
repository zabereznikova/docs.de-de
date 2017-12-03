---
title: 1019 - CompleteCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cf96d665bcd5ff703f54d2f15d1912ad0b9573c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="48548-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="48548-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="48548-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48548-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48548-104">ID</span><span class="sxs-lookup"><span data-stu-id="48548-104">ID</span></span>|<span data-ttu-id="48548-105">1019</span><span class="sxs-lookup"><span data-stu-id="48548-105">1019</span></span>|  
|<span data-ttu-id="48548-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48548-106">Keywords</span></span>|<span data-ttu-id="48548-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48548-107">WFRuntime</span></span>|  
|<span data-ttu-id="48548-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="48548-108">Level</span></span>|<span data-ttu-id="48548-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="48548-109">Verbose</span></span>|  
|<span data-ttu-id="48548-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="48548-110">Channel</span></span>|<span data-ttu-id="48548-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48548-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48548-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48548-112">Description</span></span>  
 <span data-ttu-id="48548-113">Gibt an, dass ein CancelActivityWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="48548-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48548-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="48548-114">Message</span></span>  
 <span data-ttu-id="48548-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CancelActivityWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="48548-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48548-116">Details</span><span class="sxs-lookup"><span data-stu-id="48548-116">Details</span></span>  
  
|<span data-ttu-id="48548-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="48548-117">Data Item Name</span></span>|<span data-ttu-id="48548-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="48548-118">Data Item Type</span></span>|<span data-ttu-id="48548-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48548-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48548-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="48548-120">Activity</span></span>|<span data-ttu-id="48548-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="48548-121">xs:string</span></span>|<span data-ttu-id="48548-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48548-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="48548-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="48548-123">DisplayName</span></span>|<span data-ttu-id="48548-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="48548-124">xs:string</span></span>|<span data-ttu-id="48548-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48548-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="48548-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="48548-126">InstanceId</span></span>|<span data-ttu-id="48548-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="48548-127">xs:string</span></span>|<span data-ttu-id="48548-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48548-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="48548-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48548-129">AppDomain</span></span>|<span data-ttu-id="48548-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="48548-130">xs:string</span></span>|<span data-ttu-id="48548-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48548-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
