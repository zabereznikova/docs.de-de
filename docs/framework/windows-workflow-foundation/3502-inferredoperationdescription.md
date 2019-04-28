---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756090"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="18f2c-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="18f2c-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="18f2c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="18f2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18f2c-104">ID</span><span class="sxs-lookup"><span data-stu-id="18f2c-104">ID</span></span>|<span data-ttu-id="18f2c-105">3502</span><span class="sxs-lookup"><span data-stu-id="18f2c-105">3502</span></span>|  
|<span data-ttu-id="18f2c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="18f2c-106">Keywords</span></span>|<span data-ttu-id="18f2c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="18f2c-107">WFServices</span></span>|  
|<span data-ttu-id="18f2c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="18f2c-108">Level</span></span>|<span data-ttu-id="18f2c-109">Information</span><span class="sxs-lookup"><span data-stu-id="18f2c-109">Information</span></span>|  
|<span data-ttu-id="18f2c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="18f2c-110">Channel</span></span>|<span data-ttu-id="18f2c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="18f2c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="18f2c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18f2c-112">Description</span></span>  
 <span data-ttu-id="18f2c-113">Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="18f2c-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="18f2c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="18f2c-114">Message</span></span>  
 <span data-ttu-id="18f2c-115">Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="18f2c-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="18f2c-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="18f2c-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="18f2c-117">Details</span><span class="sxs-lookup"><span data-stu-id="18f2c-117">Details</span></span>  
  
|<span data-ttu-id="18f2c-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="18f2c-118">Data Item Name</span></span>|<span data-ttu-id="18f2c-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="18f2c-119">Data Item Type</span></span>|<span data-ttu-id="18f2c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18f2c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="18f2c-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="18f2c-121">OperationName</span></span>|<span data-ttu-id="18f2c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="18f2c-122">xs:string</span></span>|<span data-ttu-id="18f2c-123">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="18f2c-123">The name of the operation.</span></span>|  
|<span data-ttu-id="18f2c-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="18f2c-124">ContractName</span></span>|<span data-ttu-id="18f2c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="18f2c-125">xs:string</span></span>|<span data-ttu-id="18f2c-126">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="18f2c-126">The name of the contract.</span></span>|  
|<span data-ttu-id="18f2c-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="18f2c-127">IsOneWay</span></span>|<span data-ttu-id="18f2c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="18f2c-128">xs:string</span></span>|<span data-ttu-id="18f2c-129">True oder False gibt an, ob der Vertrag unidirektional ist.</span><span class="sxs-lookup"><span data-stu-id="18f2c-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="18f2c-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="18f2c-130">AppDomain</span></span>|<span data-ttu-id="18f2c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="18f2c-131">xs:string</span></span>|<span data-ttu-id="18f2c-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="18f2c-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
