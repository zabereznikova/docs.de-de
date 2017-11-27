---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60367b33e1e57cce8646b4fcde79c7d4fd20a4cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="32033-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="32033-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="32033-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="32033-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32033-104">ID</span><span class="sxs-lookup"><span data-stu-id="32033-104">ID</span></span>|<span data-ttu-id="32033-105">3503</span><span class="sxs-lookup"><span data-stu-id="32033-105">3503</span></span>|  
|<span data-ttu-id="32033-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="32033-106">Keywords</span></span>|<span data-ttu-id="32033-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="32033-107">WFServices</span></span>|  
|<span data-ttu-id="32033-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="32033-108">Level</span></span>|<span data-ttu-id="32033-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="32033-109">Warning</span></span>|  
|<span data-ttu-id="32033-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="32033-110">Channel</span></span>|<span data-ttu-id="32033-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="32033-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32033-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32033-112">Description</span></span>  
 <span data-ttu-id="32033-113">Gibt an, dass eine doppelte CorrelationQuery gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="32033-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="32033-114">Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="32033-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32033-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="32033-115">Message</span></span>  
 <span data-ttu-id="32033-116">Es wurde eine doppelte CorrelationQuery mit Where='%1' gefunden.</span><span class="sxs-lookup"><span data-stu-id="32033-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="32033-117">Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="32033-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="32033-118">Details</span><span class="sxs-lookup"><span data-stu-id="32033-118">Details</span></span>  
  
|<span data-ttu-id="32033-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="32033-119">Data Item Name</span></span>|<span data-ttu-id="32033-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="32033-120">Data Item Type</span></span>|<span data-ttu-id="32033-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32033-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32033-122">Where</span><span class="sxs-lookup"><span data-stu-id="32033-122">Where</span></span>|<span data-ttu-id="32033-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="32033-123">xs:string</span></span>|<span data-ttu-id="32033-124">Where-Abschnitt der Korrelationsabfrage.</span><span class="sxs-lookup"><span data-stu-id="32033-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="32033-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="32033-125">AppDomain</span></span>|<span data-ttu-id="32033-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="32033-126">xs:string</span></span>|<span data-ttu-id="32033-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="32033-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
