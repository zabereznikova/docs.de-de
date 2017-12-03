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
ms.openlocfilehash: 6a06cec1ab251b8f7e82aef71589bd56e5f55f2e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="fb353-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="fb353-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fb353-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fb353-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb353-104">ID</span><span class="sxs-lookup"><span data-stu-id="fb353-104">ID</span></span>|<span data-ttu-id="fb353-105">1012</span><span class="sxs-lookup"><span data-stu-id="fb353-105">1012</span></span>|  
|<span data-ttu-id="fb353-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fb353-106">Keywords</span></span>|<span data-ttu-id="fb353-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fb353-107">WFRuntime</span></span>|  
|<span data-ttu-id="fb353-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fb353-108">Level</span></span>|<span data-ttu-id="fb353-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="fb353-109">Verbose</span></span>|  
|<span data-ttu-id="fb353-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fb353-110">Channel</span></span>|<span data-ttu-id="fb353-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fb353-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fb353-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb353-112">Description</span></span>  
 <span data-ttu-id="fb353-113">Gibt an, dass ein ExecuteActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="fb353-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fb353-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="fb353-114">Message</span></span>  
 <span data-ttu-id="fb353-115">Die Ausführung eines ExecuteActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="fb353-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fb353-116">Details</span><span class="sxs-lookup"><span data-stu-id="fb353-116">Details</span></span>  
  
|<span data-ttu-id="fb353-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fb353-117">Data Item Name</span></span>|<span data-ttu-id="fb353-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fb353-118">Data Item Type</span></span>|<span data-ttu-id="fb353-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb353-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fb353-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="fb353-120">Activity</span></span>|<span data-ttu-id="fb353-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb353-121">xs:string</span></span>|<span data-ttu-id="fb353-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fb353-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fb353-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fb353-123">DisplayName</span></span>|<span data-ttu-id="fb353-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb353-124">xs:string</span></span>|<span data-ttu-id="fb353-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fb353-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fb353-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fb353-126">InstanceId</span></span>|<span data-ttu-id="fb353-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb353-127">xs:string</span></span>|<span data-ttu-id="fb353-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fb353-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fb353-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fb353-129">AppDomain</span></span>|<span data-ttu-id="fb353-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb353-130">xs:string</span></span>|<span data-ttu-id="fb353-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fb353-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
