---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270327"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="ce054-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="ce054-102">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="ce054-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ce054-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce054-104">id</span><span class="sxs-lookup"><span data-stu-id="ce054-104">ID</span></span>|<span data-ttu-id="ce054-105">3503</span><span class="sxs-lookup"><span data-stu-id="ce054-105">3503</span></span>|  
|<span data-ttu-id="ce054-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ce054-106">Keywords</span></span>|<span data-ttu-id="ce054-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ce054-107">WFServices</span></span>|  
|<span data-ttu-id="ce054-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ce054-108">Level</span></span>|<span data-ttu-id="ce054-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="ce054-109">Warning</span></span>|  
|<span data-ttu-id="ce054-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ce054-110">Channel</span></span>|<span data-ttu-id="ce054-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ce054-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ce054-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce054-112">Description</span></span>  

 <span data-ttu-id="ce054-113">Gibt an, dass eine doppelte CorrelationQuery gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="ce054-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="ce054-114">Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce054-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ce054-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="ce054-115">Message</span></span>  

 <span data-ttu-id="ce054-116">Es wurde eine doppelte CorrelationQuery mit Where='%1' gefunden.</span><span class="sxs-lookup"><span data-stu-id="ce054-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="ce054-117">Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce054-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ce054-118">Details</span><span class="sxs-lookup"><span data-stu-id="ce054-118">Details</span></span>  
  
|<span data-ttu-id="ce054-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ce054-119">Data Item Name</span></span>|<span data-ttu-id="ce054-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ce054-120">Data Item Type</span></span>|<span data-ttu-id="ce054-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce054-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ce054-122">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="ce054-122">Where</span></span>|<span data-ttu-id="ce054-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce054-123">xs:string</span></span>|<span data-ttu-id="ce054-124">Where-Abschnitt der Korrelationsabfrage.</span><span class="sxs-lookup"><span data-stu-id="ce054-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="ce054-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ce054-125">AppDomain</span></span>|<span data-ttu-id="ce054-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce054-126">xs:string</span></span>|<span data-ttu-id="ce054-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ce054-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
