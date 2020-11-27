---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261162"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="fa32c-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="fa32c-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="fa32c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fa32c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa32c-104">id</span><span class="sxs-lookup"><span data-stu-id="fa32c-104">ID</span></span>|<span data-ttu-id="fa32c-105">3552</span><span class="sxs-lookup"><span data-stu-id="fa32c-105">3552</span></span>|  
|<span data-ttu-id="fa32c-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="fa32c-106">Keywords</span></span>|<span data-ttu-id="fa32c-107">Kontingent, WFServices</span><span class="sxs-lookup"><span data-stu-id="fa32c-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="fa32c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fa32c-108">Level</span></span>|<span data-ttu-id="fa32c-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="fa32c-109">Warning</span></span>|  
|<span data-ttu-id="fa32c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fa32c-110">Channel</span></span>|<span data-ttu-id="fa32c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fa32c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fa32c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa32c-112">Description</span></span>  

 <span data-ttu-id="fa32c-113">Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="fa32c-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fa32c-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="fa32c-114">Message</span></span>  

 <span data-ttu-id="fa32c-115">Die Drosselungsgrenze 'MaxPendingMessagesPerChannel' von '%1' wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="fa32c-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="fa32c-116">Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="fa32c-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fa32c-117">Details</span><span class="sxs-lookup"><span data-stu-id="fa32c-117">Details</span></span>  
  
|<span data-ttu-id="fa32c-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fa32c-118">Data Item Name</span></span>|<span data-ttu-id="fa32c-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fa32c-119">Data Item Type</span></span>|<span data-ttu-id="fa32c-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa32c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fa32c-121">Begrenzung</span><span class="sxs-lookup"><span data-stu-id="fa32c-121">Limit</span></span>|<span data-ttu-id="fa32c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa32c-122">xs:string</span></span>|<span data-ttu-id="fa32c-123">Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="fa32c-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="fa32c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa32c-124">AppDomain</span></span>|<span data-ttu-id="fa32c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa32c-125">xs:string</span></span>|<span data-ttu-id="fa32c-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fa32c-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
