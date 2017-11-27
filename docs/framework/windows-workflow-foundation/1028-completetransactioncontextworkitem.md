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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77ef22bd29c167b5be26ceb5360397d38c547c22
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="3816b-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="3816b-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3816b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3816b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3816b-104">ID</span><span class="sxs-lookup"><span data-stu-id="3816b-104">ID</span></span>|<span data-ttu-id="3816b-105">1028</span><span class="sxs-lookup"><span data-stu-id="3816b-105">1028</span></span>|  
|<span data-ttu-id="3816b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3816b-106">Keywords</span></span>|<span data-ttu-id="3816b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3816b-107">WFRuntime</span></span>|  
|<span data-ttu-id="3816b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3816b-108">Level</span></span>|<span data-ttu-id="3816b-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="3816b-109">Verbose</span></span>|  
|<span data-ttu-id="3816b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3816b-110">Channel</span></span>|<span data-ttu-id="3816b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3816b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3816b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3816b-112">Description</span></span>  
 <span data-ttu-id="3816b-113">Gibt an, dass ein TransactionContextWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3816b-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3816b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3816b-114">Message</span></span>  
 <span data-ttu-id="3816b-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3816b-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3816b-116">Details</span><span class="sxs-lookup"><span data-stu-id="3816b-116">Details</span></span>  
  
|<span data-ttu-id="3816b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3816b-117">Data Item Name</span></span>|<span data-ttu-id="3816b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3816b-118">Data Item Type</span></span>|<span data-ttu-id="3816b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3816b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3816b-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="3816b-120">Activity</span></span>|<span data-ttu-id="3816b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3816b-121">xs:string</span></span>|<span data-ttu-id="3816b-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3816b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3816b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3816b-123">DisplayName</span></span>|<span data-ttu-id="3816b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3816b-124">xs:string</span></span>|<span data-ttu-id="3816b-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3816b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3816b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3816b-126">InstanceId</span></span>|<span data-ttu-id="3816b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3816b-127">xs:string</span></span>|<span data-ttu-id="3816b-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3816b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3816b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3816b-129">AppDomain</span></span>|<span data-ttu-id="3816b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3816b-130">xs:string</span></span>|<span data-ttu-id="3816b-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3816b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
