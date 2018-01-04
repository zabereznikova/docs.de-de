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
ms.workload: dotnet
ms.openlocfilehash: 378f756003e45905e3697e2e9470aa1e582a2ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="fd417-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="fd417-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fd417-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fd417-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd417-104">ID</span><span class="sxs-lookup"><span data-stu-id="fd417-104">ID</span></span>|<span data-ttu-id="fd417-105">1019</span><span class="sxs-lookup"><span data-stu-id="fd417-105">1019</span></span>|  
|<span data-ttu-id="fd417-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fd417-106">Keywords</span></span>|<span data-ttu-id="fd417-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fd417-107">WFRuntime</span></span>|  
|<span data-ttu-id="fd417-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fd417-108">Level</span></span>|<span data-ttu-id="fd417-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="fd417-109">Verbose</span></span>|  
|<span data-ttu-id="fd417-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fd417-110">Channel</span></span>|<span data-ttu-id="fd417-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fd417-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd417-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd417-112">Description</span></span>  
 <span data-ttu-id="fd417-113">Gibt an, dass ein CancelActivityWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="fd417-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd417-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="fd417-114">Message</span></span>  
 <span data-ttu-id="fd417-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CancelActivityWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fd417-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd417-116">Details</span><span class="sxs-lookup"><span data-stu-id="fd417-116">Details</span></span>  
  
|<span data-ttu-id="fd417-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fd417-117">Data Item Name</span></span>|<span data-ttu-id="fd417-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fd417-118">Data Item Type</span></span>|<span data-ttu-id="fd417-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd417-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd417-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="fd417-120">Activity</span></span>|<span data-ttu-id="fd417-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd417-121">xs:string</span></span>|<span data-ttu-id="fd417-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fd417-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fd417-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fd417-123">DisplayName</span></span>|<span data-ttu-id="fd417-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd417-124">xs:string</span></span>|<span data-ttu-id="fd417-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fd417-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fd417-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fd417-126">InstanceId</span></span>|<span data-ttu-id="fd417-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd417-127">xs:string</span></span>|<span data-ttu-id="fd417-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fd417-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fd417-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd417-129">AppDomain</span></span>|<span data-ttu-id="fd417-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd417-130">xs:string</span></span>|<span data-ttu-id="fd417-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fd417-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
