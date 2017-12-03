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
ms.openlocfilehash: 144ab1a4a2fd313dc7817846e3e0118145cd3f8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="05b8b-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="05b8b-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="05b8b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="05b8b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05b8b-104">ID</span><span class="sxs-lookup"><span data-stu-id="05b8b-104">ID</span></span>|<span data-ttu-id="05b8b-105">3502</span><span class="sxs-lookup"><span data-stu-id="05b8b-105">3502</span></span>|  
|<span data-ttu-id="05b8b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="05b8b-106">Keywords</span></span>|<span data-ttu-id="05b8b-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="05b8b-107">WFServices</span></span>|  
|<span data-ttu-id="05b8b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="05b8b-108">Level</span></span>|<span data-ttu-id="05b8b-109">Information</span><span class="sxs-lookup"><span data-stu-id="05b8b-109">Information</span></span>|  
|<span data-ttu-id="05b8b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="05b8b-110">Channel</span></span>|<span data-ttu-id="05b8b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="05b8b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="05b8b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05b8b-112">Description</span></span>  
 <span data-ttu-id="05b8b-113">Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="05b8b-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="05b8b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="05b8b-114">Message</span></span>  
 <span data-ttu-id="05b8b-115">Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="05b8b-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="05b8b-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="05b8b-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="05b8b-117">Details</span><span class="sxs-lookup"><span data-stu-id="05b8b-117">Details</span></span>  
  
|<span data-ttu-id="05b8b-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="05b8b-118">Data Item Name</span></span>|<span data-ttu-id="05b8b-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="05b8b-119">Data Item Type</span></span>|<span data-ttu-id="05b8b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05b8b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="05b8b-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="05b8b-121">OperationName</span></span>|<span data-ttu-id="05b8b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="05b8b-122">xs:string</span></span>|<span data-ttu-id="05b8b-123">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="05b8b-123">The name of the operation.</span></span>|  
|<span data-ttu-id="05b8b-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="05b8b-124">ContractName</span></span>|<span data-ttu-id="05b8b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="05b8b-125">xs:string</span></span>|<span data-ttu-id="05b8b-126">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="05b8b-126">The name of the contract.</span></span>|  
|<span data-ttu-id="05b8b-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="05b8b-127">IsOneWay</span></span>|<span data-ttu-id="05b8b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="05b8b-128">xs:string</span></span>|<span data-ttu-id="05b8b-129">True oder False gibt an, ob der Vertrag unidirektional ist.</span><span class="sxs-lookup"><span data-stu-id="05b8b-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="05b8b-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="05b8b-130">AppDomain</span></span>|<span data-ttu-id="05b8b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="05b8b-131">xs:string</span></span>|<span data-ttu-id="05b8b-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="05b8b-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
