---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dc752a5c9d5bebe39a4d4be2c3642333aa041de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="1d3cc-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="1d3cc-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="1d3cc-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d3cc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d3cc-104">ID</span><span class="sxs-lookup"><span data-stu-id="1d3cc-104">ID</span></span>|<span data-ttu-id="1d3cc-105">1126</span><span class="sxs-lookup"><span data-stu-id="1d3cc-105">1126</span></span>|  
|<span data-ttu-id="1d3cc-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1d3cc-106">Keywords</span></span>|<span data-ttu-id="1d3cc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1d3cc-107">WFRuntime</span></span>|  
|<span data-ttu-id="1d3cc-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1d3cc-108">Level</span></span>|<span data-ttu-id="1d3cc-109">Information</span><span class="sxs-lookup"><span data-stu-id="1d3cc-109">Information</span></span>|  
|<span data-ttu-id="1d3cc-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1d3cc-110">Channel</span></span>|<span data-ttu-id="1d3cc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1d3cc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d3cc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d3cc-112">Description</span></span>  
 <span data-ttu-id="1d3cc-113">Gibt an, dass von der Methode, die von der InvokeMethod-Aktivität aufgerufen wurde, eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1d3cc-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d3cc-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1d3cc-114">Message</span></span>  
 <span data-ttu-id="1d3cc-115">In der von der Aktivität '%1' aufgerufenen Methode wurde eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1d3cc-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="1d3cc-116">%2</span><span class="sxs-lookup"><span data-stu-id="1d3cc-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d3cc-117">Details</span><span class="sxs-lookup"><span data-stu-id="1d3cc-117">Details</span></span>  
  
|<span data-ttu-id="1d3cc-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1d3cc-118">Data Item Name</span></span>|<span data-ttu-id="1d3cc-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1d3cc-119">Data Item Type</span></span>|<span data-ttu-id="1d3cc-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d3cc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d3cc-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="1d3cc-121">InvokeMethod</span></span>|<span data-ttu-id="1d3cc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d3cc-122">xs:string</span></span>|<span data-ttu-id="1d3cc-123">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1d3cc-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="1d3cc-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="1d3cc-124">Exception</span></span>|<span data-ttu-id="1d3cc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d3cc-125">xs:string</span></span>|<span data-ttu-id="1d3cc-126">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="1d3cc-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="1d3cc-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1d3cc-127">AppDomain</span></span>|<span data-ttu-id="1d3cc-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d3cc-128">xs:string</span></span>|<span data-ttu-id="1d3cc-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d3cc-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
