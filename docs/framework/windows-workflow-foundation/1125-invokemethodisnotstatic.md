---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 0405b4e1207db5c056fbd478b98c408258daf0c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294208"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="29534-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="29534-102">1125 - InvokeMethodIsNotStatic</span></span>

## <a name="properties"></a><span data-ttu-id="29534-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29534-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29534-104">id</span><span class="sxs-lookup"><span data-stu-id="29534-104">ID</span></span>|<span data-ttu-id="29534-105">1125</span><span class="sxs-lookup"><span data-stu-id="29534-105">1125</span></span>|  
|<span data-ttu-id="29534-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="29534-106">Keywords</span></span>|<span data-ttu-id="29534-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="29534-107">WFRuntime</span></span>|  
|<span data-ttu-id="29534-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="29534-108">Level</span></span>|<span data-ttu-id="29534-109">Information</span><span class="sxs-lookup"><span data-stu-id="29534-109">Information</span></span>|  
|<span data-ttu-id="29534-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="29534-110">Channel</span></span>|<span data-ttu-id="29534-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="29534-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="29534-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="29534-112">Description</span></span>  

 <span data-ttu-id="29534-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass die aufzurufende Methode nicht statisch ist.</span><span class="sxs-lookup"><span data-stu-id="29534-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="29534-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="29534-114">Message</span></span>  

 <span data-ttu-id="29534-115">InvokeMethod '%1' - Methode ist nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="29534-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="29534-116">Details</span><span class="sxs-lookup"><span data-stu-id="29534-116">Details</span></span>  
  
|<span data-ttu-id="29534-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="29534-117">Data Item Name</span></span>|<span data-ttu-id="29534-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="29534-118">Data Item Type</span></span>|<span data-ttu-id="29534-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="29534-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="29534-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="29534-120">InvokeMethod</span></span>|<span data-ttu-id="29534-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="29534-121">xs:string</span></span>|<span data-ttu-id="29534-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="29534-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="29534-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="29534-123">AppDomain</span></span>|<span data-ttu-id="29534-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="29534-124">xs:string</span></span>|<span data-ttu-id="29534-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="29534-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
