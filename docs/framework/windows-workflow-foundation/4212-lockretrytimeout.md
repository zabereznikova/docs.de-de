---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abe1f560cc984551f069a75873a7e5545aec03cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="09dd3-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="09dd3-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="09dd3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="09dd3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09dd3-104">ID</span><span class="sxs-lookup"><span data-stu-id="09dd3-104">ID</span></span>|<span data-ttu-id="09dd3-105">4212</span><span class="sxs-lookup"><span data-stu-id="09dd3-105">4212</span></span>|  
|<span data-ttu-id="09dd3-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="09dd3-106">Keywords</span></span>|<span data-ttu-id="09dd3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="09dd3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="09dd3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="09dd3-108">Level</span></span>|<span data-ttu-id="09dd3-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="09dd3-109">Warning</span></span>|  
|<span data-ttu-id="09dd3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="09dd3-110">Channel</span></span>|<span data-ttu-id="09dd3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="09dd3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="09dd3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09dd3-112">Description</span></span>  
 <span data-ttu-id="09dd3-113">Im SQL-Anbieter ist ein Timeout aufgetreten bei dem Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="09dd3-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="09dd3-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="09dd3-114">Message</span></span>  
 <span data-ttu-id="09dd3-115">Timeout beim Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="09dd3-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="09dd3-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="09dd3-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="09dd3-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="09dd3-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="09dd3-118">Details</span><span class="sxs-lookup"><span data-stu-id="09dd3-118">Details</span></span>  
  
|<span data-ttu-id="09dd3-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="09dd3-119">Data Item Name</span></span>|<span data-ttu-id="09dd3-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="09dd3-120">Data Item Type</span></span>|<span data-ttu-id="09dd3-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09dd3-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="09dd3-122">Delay</span><span class="sxs-lookup"><span data-stu-id="09dd3-122">Delay</span></span>|<span data-ttu-id="09dd3-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="09dd3-123">xs:string</span></span>|<span data-ttu-id="09dd3-124">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="09dd3-124">The delay between retries.</span></span>|  
|<span data-ttu-id="09dd3-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="09dd3-125">AppDomain</span></span>|<span data-ttu-id="09dd3-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="09dd3-126">xs:string</span></span>|<span data-ttu-id="09dd3-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="09dd3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
