---
title: 1018 - StartCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d64d18474ff867ee5679e07c18a288f07185f60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="3a43e-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3a43e-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3a43e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3a43e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a43e-104">ID</span><span class="sxs-lookup"><span data-stu-id="3a43e-104">ID</span></span>|<span data-ttu-id="3a43e-105">1018</span><span class="sxs-lookup"><span data-stu-id="3a43e-105">1018</span></span>|  
|<span data-ttu-id="3a43e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3a43e-106">Keywords</span></span>|<span data-ttu-id="3a43e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3a43e-107">WFRuntime</span></span>|  
|<span data-ttu-id="3a43e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3a43e-108">Level</span></span>|<span data-ttu-id="3a43e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="3a43e-109">Verbose</span></span>|  
|<span data-ttu-id="3a43e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3a43e-110">Channel</span></span>|<span data-ttu-id="3a43e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3a43e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3a43e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a43e-112">Description</span></span>  
 <span data-ttu-id="3a43e-113">Gibt an, dass ein CancelActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="3a43e-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3a43e-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3a43e-114">Message</span></span>  
 <span data-ttu-id="3a43e-115">Die Ausführung einer CancelActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="3a43e-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3a43e-116">Details</span><span class="sxs-lookup"><span data-stu-id="3a43e-116">Details</span></span>  
  
|<span data-ttu-id="3a43e-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3a43e-117">Data Item Name</span></span>|<span data-ttu-id="3a43e-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3a43e-118">Data Item Type</span></span>|<span data-ttu-id="3a43e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a43e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3a43e-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="3a43e-120">Activity</span></span>|<span data-ttu-id="3a43e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a43e-121">xs:string</span></span>|<span data-ttu-id="3a43e-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3a43e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3a43e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3a43e-123">DisplayName</span></span>|<span data-ttu-id="3a43e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a43e-124">xs:string</span></span>|<span data-ttu-id="3a43e-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3a43e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3a43e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3a43e-126">InstanceId</span></span>|<span data-ttu-id="3a43e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a43e-127">xs:string</span></span>|<span data-ttu-id="3a43e-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3a43e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3a43e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3a43e-129">AppDomain</span></span>|<span data-ttu-id="3a43e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a43e-130">xs:string</span></span>|<span data-ttu-id="3a43e-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3a43e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
