---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511399"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="d7e4a-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="d7e4a-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="d7e4a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d7e4a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7e4a-104">ID</span><span class="sxs-lookup"><span data-stu-id="d7e4a-104">ID</span></span>|<span data-ttu-id="d7e4a-105">3503</span><span class="sxs-lookup"><span data-stu-id="d7e4a-105">3503</span></span>|  
|<span data-ttu-id="d7e4a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d7e4a-106">Keywords</span></span>|<span data-ttu-id="d7e4a-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d7e4a-107">WFServices</span></span>|  
|<span data-ttu-id="d7e4a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d7e4a-108">Level</span></span>|<span data-ttu-id="d7e4a-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="d7e4a-109">Warning</span></span>|  
|<span data-ttu-id="d7e4a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d7e4a-110">Channel</span></span>|<span data-ttu-id="d7e4a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d7e4a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d7e4a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7e4a-112">Description</span></span>  
 <span data-ttu-id="d7e4a-113">Gibt an, dass eine doppelte CorrelationQuery gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="d7e4a-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="d7e4a-114">Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7e4a-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d7e4a-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="d7e4a-115">Message</span></span>  
 <span data-ttu-id="d7e4a-116">Es wurde eine doppelte CorrelationQuery mit Where='%1' gefunden.</span><span class="sxs-lookup"><span data-stu-id="d7e4a-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="d7e4a-117">Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7e4a-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d7e4a-118">Details</span><span class="sxs-lookup"><span data-stu-id="d7e4a-118">Details</span></span>  
  
|<span data-ttu-id="d7e4a-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d7e4a-119">Data Item Name</span></span>|<span data-ttu-id="d7e4a-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d7e4a-120">Data Item Type</span></span>|<span data-ttu-id="d7e4a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7e4a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d7e4a-122">Where</span><span class="sxs-lookup"><span data-stu-id="d7e4a-122">Where</span></span>|<span data-ttu-id="d7e4a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7e4a-123">xs:string</span></span>|<span data-ttu-id="d7e4a-124">Where-Abschnitt der Korrelationsabfrage.</span><span class="sxs-lookup"><span data-stu-id="d7e4a-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="d7e4a-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d7e4a-125">AppDomain</span></span>|<span data-ttu-id="d7e4a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7e4a-126">xs:string</span></span>|<span data-ttu-id="d7e4a-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d7e4a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
