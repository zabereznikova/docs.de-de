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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c318ee6509ce8b96a1e7e78a13f4aeb7c76dde6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="70940-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="70940-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="70940-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="70940-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70940-104">ID</span><span class="sxs-lookup"><span data-stu-id="70940-104">ID</span></span>|<span data-ttu-id="70940-105">4211</span><span class="sxs-lookup"><span data-stu-id="70940-105">4211</span></span>|  
|<span data-ttu-id="70940-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="70940-106">Keywords</span></span>|<span data-ttu-id="70940-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="70940-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="70940-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="70940-108">Level</span></span>|<span data-ttu-id="70940-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="70940-109">Warning</span></span>|  
|<span data-ttu-id="70940-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="70940-110">Channel</span></span>|<span data-ttu-id="70940-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="70940-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="70940-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70940-112">Description</span></span>  
 <span data-ttu-id="70940-113">Gibt an, dass eine SQL-Wiederholung in die Warteschlange gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="70940-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="70940-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="70940-114">Message</span></span>  
 <span data-ttu-id="70940-115">SQL-Wiederholung wird mit einer Verzögerung von %1 Millisekunden in die Warteschlange eingefügt.</span><span class="sxs-lookup"><span data-stu-id="70940-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="70940-116">Details</span><span class="sxs-lookup"><span data-stu-id="70940-116">Details</span></span>  
  
|<span data-ttu-id="70940-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="70940-117">Data Item Name</span></span>|<span data-ttu-id="70940-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="70940-118">Data Item Type</span></span>|<span data-ttu-id="70940-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70940-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="70940-120">Delay</span><span class="sxs-lookup"><span data-stu-id="70940-120">Delay</span></span>|<span data-ttu-id="70940-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="70940-121">xs:string</span></span>|<span data-ttu-id="70940-122">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="70940-122">The delay between retries.</span></span>|  
|<span data-ttu-id="70940-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="70940-123">AppDomain</span></span>|<span data-ttu-id="70940-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="70940-124">xs:string</span></span>|<span data-ttu-id="70940-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="70940-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
