---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a3b03e8ac24bc1652b88b71e8c25862a07c194f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="7efe1-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="7efe1-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7efe1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7efe1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7efe1-104">ID</span><span class="sxs-lookup"><span data-stu-id="7efe1-104">ID</span></span>|<span data-ttu-id="7efe1-105">1012</span><span class="sxs-lookup"><span data-stu-id="7efe1-105">1012</span></span>|  
|<span data-ttu-id="7efe1-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7efe1-106">Keywords</span></span>|<span data-ttu-id="7efe1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7efe1-107">WFRuntime</span></span>|  
|<span data-ttu-id="7efe1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7efe1-108">Level</span></span>|<span data-ttu-id="7efe1-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="7efe1-109">Verbose</span></span>|  
|<span data-ttu-id="7efe1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7efe1-110">Channel</span></span>|<span data-ttu-id="7efe1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7efe1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7efe1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7efe1-112">Description</span></span>  
 <span data-ttu-id="7efe1-113">Gibt an, dass ein ExecuteActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="7efe1-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7efe1-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="7efe1-114">Message</span></span>  
 <span data-ttu-id="7efe1-115">Die Ausführung eines ExecuteActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="7efe1-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7efe1-116">Details</span><span class="sxs-lookup"><span data-stu-id="7efe1-116">Details</span></span>  
  
|<span data-ttu-id="7efe1-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7efe1-117">Data Item Name</span></span>|<span data-ttu-id="7efe1-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7efe1-118">Data Item Type</span></span>|<span data-ttu-id="7efe1-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7efe1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7efe1-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="7efe1-120">Activity</span></span>|<span data-ttu-id="7efe1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7efe1-121">xs:string</span></span>|<span data-ttu-id="7efe1-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7efe1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="7efe1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7efe1-123">DisplayName</span></span>|<span data-ttu-id="7efe1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7efe1-124">xs:string</span></span>|<span data-ttu-id="7efe1-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7efe1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="7efe1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7efe1-126">InstanceId</span></span>|<span data-ttu-id="7efe1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7efe1-127">xs:string</span></span>|<span data-ttu-id="7efe1-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7efe1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7efe1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7efe1-129">AppDomain</span></span>|<span data-ttu-id="7efe1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7efe1-130">xs:string</span></span>|<span data-ttu-id="7efe1-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7efe1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
