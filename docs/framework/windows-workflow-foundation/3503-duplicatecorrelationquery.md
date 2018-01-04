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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 997bdf4423364e9b5361635820849a6bde9e8960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="4ca64-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="4ca64-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="4ca64-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4ca64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ca64-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ca64-104">ID</span></span>|<span data-ttu-id="4ca64-105">3503</span><span class="sxs-lookup"><span data-stu-id="4ca64-105">3503</span></span>|  
|<span data-ttu-id="4ca64-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4ca64-106">Keywords</span></span>|<span data-ttu-id="4ca64-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4ca64-107">WFServices</span></span>|  
|<span data-ttu-id="4ca64-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4ca64-108">Level</span></span>|<span data-ttu-id="4ca64-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="4ca64-109">Warning</span></span>|  
|<span data-ttu-id="4ca64-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4ca64-110">Channel</span></span>|<span data-ttu-id="4ca64-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4ca64-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ca64-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ca64-112">Description</span></span>  
 <span data-ttu-id="4ca64-113">Gibt an, dass eine doppelte CorrelationQuery gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="4ca64-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="4ca64-114">Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ca64-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ca64-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="4ca64-115">Message</span></span>  
 <span data-ttu-id="4ca64-116">Es wurde eine doppelte CorrelationQuery mit Where='%1' gefunden.</span><span class="sxs-lookup"><span data-stu-id="4ca64-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="4ca64-117">Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ca64-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ca64-118">Details</span><span class="sxs-lookup"><span data-stu-id="4ca64-118">Details</span></span>  
  
|<span data-ttu-id="4ca64-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4ca64-119">Data Item Name</span></span>|<span data-ttu-id="4ca64-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4ca64-120">Data Item Type</span></span>|<span data-ttu-id="4ca64-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ca64-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ca64-122">Where</span><span class="sxs-lookup"><span data-stu-id="4ca64-122">Where</span></span>|<span data-ttu-id="4ca64-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ca64-123">xs:string</span></span>|<span data-ttu-id="4ca64-124">Where-Abschnitt der Korrelationsabfrage.</span><span class="sxs-lookup"><span data-stu-id="4ca64-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="4ca64-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4ca64-125">AppDomain</span></span>|<span data-ttu-id="4ca64-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ca64-126">xs:string</span></span>|<span data-ttu-id="4ca64-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4ca64-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
