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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 934c2947e86b429e9b990c273f22c0511f209a53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="2e5df-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="2e5df-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="2e5df-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e5df-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e5df-104">ID</span><span class="sxs-lookup"><span data-stu-id="2e5df-104">ID</span></span>|<span data-ttu-id="2e5df-105">1125</span><span class="sxs-lookup"><span data-stu-id="2e5df-105">1125</span></span>|  
|<span data-ttu-id="2e5df-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2e5df-106">Keywords</span></span>|<span data-ttu-id="2e5df-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2e5df-107">WFRuntime</span></span>|  
|<span data-ttu-id="2e5df-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e5df-108">Level</span></span>|<span data-ttu-id="2e5df-109">Information</span><span class="sxs-lookup"><span data-stu-id="2e5df-109">Information</span></span>|  
|<span data-ttu-id="2e5df-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2e5df-110">Channel</span></span>|<span data-ttu-id="2e5df-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2e5df-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2e5df-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e5df-112">Description</span></span>  
 <span data-ttu-id="2e5df-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass die aufzurufende Methode nicht statisch ist.</span><span class="sxs-lookup"><span data-stu-id="2e5df-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2e5df-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="2e5df-114">Message</span></span>  
 <span data-ttu-id="2e5df-115">InvokeMethod '%1' - Methode ist nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="2e5df-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2e5df-116">Details</span><span class="sxs-lookup"><span data-stu-id="2e5df-116">Details</span></span>  
  
|<span data-ttu-id="2e5df-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2e5df-117">Data Item Name</span></span>|<span data-ttu-id="2e5df-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2e5df-118">Data Item Type</span></span>|<span data-ttu-id="2e5df-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e5df-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2e5df-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="2e5df-120">InvokeMethod</span></span>|<span data-ttu-id="2e5df-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e5df-121">xs:string</span></span>|<span data-ttu-id="2e5df-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2e5df-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="2e5df-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2e5df-123">AppDomain</span></span>|<span data-ttu-id="2e5df-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e5df-124">xs:string</span></span>|<span data-ttu-id="2e5df-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e5df-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
