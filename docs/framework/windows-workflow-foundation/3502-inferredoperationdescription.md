---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242109"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="feac5-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="feac5-102">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="feac5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="feac5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="feac5-104">id</span><span class="sxs-lookup"><span data-stu-id="feac5-104">ID</span></span>|<span data-ttu-id="feac5-105">3502</span><span class="sxs-lookup"><span data-stu-id="feac5-105">3502</span></span>|  
|<span data-ttu-id="feac5-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="feac5-106">Keywords</span></span>|<span data-ttu-id="feac5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="feac5-107">WFServices</span></span>|  
|<span data-ttu-id="feac5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="feac5-108">Level</span></span>|<span data-ttu-id="feac5-109">Information</span><span class="sxs-lookup"><span data-stu-id="feac5-109">Information</span></span>|  
|<span data-ttu-id="feac5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="feac5-110">Channel</span></span>|<span data-ttu-id="feac5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="feac5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="feac5-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="feac5-112">Description</span></span>  

 <span data-ttu-id="feac5-113">Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="feac5-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="feac5-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="feac5-114">Message</span></span>  

 <span data-ttu-id="feac5-115">Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="feac5-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="feac5-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="feac5-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="feac5-117">Details</span><span class="sxs-lookup"><span data-stu-id="feac5-117">Details</span></span>  
  
|<span data-ttu-id="feac5-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="feac5-118">Data Item Name</span></span>|<span data-ttu-id="feac5-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="feac5-119">Data Item Type</span></span>|<span data-ttu-id="feac5-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="feac5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="feac5-121">Vorgangsname</span><span class="sxs-lookup"><span data-stu-id="feac5-121">OperationName</span></span>|<span data-ttu-id="feac5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="feac5-122">xs:string</span></span>|<span data-ttu-id="feac5-123">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="feac5-123">The name of the operation.</span></span>|  
|<span data-ttu-id="feac5-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="feac5-124">ContractName</span></span>|<span data-ttu-id="feac5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="feac5-125">xs:string</span></span>|<span data-ttu-id="feac5-126">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="feac5-126">The name of the contract.</span></span>|  
|<span data-ttu-id="feac5-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="feac5-127">IsOneWay</span></span>|<span data-ttu-id="feac5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="feac5-128">xs:string</span></span>|<span data-ttu-id="feac5-129">True oder False gibt an, ob der Vertrag unidirektional ist.</span><span class="sxs-lookup"><span data-stu-id="feac5-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="feac5-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="feac5-130">AppDomain</span></span>|<span data-ttu-id="feac5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="feac5-131">xs:string</span></span>|<span data-ttu-id="feac5-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="feac5-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
