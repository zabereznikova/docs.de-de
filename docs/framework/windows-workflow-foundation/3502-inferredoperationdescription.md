---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2c2464cd8c6f0c16946847a5503270453d5b019
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="c814e-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="c814e-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="c814e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c814e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c814e-104">ID</span><span class="sxs-lookup"><span data-stu-id="c814e-104">ID</span></span>|<span data-ttu-id="c814e-105">3502</span><span class="sxs-lookup"><span data-stu-id="c814e-105">3502</span></span>|  
|<span data-ttu-id="c814e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c814e-106">Keywords</span></span>|<span data-ttu-id="c814e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="c814e-107">WFServices</span></span>|  
|<span data-ttu-id="c814e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="c814e-108">Level</span></span>|<span data-ttu-id="c814e-109">Information</span><span class="sxs-lookup"><span data-stu-id="c814e-109">Information</span></span>|  
|<span data-ttu-id="c814e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="c814e-110">Channel</span></span>|<span data-ttu-id="c814e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c814e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c814e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c814e-112">Description</span></span>  
 <span data-ttu-id="c814e-113">Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="c814e-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c814e-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="c814e-114">Message</span></span>  
 <span data-ttu-id="c814e-115">Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c814e-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="c814e-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="c814e-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c814e-117">Details</span><span class="sxs-lookup"><span data-stu-id="c814e-117">Details</span></span>  
  
|<span data-ttu-id="c814e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="c814e-118">Data Item Name</span></span>|<span data-ttu-id="c814e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="c814e-119">Data Item Type</span></span>|<span data-ttu-id="c814e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c814e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c814e-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="c814e-121">OperationName</span></span>|<span data-ttu-id="c814e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c814e-122">xs:string</span></span>|<span data-ttu-id="c814e-123">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="c814e-123">The name of the operation.</span></span>|  
|<span data-ttu-id="c814e-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="c814e-124">ContractName</span></span>|<span data-ttu-id="c814e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c814e-125">xs:string</span></span>|<span data-ttu-id="c814e-126">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="c814e-126">The name of the contract.</span></span>|  
|<span data-ttu-id="c814e-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="c814e-127">IsOneWay</span></span>|<span data-ttu-id="c814e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c814e-128">xs:string</span></span>|<span data-ttu-id="c814e-129">True oder False gibt an, ob der Vertrag unidirektional ist.</span><span class="sxs-lookup"><span data-stu-id="c814e-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="c814e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c814e-130">AppDomain</span></span>|<span data-ttu-id="c814e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c814e-131">xs:string</span></span>|<span data-ttu-id="c814e-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c814e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
