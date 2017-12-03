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
ms.openlocfilehash: a1021d7d23b8e9c25684da567b769c24380a8a0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="48497-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="48497-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="48497-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48497-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48497-104">ID</span><span class="sxs-lookup"><span data-stu-id="48497-104">ID</span></span>|<span data-ttu-id="48497-105">1126</span><span class="sxs-lookup"><span data-stu-id="48497-105">1126</span></span>|  
|<span data-ttu-id="48497-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48497-106">Keywords</span></span>|<span data-ttu-id="48497-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48497-107">WFRuntime</span></span>|  
|<span data-ttu-id="48497-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="48497-108">Level</span></span>|<span data-ttu-id="48497-109">Information</span><span class="sxs-lookup"><span data-stu-id="48497-109">Information</span></span>|  
|<span data-ttu-id="48497-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="48497-110">Channel</span></span>|<span data-ttu-id="48497-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48497-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48497-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48497-112">Description</span></span>  
 <span data-ttu-id="48497-113">Gibt an, dass von der Methode, die von der InvokeMethod-Aktivität aufgerufen wurde, eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="48497-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48497-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="48497-114">Message</span></span>  
 <span data-ttu-id="48497-115">In der von der Aktivität '%1' aufgerufenen Methode wurde eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="48497-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="48497-116">%2</span><span class="sxs-lookup"><span data-stu-id="48497-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="48497-117">Details</span><span class="sxs-lookup"><span data-stu-id="48497-117">Details</span></span>  
  
|<span data-ttu-id="48497-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="48497-118">Data Item Name</span></span>|<span data-ttu-id="48497-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="48497-119">Data Item Type</span></span>|<span data-ttu-id="48497-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48497-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48497-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="48497-121">InvokeMethod</span></span>|<span data-ttu-id="48497-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="48497-122">xs:string</span></span>|<span data-ttu-id="48497-123">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48497-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="48497-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="48497-124">Exception</span></span>|<span data-ttu-id="48497-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="48497-125">xs:string</span></span>|<span data-ttu-id="48497-126">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="48497-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="48497-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48497-127">AppDomain</span></span>|<span data-ttu-id="48497-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="48497-128">xs:string</span></span>|<span data-ttu-id="48497-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48497-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
