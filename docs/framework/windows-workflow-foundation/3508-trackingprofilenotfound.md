---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34812b6ddefb69c053cfefa91d7227a7bf15f42e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="008d7-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="008d7-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="008d7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="008d7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="008d7-104">ID</span><span class="sxs-lookup"><span data-stu-id="008d7-104">ID</span></span>|<span data-ttu-id="008d7-105">3508</span><span class="sxs-lookup"><span data-stu-id="008d7-105">3508</span></span>|  
|<span data-ttu-id="008d7-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="008d7-106">Keywords</span></span>|<span data-ttu-id="008d7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="008d7-107">WFServices</span></span>|  
|<span data-ttu-id="008d7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="008d7-108">Level</span></span>|<span data-ttu-id="008d7-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="008d7-109">Verbose</span></span>|  
|<span data-ttu-id="008d7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="008d7-110">Channel</span></span>|<span data-ttu-id="008d7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="008d7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="008d7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="008d7-112">Description</span></span>  
 <span data-ttu-id="008d7-113">Gibt an, dass entweder das TrackingProfile nicht in der Konfigurationsdatei gefunden wurde oder die ActivityDefinitionId nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="008d7-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="008d7-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="008d7-114">Message</span></span>  
 <span data-ttu-id="008d7-115">TrackingProfile '%1' für die ActivityDefinitionId '%2' wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="008d7-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="008d7-116">Entweder wurde das TrackingProfile nicht in der Konfigurationsdatei gefunden, oder die ActivityDefinitionId stimmt nicht überein.</span><span class="sxs-lookup"><span data-stu-id="008d7-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="008d7-117">Details</span><span class="sxs-lookup"><span data-stu-id="008d7-117">Details</span></span>  
  
|<span data-ttu-id="008d7-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="008d7-118">Data Item Name</span></span>|<span data-ttu-id="008d7-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="008d7-119">Data Item Type</span></span>|<span data-ttu-id="008d7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="008d7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="008d7-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="008d7-121">TrackingProfile</span></span>|<span data-ttu-id="008d7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="008d7-122">xs:string</span></span>|<span data-ttu-id="008d7-123">Der Name des Nachverfolgungsprofils.</span><span class="sxs-lookup"><span data-stu-id="008d7-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="008d7-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="008d7-124">ActivityDefinitionId</span></span>|<span data-ttu-id="008d7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="008d7-125">xs:string</span></span>|<span data-ttu-id="008d7-126">Die Aktivitätsdefinitions-ID.</span><span class="sxs-lookup"><span data-stu-id="008d7-126">The activity definition id.</span></span>|  
|<span data-ttu-id="008d7-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="008d7-127">AppDomain</span></span>|<span data-ttu-id="008d7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="008d7-128">xs:string</span></span>|<span data-ttu-id="008d7-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="008d7-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
