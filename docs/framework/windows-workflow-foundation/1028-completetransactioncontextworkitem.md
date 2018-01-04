---
title: 1028 - CompleteTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cd2ee443d6c521f168a170a1079eb4e9657e2dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="747a5-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="747a5-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="747a5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="747a5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="747a5-104">ID</span><span class="sxs-lookup"><span data-stu-id="747a5-104">ID</span></span>|<span data-ttu-id="747a5-105">1028</span><span class="sxs-lookup"><span data-stu-id="747a5-105">1028</span></span>|  
|<span data-ttu-id="747a5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="747a5-106">Keywords</span></span>|<span data-ttu-id="747a5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="747a5-107">WFRuntime</span></span>|  
|<span data-ttu-id="747a5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="747a5-108">Level</span></span>|<span data-ttu-id="747a5-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="747a5-109">Verbose</span></span>|  
|<span data-ttu-id="747a5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="747a5-110">Channel</span></span>|<span data-ttu-id="747a5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="747a5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="747a5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="747a5-112">Description</span></span>  
 <span data-ttu-id="747a5-113">Gibt an, dass ein TransactionContextWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="747a5-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="747a5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="747a5-114">Message</span></span>  
 <span data-ttu-id="747a5-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="747a5-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="747a5-116">Details</span><span class="sxs-lookup"><span data-stu-id="747a5-116">Details</span></span>  
  
|<span data-ttu-id="747a5-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="747a5-117">Data Item Name</span></span>|<span data-ttu-id="747a5-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="747a5-118">Data Item Type</span></span>|<span data-ttu-id="747a5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="747a5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="747a5-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="747a5-120">Activity</span></span>|<span data-ttu-id="747a5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="747a5-121">xs:string</span></span>|<span data-ttu-id="747a5-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="747a5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="747a5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="747a5-123">DisplayName</span></span>|<span data-ttu-id="747a5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="747a5-124">xs:string</span></span>|<span data-ttu-id="747a5-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="747a5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="747a5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="747a5-126">InstanceId</span></span>|<span data-ttu-id="747a5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="747a5-127">xs:string</span></span>|<span data-ttu-id="747a5-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="747a5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="747a5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="747a5-129">AppDomain</span></span>|<span data-ttu-id="747a5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="747a5-130">xs:string</span></span>|<span data-ttu-id="747a5-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="747a5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
