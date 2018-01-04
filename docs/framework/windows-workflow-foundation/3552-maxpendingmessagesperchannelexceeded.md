---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf90e78ed7fbfe500ac52e6629d31bd0aff97bd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="307c5-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="307c5-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="307c5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="307c5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="307c5-104">ID</span><span class="sxs-lookup"><span data-stu-id="307c5-104">ID</span></span>|<span data-ttu-id="307c5-105">3552</span><span class="sxs-lookup"><span data-stu-id="307c5-105">3552</span></span>|  
|<span data-ttu-id="307c5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="307c5-106">Keywords</span></span>|<span data-ttu-id="307c5-107">Kontingent, WFServices</span><span class="sxs-lookup"><span data-stu-id="307c5-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="307c5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="307c5-108">Level</span></span>|<span data-ttu-id="307c5-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="307c5-109">Warning</span></span>|  
|<span data-ttu-id="307c5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="307c5-110">Channel</span></span>|<span data-ttu-id="307c5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="307c5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="307c5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="307c5-112">Description</span></span>  
 <span data-ttu-id="307c5-113">Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="307c5-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="307c5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="307c5-114">Message</span></span>  
 <span data-ttu-id="307c5-115">Die drosselungsgrenze ' maxpendingmessagesperchannel ' von "%1" wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="307c5-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="307c5-116">Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="307c5-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="307c5-117">Details</span><span class="sxs-lookup"><span data-stu-id="307c5-117">Details</span></span>  
  
|<span data-ttu-id="307c5-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="307c5-118">Data Item Name</span></span>|<span data-ttu-id="307c5-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="307c5-119">Data Item Type</span></span>|<span data-ttu-id="307c5-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="307c5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="307c5-121">Limit</span><span class="sxs-lookup"><span data-stu-id="307c5-121">Limit</span></span>|<span data-ttu-id="307c5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="307c5-122">xs:string</span></span>|<span data-ttu-id="307c5-123">Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="307c5-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="307c5-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="307c5-124">AppDomain</span></span>|<span data-ttu-id="307c5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="307c5-125">xs:string</span></span>|<span data-ttu-id="307c5-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="307c5-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
