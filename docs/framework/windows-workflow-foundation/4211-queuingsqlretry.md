---
title: 4211 - QueuingSqlRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ffd44cf9d2333b22e3be809d05f2fa8c33d4cac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="bfa96-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="bfa96-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="bfa96-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bfa96-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfa96-104">ID</span><span class="sxs-lookup"><span data-stu-id="bfa96-104">ID</span></span>|<span data-ttu-id="bfa96-105">4211</span><span class="sxs-lookup"><span data-stu-id="bfa96-105">4211</span></span>|  
|<span data-ttu-id="bfa96-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bfa96-106">Keywords</span></span>|<span data-ttu-id="bfa96-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="bfa96-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="bfa96-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bfa96-108">Level</span></span>|<span data-ttu-id="bfa96-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="bfa96-109">Warning</span></span>|  
|<span data-ttu-id="bfa96-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bfa96-110">Channel</span></span>|<span data-ttu-id="bfa96-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bfa96-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bfa96-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfa96-112">Description</span></span>  
 <span data-ttu-id="bfa96-113">Gibt an, dass eine SQL-Wiederholung in die Warteschlange gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bfa96-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bfa96-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="bfa96-114">Message</span></span>  
 <span data-ttu-id="bfa96-115">SQL-Wiederholung wird mit einer Verzögerung von %1 Millisekunden in die Warteschlange eingefügt.</span><span class="sxs-lookup"><span data-stu-id="bfa96-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bfa96-116">Details</span><span class="sxs-lookup"><span data-stu-id="bfa96-116">Details</span></span>  
  
|<span data-ttu-id="bfa96-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bfa96-117">Data Item Name</span></span>|<span data-ttu-id="bfa96-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bfa96-118">Data Item Type</span></span>|<span data-ttu-id="bfa96-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfa96-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bfa96-120">Delay</span><span class="sxs-lookup"><span data-stu-id="bfa96-120">Delay</span></span>|<span data-ttu-id="bfa96-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bfa96-121">xs:string</span></span>|<span data-ttu-id="bfa96-122">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="bfa96-122">The delay between retries.</span></span>|  
|<span data-ttu-id="bfa96-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bfa96-123">AppDomain</span></span>|<span data-ttu-id="bfa96-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bfa96-124">xs:string</span></span>|<span data-ttu-id="bfa96-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bfa96-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
