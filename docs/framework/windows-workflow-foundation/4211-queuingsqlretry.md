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
ms.openlocfilehash: 349a91f5b4708d829aee8d7f055871ac7dcc8914
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="38ef9-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="38ef9-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="38ef9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="38ef9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38ef9-104">ID</span><span class="sxs-lookup"><span data-stu-id="38ef9-104">ID</span></span>|<span data-ttu-id="38ef9-105">4211</span><span class="sxs-lookup"><span data-stu-id="38ef9-105">4211</span></span>|  
|<span data-ttu-id="38ef9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="38ef9-106">Keywords</span></span>|<span data-ttu-id="38ef9-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="38ef9-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="38ef9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="38ef9-108">Level</span></span>|<span data-ttu-id="38ef9-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="38ef9-109">Warning</span></span>|  
|<span data-ttu-id="38ef9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="38ef9-110">Channel</span></span>|<span data-ttu-id="38ef9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="38ef9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38ef9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38ef9-112">Description</span></span>  
 <span data-ttu-id="38ef9-113">Gibt an, dass eine SQL-Wiederholung in die Warteschlange gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="38ef9-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="38ef9-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="38ef9-114">Message</span></span>  
 <span data-ttu-id="38ef9-115">SQL-Wiederholung wird mit einer Verzögerung von %1 Millisekunden in die Warteschlange eingefügt.</span><span class="sxs-lookup"><span data-stu-id="38ef9-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="38ef9-116">Details</span><span class="sxs-lookup"><span data-stu-id="38ef9-116">Details</span></span>  
  
|<span data-ttu-id="38ef9-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="38ef9-117">Data Item Name</span></span>|<span data-ttu-id="38ef9-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="38ef9-118">Data Item Type</span></span>|<span data-ttu-id="38ef9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38ef9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="38ef9-120">Delay</span><span class="sxs-lookup"><span data-stu-id="38ef9-120">Delay</span></span>|<span data-ttu-id="38ef9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="38ef9-121">xs:string</span></span>|<span data-ttu-id="38ef9-122">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="38ef9-122">The delay between retries.</span></span>|  
|<span data-ttu-id="38ef9-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="38ef9-123">AppDomain</span></span>|<span data-ttu-id="38ef9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="38ef9-124">xs:string</span></span>|<span data-ttu-id="38ef9-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="38ef9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
