---
title: 1125 - InvokeMethodIsNotStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8b5e255e9a753c6476a070609b0cbda189d37a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="e7d64-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="e7d64-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="e7d64-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e7d64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7d64-104">ID</span><span class="sxs-lookup"><span data-stu-id="e7d64-104">ID</span></span>|<span data-ttu-id="e7d64-105">1125</span><span class="sxs-lookup"><span data-stu-id="e7d64-105">1125</span></span>|  
|<span data-ttu-id="e7d64-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e7d64-106">Keywords</span></span>|<span data-ttu-id="e7d64-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e7d64-107">WFRuntime</span></span>|  
|<span data-ttu-id="e7d64-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e7d64-108">Level</span></span>|<span data-ttu-id="e7d64-109">Information</span><span class="sxs-lookup"><span data-stu-id="e7d64-109">Information</span></span>|  
|<span data-ttu-id="e7d64-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e7d64-110">Channel</span></span>|<span data-ttu-id="e7d64-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e7d64-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e7d64-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7d64-112">Description</span></span>  
 <span data-ttu-id="e7d64-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass die aufzurufende Methode nicht statisch ist.</span><span class="sxs-lookup"><span data-stu-id="e7d64-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e7d64-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="e7d64-114">Message</span></span>  
 <span data-ttu-id="e7d64-115">InvokeMethod '%1' - Methode ist nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="e7d64-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e7d64-116">Details</span><span class="sxs-lookup"><span data-stu-id="e7d64-116">Details</span></span>  
  
|<span data-ttu-id="e7d64-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e7d64-117">Data Item Name</span></span>|<span data-ttu-id="e7d64-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e7d64-118">Data Item Type</span></span>|<span data-ttu-id="e7d64-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7d64-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e7d64-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="e7d64-120">InvokeMethod</span></span>|<span data-ttu-id="e7d64-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7d64-121">xs:string</span></span>|<span data-ttu-id="e7d64-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e7d64-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="e7d64-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e7d64-123">AppDomain</span></span>|<span data-ttu-id="e7d64-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7d64-124">xs:string</span></span>|<span data-ttu-id="e7d64-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e7d64-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
