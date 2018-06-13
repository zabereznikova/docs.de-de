---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512004"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="2adb0-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="2adb0-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="2adb0-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2adb0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2adb0-104">ID</span><span class="sxs-lookup"><span data-stu-id="2adb0-104">ID</span></span>|<span data-ttu-id="2adb0-105">3502</span><span class="sxs-lookup"><span data-stu-id="2adb0-105">3502</span></span>|  
|<span data-ttu-id="2adb0-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2adb0-106">Keywords</span></span>|<span data-ttu-id="2adb0-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="2adb0-107">WFServices</span></span>|  
|<span data-ttu-id="2adb0-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2adb0-108">Level</span></span>|<span data-ttu-id="2adb0-109">Information</span><span class="sxs-lookup"><span data-stu-id="2adb0-109">Information</span></span>|  
|<span data-ttu-id="2adb0-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2adb0-110">Channel</span></span>|<span data-ttu-id="2adb0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2adb0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2adb0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2adb0-112">Description</span></span>  
 <span data-ttu-id="2adb0-113">Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="2adb0-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2adb0-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="2adb0-114">Message</span></span>  
 <span data-ttu-id="2adb0-115">Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2adb0-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="2adb0-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="2adb0-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2adb0-117">Details</span><span class="sxs-lookup"><span data-stu-id="2adb0-117">Details</span></span>  
  
|<span data-ttu-id="2adb0-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2adb0-118">Data Item Name</span></span>|<span data-ttu-id="2adb0-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2adb0-119">Data Item Type</span></span>|<span data-ttu-id="2adb0-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2adb0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2adb0-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="2adb0-121">OperationName</span></span>|<span data-ttu-id="2adb0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2adb0-122">xs:string</span></span>|<span data-ttu-id="2adb0-123">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="2adb0-123">The name of the operation.</span></span>|  
|<span data-ttu-id="2adb0-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="2adb0-124">ContractName</span></span>|<span data-ttu-id="2adb0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2adb0-125">xs:string</span></span>|<span data-ttu-id="2adb0-126">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="2adb0-126">The name of the contract.</span></span>|  
|<span data-ttu-id="2adb0-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="2adb0-127">IsOneWay</span></span>|<span data-ttu-id="2adb0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2adb0-128">xs:string</span></span>|<span data-ttu-id="2adb0-129">True oder False gibt an, ob der Vertrag unidirektional ist.</span><span class="sxs-lookup"><span data-stu-id="2adb0-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="2adb0-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2adb0-130">AppDomain</span></span>|<span data-ttu-id="2adb0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2adb0-131">xs:string</span></span>|<span data-ttu-id="2adb0-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2adb0-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
