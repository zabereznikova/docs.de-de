---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267181"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="cc646-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="cc646-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="cc646-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cc646-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc646-104">id</span><span class="sxs-lookup"><span data-stu-id="cc646-104">ID</span></span>|<span data-ttu-id="cc646-105">4211</span><span class="sxs-lookup"><span data-stu-id="cc646-105">4211</span></span>|  
|<span data-ttu-id="cc646-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="cc646-106">Keywords</span></span>|<span data-ttu-id="cc646-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="cc646-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="cc646-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="cc646-108">Level</span></span>|<span data-ttu-id="cc646-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="cc646-109">Warning</span></span>|  
|<span data-ttu-id="cc646-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="cc646-110">Channel</span></span>|<span data-ttu-id="cc646-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cc646-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cc646-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cc646-112">Description</span></span>  

 <span data-ttu-id="cc646-113">Gibt an, dass eine SQL-Wiederholung in die Warteschlange gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cc646-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cc646-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="cc646-114">Message</span></span>  

 <span data-ttu-id="cc646-115">SQL-Wiederholung wird mit einer Verzögerung von %1 Millisekunden in die Warteschlange eingefügt.</span><span class="sxs-lookup"><span data-stu-id="cc646-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc646-116">Details</span><span class="sxs-lookup"><span data-stu-id="cc646-116">Details</span></span>  
  
|<span data-ttu-id="cc646-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="cc646-117">Data Item Name</span></span>|<span data-ttu-id="cc646-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="cc646-118">Data Item Type</span></span>|<span data-ttu-id="cc646-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cc646-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cc646-120">Verzögern</span><span class="sxs-lookup"><span data-stu-id="cc646-120">Delay</span></span>|<span data-ttu-id="cc646-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc646-121">xs:string</span></span>|<span data-ttu-id="cc646-122">Die Verzögerung zwischen den Wiederholungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="cc646-122">The delay between retries.</span></span>|  
|<span data-ttu-id="cc646-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cc646-123">AppDomain</span></span>|<span data-ttu-id="cc646-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc646-124">xs:string</span></span>|<span data-ttu-id="cc646-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cc646-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
