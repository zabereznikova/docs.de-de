---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267168"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="c4610-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="c4610-102">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="c4610-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c4610-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4610-104">id</span><span class="sxs-lookup"><span data-stu-id="c4610-104">ID</span></span>|<span data-ttu-id="c4610-105">4212</span><span class="sxs-lookup"><span data-stu-id="c4610-105">4212</span></span>|  
|<span data-ttu-id="c4610-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c4610-106">Keywords</span></span>|<span data-ttu-id="c4610-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c4610-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c4610-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="c4610-108">Level</span></span>|<span data-ttu-id="c4610-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="c4610-109">Warning</span></span>|  
|<span data-ttu-id="c4610-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="c4610-110">Channel</span></span>|<span data-ttu-id="c4610-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c4610-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c4610-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4610-112">Description</span></span>  

 <span data-ttu-id="c4610-113">Im SQL-Anbieter ist ein Timeout aufgetreten bei dem Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4610-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c4610-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="c4610-114">Message</span></span>  

 <span data-ttu-id="c4610-115">Timeout beim Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4610-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="c4610-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c4610-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="c4610-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="c4610-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c4610-118">Details</span><span class="sxs-lookup"><span data-stu-id="c4610-118">Details</span></span>  
  
|<span data-ttu-id="c4610-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="c4610-119">Data Item Name</span></span>|<span data-ttu-id="c4610-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="c4610-120">Data Item Type</span></span>|<span data-ttu-id="c4610-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4610-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c4610-122">Verzögern</span><span class="sxs-lookup"><span data-stu-id="c4610-122">Delay</span></span>|<span data-ttu-id="c4610-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4610-123">xs:string</span></span>|<span data-ttu-id="c4610-124">Die Verzögerung zwischen den Wiederholungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="c4610-124">The delay between retries.</span></span>|  
|<span data-ttu-id="c4610-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c4610-125">AppDomain</span></span>|<span data-ttu-id="c4610-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c4610-126">xs:string</span></span>|<span data-ttu-id="c4610-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c4610-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
