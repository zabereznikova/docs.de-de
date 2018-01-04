---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75386b56f7926b9ddb883e0ca212d795898fe6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="76cfb-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="76cfb-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="76cfb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="76cfb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76cfb-104">ID</span><span class="sxs-lookup"><span data-stu-id="76cfb-104">ID</span></span>|<span data-ttu-id="76cfb-105">1132</span><span class="sxs-lookup"><span data-stu-id="76cfb-105">1132</span></span>|  
|<span data-ttu-id="76cfb-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="76cfb-106">Keywords</span></span>|<span data-ttu-id="76cfb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="76cfb-107">WFRuntime</span></span>|  
|<span data-ttu-id="76cfb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="76cfb-108">Level</span></span>|<span data-ttu-id="76cfb-109">Information</span><span class="sxs-lookup"><span data-stu-id="76cfb-109">Information</span></span>|  
|<span data-ttu-id="76cfb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="76cfb-110">Channel</span></span>|<span data-ttu-id="76cfb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="76cfb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76cfb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76cfb-112">Description</span></span>  
 <span data-ttu-id="76cfb-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cfb-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76cfb-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="76cfb-114">Message</span></span>  
 <span data-ttu-id="76cfb-115">InvokeMethod '%1' - Methode verwendet kein asynchrones Muster.</span><span class="sxs-lookup"><span data-stu-id="76cfb-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76cfb-116">Details</span><span class="sxs-lookup"><span data-stu-id="76cfb-116">Details</span></span>  
  
|<span data-ttu-id="76cfb-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="76cfb-117">Data Item Name</span></span>|<span data-ttu-id="76cfb-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="76cfb-118">Data Item Type</span></span>|<span data-ttu-id="76cfb-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76cfb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76cfb-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="76cfb-120">InvokeMethod</span></span>|<span data-ttu-id="76cfb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="76cfb-121">xs:string</span></span>|<span data-ttu-id="76cfb-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="76cfb-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="76cfb-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76cfb-123">AppDomain</span></span>|<span data-ttu-id="76cfb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="76cfb-124">xs:string</span></span>|<span data-ttu-id="76cfb-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="76cfb-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
