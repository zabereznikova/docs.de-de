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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 897e6ef8b739654a61058106966c870c47f8129a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="9b176-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="9b176-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="9b176-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b176-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b176-104">ID</span><span class="sxs-lookup"><span data-stu-id="9b176-104">ID</span></span>|<span data-ttu-id="9b176-105">4212</span><span class="sxs-lookup"><span data-stu-id="9b176-105">4212</span></span>|  
|<span data-ttu-id="9b176-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9b176-106">Keywords</span></span>|<span data-ttu-id="9b176-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="9b176-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="9b176-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9b176-108">Level</span></span>|<span data-ttu-id="9b176-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="9b176-109">Warning</span></span>|  
|<span data-ttu-id="9b176-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9b176-110">Channel</span></span>|<span data-ttu-id="9b176-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9b176-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9b176-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b176-112">Description</span></span>  
 <span data-ttu-id="9b176-113">Im SQL-Anbieter ist ein Timeout aufgetreten bei dem Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9b176-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9b176-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9b176-114">Message</span></span>  
 <span data-ttu-id="9b176-115">Timeout beim Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9b176-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="9b176-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9b176-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="9b176-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="9b176-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9b176-118">Details</span><span class="sxs-lookup"><span data-stu-id="9b176-118">Details</span></span>  
  
|<span data-ttu-id="9b176-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9b176-119">Data Item Name</span></span>|<span data-ttu-id="9b176-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9b176-120">Data Item Type</span></span>|<span data-ttu-id="9b176-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b176-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9b176-122">Delay</span><span class="sxs-lookup"><span data-stu-id="9b176-122">Delay</span></span>|<span data-ttu-id="9b176-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b176-123">xs:string</span></span>|<span data-ttu-id="9b176-124">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="9b176-124">The delay between retries.</span></span>|  
|<span data-ttu-id="9b176-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9b176-125">AppDomain</span></span>|<span data-ttu-id="9b176-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b176-126">xs:string</span></span>|<span data-ttu-id="9b176-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9b176-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
