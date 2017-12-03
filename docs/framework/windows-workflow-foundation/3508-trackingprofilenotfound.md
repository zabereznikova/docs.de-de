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
ms.openlocfilehash: 346cb98b1285883a9a85f2c7abb6147f42734395
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="eeb40-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="eeb40-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="eeb40-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eeb40-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eeb40-104">ID</span><span class="sxs-lookup"><span data-stu-id="eeb40-104">ID</span></span>|<span data-ttu-id="eeb40-105">3508</span><span class="sxs-lookup"><span data-stu-id="eeb40-105">3508</span></span>|  
|<span data-ttu-id="eeb40-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="eeb40-106">Keywords</span></span>|<span data-ttu-id="eeb40-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="eeb40-107">WFServices</span></span>|  
|<span data-ttu-id="eeb40-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="eeb40-108">Level</span></span>|<span data-ttu-id="eeb40-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="eeb40-109">Verbose</span></span>|  
|<span data-ttu-id="eeb40-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="eeb40-110">Channel</span></span>|<span data-ttu-id="eeb40-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="eeb40-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eeb40-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eeb40-112">Description</span></span>  
 <span data-ttu-id="eeb40-113">Gibt an, dass entweder das TrackingProfile nicht in der Konfigurationsdatei gefunden wurde oder die ActivityDefinitionId nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="eeb40-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eeb40-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="eeb40-114">Message</span></span>  
 <span data-ttu-id="eeb40-115">TrackingProfile '%1' für die ActivityDefinitionId '%2' wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="eeb40-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="eeb40-116">Entweder wurde das TrackingProfile nicht in der Konfigurationsdatei gefunden, oder die ActivityDefinitionId stimmt nicht überein.</span><span class="sxs-lookup"><span data-stu-id="eeb40-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eeb40-117">Details</span><span class="sxs-lookup"><span data-stu-id="eeb40-117">Details</span></span>  
  
|<span data-ttu-id="eeb40-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="eeb40-118">Data Item Name</span></span>|<span data-ttu-id="eeb40-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="eeb40-119">Data Item Type</span></span>|<span data-ttu-id="eeb40-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eeb40-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eeb40-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="eeb40-121">TrackingProfile</span></span>|<span data-ttu-id="eeb40-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="eeb40-122">xs:string</span></span>|<span data-ttu-id="eeb40-123">Der Name des Nachverfolgungsprofils.</span><span class="sxs-lookup"><span data-stu-id="eeb40-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="eeb40-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="eeb40-124">ActivityDefinitionId</span></span>|<span data-ttu-id="eeb40-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="eeb40-125">xs:string</span></span>|<span data-ttu-id="eeb40-126">Die Aktivitätsdefinitions-ID.</span><span class="sxs-lookup"><span data-stu-id="eeb40-126">The activity definition id.</span></span>|  
|<span data-ttu-id="eeb40-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eeb40-127">AppDomain</span></span>|<span data-ttu-id="eeb40-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="eeb40-128">xs:string</span></span>|<span data-ttu-id="eeb40-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eeb40-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
