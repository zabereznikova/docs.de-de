---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 23262427c3da730eaf930a8b483c7c4d4ec3a3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289840"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="56daa-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="56daa-102">3508 - TrackingProfileNotFound</span></span>

## <a name="properties"></a><span data-ttu-id="56daa-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="56daa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56daa-104">id</span><span class="sxs-lookup"><span data-stu-id="56daa-104">ID</span></span>|<span data-ttu-id="56daa-105">3508</span><span class="sxs-lookup"><span data-stu-id="56daa-105">3508</span></span>|  
|<span data-ttu-id="56daa-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="56daa-106">Keywords</span></span>|<span data-ttu-id="56daa-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="56daa-107">WFServices</span></span>|  
|<span data-ttu-id="56daa-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="56daa-108">Level</span></span>|<span data-ttu-id="56daa-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="56daa-109">Verbose</span></span>|  
|<span data-ttu-id="56daa-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="56daa-110">Channel</span></span>|<span data-ttu-id="56daa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="56daa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56daa-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56daa-112">Description</span></span>  

 <span data-ttu-id="56daa-113">Gibt an, dass entweder das TrackingProfile nicht in der Konfigurationsdatei gefunden wurde oder die ActivityDefinitionId nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="56daa-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56daa-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="56daa-114">Message</span></span>  

 <span data-ttu-id="56daa-115">TrackingProfile '%1' für die ActivityDefinitionId '%2' wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="56daa-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="56daa-116">Entweder wurde das TrackingProfile nicht in der Konfigurationsdatei gefunden, oder die ActivityDefinitionId stimmt nicht überein.</span><span class="sxs-lookup"><span data-stu-id="56daa-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56daa-117">Details</span><span class="sxs-lookup"><span data-stu-id="56daa-117">Details</span></span>  
  
|<span data-ttu-id="56daa-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="56daa-118">Data Item Name</span></span>|<span data-ttu-id="56daa-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="56daa-119">Data Item Type</span></span>|<span data-ttu-id="56daa-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56daa-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56daa-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="56daa-121">TrackingProfile</span></span>|<span data-ttu-id="56daa-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="56daa-122">xs:string</span></span>|<span data-ttu-id="56daa-123">Der Name des Nachverfolgungsprofils.</span><span class="sxs-lookup"><span data-stu-id="56daa-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="56daa-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="56daa-124">ActivityDefinitionId</span></span>|<span data-ttu-id="56daa-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="56daa-125">xs:string</span></span>|<span data-ttu-id="56daa-126">Die Aktivitätsdefinitions-ID.</span><span class="sxs-lookup"><span data-stu-id="56daa-126">The activity definition id.</span></span>|  
|<span data-ttu-id="56daa-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56daa-127">AppDomain</span></span>|<span data-ttu-id="56daa-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="56daa-128">xs:string</span></span>|<span data-ttu-id="56daa-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="56daa-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
