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
ms.workload: dotnet
ms.openlocfilehash: 4d12549d201ac621361bd6a517df6c6b53ab7aec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="1e198-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="1e198-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="1e198-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1e198-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e198-104">ID</span><span class="sxs-lookup"><span data-stu-id="1e198-104">ID</span></span>|<span data-ttu-id="1e198-105">39458</span><span class="sxs-lookup"><span data-stu-id="1e198-105">39458</span></span>|  
|<span data-ttu-id="1e198-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1e198-106">Keywords</span></span>|<span data-ttu-id="1e198-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="1e198-107">WFTracking</span></span>|  
|<span data-ttu-id="1e198-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1e198-108">Level</span></span>|<span data-ttu-id="1e198-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="1e198-109">Warning</span></span>|  
|<span data-ttu-id="1e198-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1e198-110">Channel</span></span>|<span data-ttu-id="1e198-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1e198-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1e198-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e198-112">Description</span></span>  
 <span data-ttu-id="1e198-113">Gibt an, dass ein Nachverfolgungsdatensatz abgeschnitten wurde.</span><span class="sxs-lookup"><span data-stu-id="1e198-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="1e198-114">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e198-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1e198-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="1e198-115">Message</span></span>  
 <span data-ttu-id="1e198-116">Abgeschnittener Überwachungsdatensatz %1 wurde in die ETW-Sitzung mit Anbieter %2 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e198-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="1e198-117">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e198-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="1e198-118">Details</span><span class="sxs-lookup"><span data-stu-id="1e198-118">Details</span></span>  
  
|<span data-ttu-id="1e198-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1e198-119">Data Item Name</span></span>|<span data-ttu-id="1e198-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1e198-120">Data Item Type</span></span>|<span data-ttu-id="1e198-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e198-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1e198-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="1e198-122">RecordNumber</span></span>|<span data-ttu-id="1e198-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e198-123">xs:string</span></span>|<span data-ttu-id="1e198-124">Die Nummer des Nachverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="1e198-124">The tracking record number.</span></span>|  
|<span data-ttu-id="1e198-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="1e198-125">ProviderId</span></span>|<span data-ttu-id="1e198-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e198-126">xs:string</span></span>|<span data-ttu-id="1e198-127">Die ETW-Anbieter-ID.</span><span class="sxs-lookup"><span data-stu-id="1e198-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="1e198-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1e198-128">AppDomain</span></span>|<span data-ttu-id="1e198-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e198-129">xs:string</span></span>|<span data-ttu-id="1e198-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e198-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
