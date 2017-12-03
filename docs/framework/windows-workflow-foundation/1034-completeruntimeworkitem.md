---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48161ca9c9268fb52c8b8ab9f3fb6d6ce894efa4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="a67ea-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="a67ea-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a67ea-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a67ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a67ea-104">ID</span><span class="sxs-lookup"><span data-stu-id="a67ea-104">ID</span></span>|<span data-ttu-id="a67ea-105">1034</span><span class="sxs-lookup"><span data-stu-id="a67ea-105">1034</span></span>|  
|<span data-ttu-id="a67ea-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a67ea-106">Keywords</span></span>|<span data-ttu-id="a67ea-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a67ea-107">WFRuntime</span></span>|  
|<span data-ttu-id="a67ea-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a67ea-108">Level</span></span>|<span data-ttu-id="a67ea-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="a67ea-109">Verbose</span></span>|  
|<span data-ttu-id="a67ea-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a67ea-110">Channel</span></span>|<span data-ttu-id="a67ea-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a67ea-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a67ea-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a67ea-112">Description</span></span>  
 <span data-ttu-id="a67ea-113">Gibt an, dass ein RuntimeWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a67ea-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a67ea-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a67ea-114">Message</span></span>  
 <span data-ttu-id="a67ea-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine Laufzeitarbeitsaufgabe abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a67ea-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a67ea-116">Details</span><span class="sxs-lookup"><span data-stu-id="a67ea-116">Details</span></span>  
  
|<span data-ttu-id="a67ea-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a67ea-117">Data Item Name</span></span>|<span data-ttu-id="a67ea-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a67ea-118">Data Item Type</span></span>|<span data-ttu-id="a67ea-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a67ea-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a67ea-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="a67ea-120">Activity</span></span>|<span data-ttu-id="a67ea-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a67ea-121">xs:string</span></span>|<span data-ttu-id="a67ea-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a67ea-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a67ea-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a67ea-123">DisplayName</span></span>|<span data-ttu-id="a67ea-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a67ea-124">xs:string</span></span>|<span data-ttu-id="a67ea-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a67ea-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a67ea-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a67ea-126">InstanceId</span></span>|<span data-ttu-id="a67ea-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a67ea-127">xs:string</span></span>|<span data-ttu-id="a67ea-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a67ea-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a67ea-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a67ea-129">AppDomain</span></span>|<span data-ttu-id="a67ea-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a67ea-130">xs:string</span></span>|<span data-ttu-id="a67ea-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a67ea-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
