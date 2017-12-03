---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: db529ed413d70165c7813e23ce8f164262c8e16b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="61469-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="61469-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="61469-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="61469-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61469-104">ID</span><span class="sxs-lookup"><span data-stu-id="61469-104">ID</span></span>|<span data-ttu-id="61469-105">1131</span><span class="sxs-lookup"><span data-stu-id="61469-105">1131</span></span>|  
|<span data-ttu-id="61469-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="61469-106">Keywords</span></span>|<span data-ttu-id="61469-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="61469-107">WFRuntime</span></span>|  
|<span data-ttu-id="61469-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="61469-108">Level</span></span>|<span data-ttu-id="61469-109">Information</span><span class="sxs-lookup"><span data-stu-id="61469-109">Information</span></span>|  
|<span data-ttu-id="61469-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="61469-110">Channel</span></span>|<span data-ttu-id="61469-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="61469-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="61469-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61469-112">Description</span></span>  
 <span data-ttu-id="61469-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="61469-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="61469-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="61469-114">Message</span></span>  
 <span data-ttu-id="61469-115">InvokeMethod '%1' - Methode verwendet das asynchrone Muster von '%2' und '%3'.</span><span class="sxs-lookup"><span data-stu-id="61469-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="61469-116">Details</span><span class="sxs-lookup"><span data-stu-id="61469-116">Details</span></span>  
  
|<span data-ttu-id="61469-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="61469-117">Data Item Name</span></span>|<span data-ttu-id="61469-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="61469-118">Data Item Type</span></span>|<span data-ttu-id="61469-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61469-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="61469-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="61469-120">InvokeMethod</span></span>|<span data-ttu-id="61469-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="61469-121">xs:string</span></span>|<span data-ttu-id="61469-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="61469-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="61469-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="61469-123">BeginMethod</span></span>|<span data-ttu-id="61469-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="61469-124">xs:string</span></span>|<span data-ttu-id="61469-125">Der Name der Anfangsmethode.</span><span class="sxs-lookup"><span data-stu-id="61469-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="61469-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="61469-126">EndMethod</span></span>|<span data-ttu-id="61469-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="61469-127">xs:string</span></span>|<span data-ttu-id="61469-128">Der Name der Endmethode.</span><span class="sxs-lookup"><span data-stu-id="61469-128">The name of the end method.</span></span>|  
|<span data-ttu-id="61469-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="61469-129">AppDomain</span></span>|<span data-ttu-id="61469-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="61469-130">xs:string</span></span>|<span data-ttu-id="61469-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="61469-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
