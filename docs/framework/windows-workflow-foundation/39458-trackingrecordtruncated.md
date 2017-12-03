---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="f83ae-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="f83ae-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="f83ae-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f83ae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f83ae-104">ID</span><span class="sxs-lookup"><span data-stu-id="f83ae-104">ID</span></span>|<span data-ttu-id="f83ae-105">39458</span><span class="sxs-lookup"><span data-stu-id="f83ae-105">39458</span></span>|  
|<span data-ttu-id="f83ae-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f83ae-106">Keywords</span></span>|<span data-ttu-id="f83ae-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="f83ae-107">WFTracking</span></span>|  
|<span data-ttu-id="f83ae-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f83ae-108">Level</span></span>|<span data-ttu-id="f83ae-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="f83ae-109">Warning</span></span>|  
|<span data-ttu-id="f83ae-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f83ae-110">Channel</span></span>|<span data-ttu-id="f83ae-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f83ae-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f83ae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f83ae-112">Description</span></span>  
 <span data-ttu-id="f83ae-113">Gibt an, dass ein Nachverfolgungsdatensatz abgeschnitten wurde.</span><span class="sxs-lookup"><span data-stu-id="f83ae-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="f83ae-114">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="f83ae-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f83ae-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="f83ae-115">Message</span></span>  
 <span data-ttu-id="f83ae-116">Abgeschnittener Überwachungsdatensatz %1 wurde in die ETW-Sitzung mit Anbieter %2 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f83ae-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="f83ae-117">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="f83ae-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="f83ae-118">Details</span><span class="sxs-lookup"><span data-stu-id="f83ae-118">Details</span></span>  
  
|<span data-ttu-id="f83ae-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f83ae-119">Data Item Name</span></span>|<span data-ttu-id="f83ae-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f83ae-120">Data Item Type</span></span>|<span data-ttu-id="f83ae-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f83ae-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f83ae-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="f83ae-122">RecordNumber</span></span>|<span data-ttu-id="f83ae-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f83ae-123">xs:string</span></span>|<span data-ttu-id="f83ae-124">Die Nummer des Nachverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="f83ae-124">The tracking record number.</span></span>|  
|<span data-ttu-id="f83ae-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="f83ae-125">ProviderId</span></span>|<span data-ttu-id="f83ae-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f83ae-126">xs:string</span></span>|<span data-ttu-id="f83ae-127">Die ETW-Anbieter-ID.</span><span class="sxs-lookup"><span data-stu-id="f83ae-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="f83ae-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f83ae-128">AppDomain</span></span>|<span data-ttu-id="f83ae-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f83ae-129">xs:string</span></span>|<span data-ttu-id="f83ae-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f83ae-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
