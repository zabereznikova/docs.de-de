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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 044d67bc2b721451ade04947484899266d288d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="4e0af-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="4e0af-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="4e0af-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4e0af-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e0af-104">ID</span><span class="sxs-lookup"><span data-stu-id="4e0af-104">ID</span></span>|<span data-ttu-id="4e0af-105">3502</span><span class="sxs-lookup"><span data-stu-id="4e0af-105">3502</span></span>|  
|<span data-ttu-id="4e0af-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4e0af-106">Keywords</span></span>|<span data-ttu-id="4e0af-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4e0af-107">WFServices</span></span>|  
|<span data-ttu-id="4e0af-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4e0af-108">Level</span></span>|<span data-ttu-id="4e0af-109">Information</span><span class="sxs-lookup"><span data-stu-id="4e0af-109">Information</span></span>|  
|<span data-ttu-id="4e0af-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4e0af-110">Channel</span></span>|<span data-ttu-id="4e0af-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4e0af-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4e0af-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e0af-112">Description</span></span>  
 <span data-ttu-id="4e0af-113">Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="4e0af-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4e0af-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4e0af-114">Message</span></span>  
 <span data-ttu-id="4e0af-115">Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e0af-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="4e0af-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="4e0af-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4e0af-117">Details</span><span class="sxs-lookup"><span data-stu-id="4e0af-117">Details</span></span>  
  
|<span data-ttu-id="4e0af-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4e0af-118">Data Item Name</span></span>|<span data-ttu-id="4e0af-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4e0af-119">Data Item Type</span></span>|<span data-ttu-id="4e0af-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e0af-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4e0af-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="4e0af-121">OperationName</span></span>|<span data-ttu-id="4e0af-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e0af-122">xs:string</span></span>|<span data-ttu-id="4e0af-123">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="4e0af-123">The name of the operation.</span></span>|  
|<span data-ttu-id="4e0af-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="4e0af-124">ContractName</span></span>|<span data-ttu-id="4e0af-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e0af-125">xs:string</span></span>|<span data-ttu-id="4e0af-126">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="4e0af-126">The name of the contract.</span></span>|  
|<span data-ttu-id="4e0af-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="4e0af-127">IsOneWay</span></span>|<span data-ttu-id="4e0af-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e0af-128">xs:string</span></span>|<span data-ttu-id="4e0af-129">True oder False gibt an, ob der Vertrag unidirektional ist.</span><span class="sxs-lookup"><span data-stu-id="4e0af-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="4e0af-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4e0af-130">AppDomain</span></span>|<span data-ttu-id="4e0af-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e0af-131">xs:string</span></span>|<span data-ttu-id="4e0af-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4e0af-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
