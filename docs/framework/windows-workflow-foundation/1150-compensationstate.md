---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923863"
---
# <a name="1150---compensationstate"></a><span data-ttu-id="3f30b-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="3f30b-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="3f30b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3f30b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f30b-104">ID</span><span class="sxs-lookup"><span data-stu-id="3f30b-104">ID</span></span>|<span data-ttu-id="3f30b-105">1150</span><span class="sxs-lookup"><span data-stu-id="3f30b-105">1150</span></span>|  
|<span data-ttu-id="3f30b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3f30b-106">Keywords</span></span>|<span data-ttu-id="3f30b-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="3f30b-107">WFActivities</span></span>|  
|<span data-ttu-id="3f30b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3f30b-108">Level</span></span>|<span data-ttu-id="3f30b-109">Information</span><span class="sxs-lookup"><span data-stu-id="3f30b-109">Information</span></span>|  
|<span data-ttu-id="3f30b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3f30b-110">Channel</span></span>|<span data-ttu-id="3f30b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3f30b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3f30b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f30b-112">Description</span></span>  
 <span data-ttu-id="3f30b-113">Gibt eine Statusänderung in einer CompensableActivity an.</span><span class="sxs-lookup"><span data-stu-id="3f30b-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3f30b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3f30b-114">Message</span></span>  
 <span data-ttu-id="3f30b-115">CompensableActivity '%1' hat den Status '%2'.</span><span class="sxs-lookup"><span data-stu-id="3f30b-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3f30b-116">Details</span><span class="sxs-lookup"><span data-stu-id="3f30b-116">Details</span></span>  
  
|<span data-ttu-id="3f30b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3f30b-117">Data Item Name</span></span>|<span data-ttu-id="3f30b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3f30b-118">Data Item Type</span></span>|<span data-ttu-id="3f30b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f30b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3f30b-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3f30b-120">DisplayName</span></span>|<span data-ttu-id="3f30b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f30b-121">xs:string</span></span>|<span data-ttu-id="3f30b-122">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3f30b-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="3f30b-123">Zustand</span><span class="sxs-lookup"><span data-stu-id="3f30b-123">State</span></span>|<span data-ttu-id="3f30b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f30b-124">xs:string</span></span>|<span data-ttu-id="3f30b-125">Der Kompensationsstatus.</span><span class="sxs-lookup"><span data-stu-id="3f30b-125">The compensation state.</span></span>|  
|<span data-ttu-id="3f30b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3f30b-126">AppDomain</span></span>|<span data-ttu-id="3f30b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f30b-127">xs:string</span></span>|<span data-ttu-id="3f30b-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3f30b-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
