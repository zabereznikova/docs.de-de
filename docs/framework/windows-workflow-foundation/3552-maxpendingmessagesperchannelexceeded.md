---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511230"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="a8728-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="a8728-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="a8728-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a8728-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8728-104">ID</span><span class="sxs-lookup"><span data-stu-id="a8728-104">ID</span></span>|<span data-ttu-id="a8728-105">3552</span><span class="sxs-lookup"><span data-stu-id="a8728-105">3552</span></span>|  
|<span data-ttu-id="a8728-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a8728-106">Keywords</span></span>|<span data-ttu-id="a8728-107">Kontingent, WFServices</span><span class="sxs-lookup"><span data-stu-id="a8728-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="a8728-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a8728-108">Level</span></span>|<span data-ttu-id="a8728-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="a8728-109">Warning</span></span>|  
|<span data-ttu-id="a8728-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a8728-110">Channel</span></span>|<span data-ttu-id="a8728-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a8728-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a8728-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8728-112">Description</span></span>  
 <span data-ttu-id="a8728-113">Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="a8728-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a8728-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a8728-114">Message</span></span>  
 <span data-ttu-id="a8728-115">Die drosselungsgrenze ' maxpendingmessagesperchannel ' von "%1" wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="a8728-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="a8728-116">Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="a8728-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a8728-117">Details</span><span class="sxs-lookup"><span data-stu-id="a8728-117">Details</span></span>  
  
|<span data-ttu-id="a8728-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a8728-118">Data Item Name</span></span>|<span data-ttu-id="a8728-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a8728-119">Data Item Type</span></span>|<span data-ttu-id="a8728-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8728-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a8728-121">Limit</span><span class="sxs-lookup"><span data-stu-id="a8728-121">Limit</span></span>|<span data-ttu-id="a8728-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8728-122">xs:string</span></span>|<span data-ttu-id="a8728-123">Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="a8728-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="a8728-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a8728-124">AppDomain</span></span>|<span data-ttu-id="a8728-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8728-125">xs:string</span></span>|<span data-ttu-id="a8728-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a8728-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
