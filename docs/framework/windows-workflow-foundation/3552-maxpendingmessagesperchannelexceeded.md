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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ba5e4aa8e1338321838e40db7d976107315ef64
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="d0d5f-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="d0d5f-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="d0d5f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0d5f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0d5f-104">ID</span><span class="sxs-lookup"><span data-stu-id="d0d5f-104">ID</span></span>|<span data-ttu-id="d0d5f-105">3552</span><span class="sxs-lookup"><span data-stu-id="d0d5f-105">3552</span></span>|  
|<span data-ttu-id="d0d5f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d0d5f-106">Keywords</span></span>|<span data-ttu-id="d0d5f-107">Kontingent, WFServices</span><span class="sxs-lookup"><span data-stu-id="d0d5f-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="d0d5f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d0d5f-108">Level</span></span>|<span data-ttu-id="d0d5f-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="d0d5f-109">Warning</span></span>|  
|<span data-ttu-id="d0d5f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d0d5f-110">Channel</span></span>|<span data-ttu-id="d0d5f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d0d5f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0d5f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0d5f-112">Description</span></span>  
 <span data-ttu-id="d0d5f-113">Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="d0d5f-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0d5f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d0d5f-114">Message</span></span>  
 <span data-ttu-id="d0d5f-115">Die drosselungsgrenze ' maxpendingmessagesperchannel ' von "%1" wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="d0d5f-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="d0d5f-116">Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="d0d5f-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0d5f-117">Details</span><span class="sxs-lookup"><span data-stu-id="d0d5f-117">Details</span></span>  
  
|<span data-ttu-id="d0d5f-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d0d5f-118">Data Item Name</span></span>|<span data-ttu-id="d0d5f-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d0d5f-119">Data Item Type</span></span>|<span data-ttu-id="d0d5f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0d5f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0d5f-121">Limit</span><span class="sxs-lookup"><span data-stu-id="d0d5f-121">Limit</span></span>|<span data-ttu-id="d0d5f-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0d5f-122">xs:string</span></span>|<span data-ttu-id="d0d5f-123">Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="d0d5f-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="d0d5f-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0d5f-124">AppDomain</span></span>|<span data-ttu-id="d0d5f-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0d5f-125">xs:string</span></span>|<span data-ttu-id="d0d5f-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d0d5f-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
