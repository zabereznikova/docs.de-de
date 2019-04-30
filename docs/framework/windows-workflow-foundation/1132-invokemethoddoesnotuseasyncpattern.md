---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924214"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="0bc57-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="0bc57-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="0bc57-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0bc57-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bc57-104">ID</span><span class="sxs-lookup"><span data-stu-id="0bc57-104">ID</span></span>|<span data-ttu-id="0bc57-105">1132</span><span class="sxs-lookup"><span data-stu-id="0bc57-105">1132</span></span>|  
|<span data-ttu-id="0bc57-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0bc57-106">Keywords</span></span>|<span data-ttu-id="0bc57-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0bc57-107">WFRuntime</span></span>|  
|<span data-ttu-id="0bc57-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0bc57-108">Level</span></span>|<span data-ttu-id="0bc57-109">Information</span><span class="sxs-lookup"><span data-stu-id="0bc57-109">Information</span></span>|  
|<span data-ttu-id="0bc57-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0bc57-110">Channel</span></span>|<span data-ttu-id="0bc57-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0bc57-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0bc57-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bc57-112">Description</span></span>  
 <span data-ttu-id="0bc57-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bc57-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0bc57-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0bc57-114">Message</span></span>  
 <span data-ttu-id="0bc57-115">InvokeMethod '%1' - Methode verwendet kein asynchrones Muster.</span><span class="sxs-lookup"><span data-stu-id="0bc57-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0bc57-116">Details</span><span class="sxs-lookup"><span data-stu-id="0bc57-116">Details</span></span>  
  
|<span data-ttu-id="0bc57-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0bc57-117">Data Item Name</span></span>|<span data-ttu-id="0bc57-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0bc57-118">Data Item Type</span></span>|<span data-ttu-id="0bc57-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bc57-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0bc57-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="0bc57-120">InvokeMethod</span></span>|<span data-ttu-id="0bc57-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0bc57-121">xs:string</span></span>|<span data-ttu-id="0bc57-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0bc57-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="0bc57-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0bc57-123">AppDomain</span></span>|<span data-ttu-id="0bc57-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0bc57-124">xs:string</span></span>|<span data-ttu-id="0bc57-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0bc57-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
