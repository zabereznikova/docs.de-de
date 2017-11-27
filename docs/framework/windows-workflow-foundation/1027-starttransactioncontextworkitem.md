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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be35a4d478f4f2af0921cac942ebb95d6aed38d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="a5803-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="a5803-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a5803-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a5803-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5803-104">ID</span><span class="sxs-lookup"><span data-stu-id="a5803-104">ID</span></span>|<span data-ttu-id="a5803-105">1027</span><span class="sxs-lookup"><span data-stu-id="a5803-105">1027</span></span>|  
|<span data-ttu-id="a5803-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a5803-106">Keywords</span></span>|<span data-ttu-id="a5803-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a5803-107">WFRuntime</span></span>|  
|<span data-ttu-id="a5803-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a5803-108">Level</span></span>|<span data-ttu-id="a5803-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="a5803-109">Verbose</span></span>|  
|<span data-ttu-id="a5803-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a5803-110">Channel</span></span>|<span data-ttu-id="a5803-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a5803-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a5803-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5803-112">Description</span></span>  
 <span data-ttu-id="a5803-113">Gibt an, dass ein TransactionContextWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="a5803-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a5803-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a5803-114">Message</span></span>  
 <span data-ttu-id="a5803-115">Die Ausführung von TransactionContextWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="a5803-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a5803-116">Details</span><span class="sxs-lookup"><span data-stu-id="a5803-116">Details</span></span>  
  
|<span data-ttu-id="a5803-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a5803-117">Data Item Name</span></span>|<span data-ttu-id="a5803-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a5803-118">Data Item Type</span></span>|<span data-ttu-id="a5803-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5803-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a5803-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="a5803-120">Activity</span></span>|<span data-ttu-id="a5803-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5803-121">xs:string</span></span>|<span data-ttu-id="a5803-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a5803-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a5803-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a5803-123">DisplayName</span></span>|<span data-ttu-id="a5803-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5803-124">xs:string</span></span>|<span data-ttu-id="a5803-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a5803-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a5803-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a5803-126">InstanceId</span></span>|<span data-ttu-id="a5803-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5803-127">xs:string</span></span>|<span data-ttu-id="a5803-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a5803-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a5803-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a5803-129">AppDomain</span></span>|<span data-ttu-id="a5803-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5803-130">xs:string</span></span>|<span data-ttu-id="a5803-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a5803-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
