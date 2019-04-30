---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945937"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="01e58-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="01e58-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="01e58-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="01e58-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01e58-104">ID</span><span class="sxs-lookup"><span data-stu-id="01e58-104">ID</span></span>|<span data-ttu-id="01e58-105">3552</span><span class="sxs-lookup"><span data-stu-id="01e58-105">3552</span></span>|  
|<span data-ttu-id="01e58-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="01e58-106">Keywords</span></span>|<span data-ttu-id="01e58-107">Kontingent, WFServices</span><span class="sxs-lookup"><span data-stu-id="01e58-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="01e58-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="01e58-108">Level</span></span>|<span data-ttu-id="01e58-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="01e58-109">Warning</span></span>|  
|<span data-ttu-id="01e58-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="01e58-110">Channel</span></span>|<span data-ttu-id="01e58-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="01e58-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01e58-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01e58-112">Description</span></span>  
 <span data-ttu-id="01e58-113">Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="01e58-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01e58-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="01e58-114">Message</span></span>  
 <span data-ttu-id="01e58-115">Die drosselungsgrenze ' maxpendingmessagesperchannel ' von '%1' wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="01e58-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="01e58-116">Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="01e58-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01e58-117">Details</span><span class="sxs-lookup"><span data-stu-id="01e58-117">Details</span></span>  
  
|<span data-ttu-id="01e58-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="01e58-118">Data Item Name</span></span>|<span data-ttu-id="01e58-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="01e58-119">Data Item Type</span></span>|<span data-ttu-id="01e58-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01e58-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01e58-121">Limit</span><span class="sxs-lookup"><span data-stu-id="01e58-121">Limit</span></span>|<span data-ttu-id="01e58-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="01e58-122">xs:string</span></span>|<span data-ttu-id="01e58-123">Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="01e58-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="01e58-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="01e58-124">AppDomain</span></span>|<span data-ttu-id="01e58-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="01e58-125">xs:string</span></span>|<span data-ttu-id="01e58-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="01e58-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
