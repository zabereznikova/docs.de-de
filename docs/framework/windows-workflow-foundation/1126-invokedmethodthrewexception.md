---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 7caaebe42f49a62fec61ba17a4d3fe3a538e2ab4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262839"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="a6e0a-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="a6e0a-102">1126 - InvokedMethodThrewException</span></span>

## <a name="properties"></a><span data-ttu-id="a6e0a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6e0a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6e0a-104">id</span><span class="sxs-lookup"><span data-stu-id="a6e0a-104">ID</span></span>|<span data-ttu-id="a6e0a-105">1126</span><span class="sxs-lookup"><span data-stu-id="a6e0a-105">1126</span></span>|  
|<span data-ttu-id="a6e0a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="a6e0a-106">Keywords</span></span>|<span data-ttu-id="a6e0a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a6e0a-107">WFRuntime</span></span>|  
|<span data-ttu-id="a6e0a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a6e0a-108">Level</span></span>|<span data-ttu-id="a6e0a-109">Information</span><span class="sxs-lookup"><span data-stu-id="a6e0a-109">Information</span></span>|  
|<span data-ttu-id="a6e0a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a6e0a-110">Channel</span></span>|<span data-ttu-id="a6e0a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a6e0a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6e0a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a6e0a-112">Description</span></span>  

 <span data-ttu-id="a6e0a-113">Gibt an, dass von der Methode, die von der InvokeMethod-Aktivität aufgerufen wurde, eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6e0a-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="a6e0a-114">Message</span></span>  

 <span data-ttu-id="a6e0a-115">In der von der Aktivität '%1' aufgerufenen Methode wurde eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="a6e0a-116">%2</span><span class="sxs-lookup"><span data-stu-id="a6e0a-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6e0a-117">Details</span><span class="sxs-lookup"><span data-stu-id="a6e0a-117">Details</span></span>  
  
|<span data-ttu-id="a6e0a-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a6e0a-118">Data Item Name</span></span>|<span data-ttu-id="a6e0a-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a6e0a-119">Data Item Type</span></span>|<span data-ttu-id="a6e0a-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a6e0a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6e0a-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a6e0a-121">InvokeMethod</span></span>|<span data-ttu-id="a6e0a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e0a-122">xs:string</span></span>|<span data-ttu-id="a6e0a-123">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="a6e0a-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="a6e0a-124">Exception</span></span>|<span data-ttu-id="a6e0a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e0a-125">xs:string</span></span>|<span data-ttu-id="a6e0a-126">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="a6e0a-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a6e0a-127">AppDomain</span></span>|<span data-ttu-id="a6e0a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6e0a-128">xs:string</span></span>|<span data-ttu-id="a6e0a-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6e0a-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
