---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 2192b63b8a08657b69f6e3984f898bd6baddbc5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294182"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="3403b-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="3403b-102">1131 - InvokeMethodUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="3403b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3403b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3403b-104">id</span><span class="sxs-lookup"><span data-stu-id="3403b-104">ID</span></span>|<span data-ttu-id="3403b-105">1131</span><span class="sxs-lookup"><span data-stu-id="3403b-105">1131</span></span>|  
|<span data-ttu-id="3403b-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="3403b-106">Keywords</span></span>|<span data-ttu-id="3403b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3403b-107">WFRuntime</span></span>|  
|<span data-ttu-id="3403b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3403b-108">Level</span></span>|<span data-ttu-id="3403b-109">Information</span><span class="sxs-lookup"><span data-stu-id="3403b-109">Information</span></span>|  
|<span data-ttu-id="3403b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3403b-110">Channel</span></span>|<span data-ttu-id="3403b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3403b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3403b-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3403b-112">Description</span></span>  

 <span data-ttu-id="3403b-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="3403b-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3403b-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="3403b-114">Message</span></span>  

 <span data-ttu-id="3403b-115">InvokeMethod '%1' - Methode verwendet das asynchrone Muster von '%2' und '%3'.</span><span class="sxs-lookup"><span data-stu-id="3403b-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3403b-116">Details</span><span class="sxs-lookup"><span data-stu-id="3403b-116">Details</span></span>  
  
|<span data-ttu-id="3403b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3403b-117">Data Item Name</span></span>|<span data-ttu-id="3403b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3403b-118">Data Item Type</span></span>|<span data-ttu-id="3403b-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3403b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3403b-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="3403b-120">InvokeMethod</span></span>|<span data-ttu-id="3403b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3403b-121">xs:string</span></span>|<span data-ttu-id="3403b-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3403b-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="3403b-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="3403b-123">BeginMethod</span></span>|<span data-ttu-id="3403b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3403b-124">xs:string</span></span>|<span data-ttu-id="3403b-125">Der Name der Anfangsmethode.</span><span class="sxs-lookup"><span data-stu-id="3403b-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="3403b-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="3403b-126">EndMethod</span></span>|<span data-ttu-id="3403b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3403b-127">xs:string</span></span>|<span data-ttu-id="3403b-128">Der Name der Endmethode.</span><span class="sxs-lookup"><span data-stu-id="3403b-128">The name of the end method.</span></span>|  
|<span data-ttu-id="3403b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3403b-129">AppDomain</span></span>|<span data-ttu-id="3403b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3403b-130">xs:string</span></span>|<span data-ttu-id="3403b-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3403b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
