---
title: 1027 - StartTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa644cb7693b8608f119cf211b3b08ab4b1a2b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="312c1-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="312c1-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="312c1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="312c1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="312c1-104">ID</span><span class="sxs-lookup"><span data-stu-id="312c1-104">ID</span></span>|<span data-ttu-id="312c1-105">1027</span><span class="sxs-lookup"><span data-stu-id="312c1-105">1027</span></span>|  
|<span data-ttu-id="312c1-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="312c1-106">Keywords</span></span>|<span data-ttu-id="312c1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="312c1-107">WFRuntime</span></span>|  
|<span data-ttu-id="312c1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="312c1-108">Level</span></span>|<span data-ttu-id="312c1-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="312c1-109">Verbose</span></span>|  
|<span data-ttu-id="312c1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="312c1-110">Channel</span></span>|<span data-ttu-id="312c1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="312c1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="312c1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="312c1-112">Description</span></span>  
 <span data-ttu-id="312c1-113">Gibt an, dass ein TransactionContextWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="312c1-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="312c1-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="312c1-114">Message</span></span>  
 <span data-ttu-id="312c1-115">Die Ausführung von TransactionContextWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="312c1-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="312c1-116">Details</span><span class="sxs-lookup"><span data-stu-id="312c1-116">Details</span></span>  
  
|<span data-ttu-id="312c1-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="312c1-117">Data Item Name</span></span>|<span data-ttu-id="312c1-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="312c1-118">Data Item Type</span></span>|<span data-ttu-id="312c1-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="312c1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="312c1-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="312c1-120">Activity</span></span>|<span data-ttu-id="312c1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="312c1-121">xs:string</span></span>|<span data-ttu-id="312c1-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="312c1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="312c1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="312c1-123">DisplayName</span></span>|<span data-ttu-id="312c1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="312c1-124">xs:string</span></span>|<span data-ttu-id="312c1-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="312c1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="312c1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="312c1-126">InstanceId</span></span>|<span data-ttu-id="312c1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="312c1-127">xs:string</span></span>|<span data-ttu-id="312c1-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="312c1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="312c1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="312c1-129">AppDomain</span></span>|<span data-ttu-id="312c1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="312c1-130">xs:string</span></span>|<span data-ttu-id="312c1-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="312c1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
