---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 9249bdd0fe996ee7c1b04783ac8fef2c48063cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294156"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="b88b1-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="b88b1-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="b88b1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b88b1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b88b1-104">id</span><span class="sxs-lookup"><span data-stu-id="b88b1-104">ID</span></span>|<span data-ttu-id="b88b1-105">1132</span><span class="sxs-lookup"><span data-stu-id="b88b1-105">1132</span></span>|  
|<span data-ttu-id="b88b1-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="b88b1-106">Keywords</span></span>|<span data-ttu-id="b88b1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b88b1-107">WFRuntime</span></span>|  
|<span data-ttu-id="b88b1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b88b1-108">Level</span></span>|<span data-ttu-id="b88b1-109">Information</span><span class="sxs-lookup"><span data-stu-id="b88b1-109">Information</span></span>|  
|<span data-ttu-id="b88b1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b88b1-110">Channel</span></span>|<span data-ttu-id="b88b1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b88b1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b88b1-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b88b1-112">Description</span></span>  

 <span data-ttu-id="b88b1-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b88b1-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b88b1-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="b88b1-114">Message</span></span>  

 <span data-ttu-id="b88b1-115">InvokeMethod '%1' - Methode verwendet kein asynchrones Muster.</span><span class="sxs-lookup"><span data-stu-id="b88b1-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b88b1-116">Details</span><span class="sxs-lookup"><span data-stu-id="b88b1-116">Details</span></span>  
  
|<span data-ttu-id="b88b1-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b88b1-117">Data Item Name</span></span>|<span data-ttu-id="b88b1-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b88b1-118">Data Item Type</span></span>|<span data-ttu-id="b88b1-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b88b1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b88b1-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b88b1-120">InvokeMethod</span></span>|<span data-ttu-id="b88b1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b88b1-121">xs:string</span></span>|<span data-ttu-id="b88b1-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b88b1-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="b88b1-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b88b1-123">AppDomain</span></span>|<span data-ttu-id="b88b1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b88b1-124">xs:string</span></span>|<span data-ttu-id="b88b1-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b88b1-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
