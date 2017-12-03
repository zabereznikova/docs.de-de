---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de056ffcdfeb3ea5dee9eaca213fe96ee991d067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="7ac2f-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="7ac2f-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="7ac2f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7ac2f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ac2f-104">ID</span><span class="sxs-lookup"><span data-stu-id="7ac2f-104">ID</span></span>|<span data-ttu-id="7ac2f-105">39456</span><span class="sxs-lookup"><span data-stu-id="7ac2f-105">39456</span></span>|  
|<span data-ttu-id="7ac2f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7ac2f-106">Keywords</span></span>|<span data-ttu-id="7ac2f-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="7ac2f-107">WFTracking</span></span>|  
|<span data-ttu-id="7ac2f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7ac2f-108">Level</span></span>|<span data-ttu-id="7ac2f-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="7ac2f-109">Warning</span></span>|  
|<span data-ttu-id="7ac2f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7ac2f-110">Channel</span></span>|<span data-ttu-id="7ac2f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7ac2f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7ac2f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ac2f-112">Description</span></span>  
 <span data-ttu-id="7ac2f-113">Gibt an, dass ein Nachverfolgungsdatensatz gelöscht wurde, weil sein Größe den maximal zulässigen Wert des ETW-Sitzungsanbieters überschreitet.</span><span class="sxs-lookup"><span data-stu-id="7ac2f-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7ac2f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="7ac2f-114">Message</span></span>  
 <span data-ttu-id="7ac2f-115">Die Größe des Überwachungsdatensatzes %1 überschreitet das zulässige Maximum der ETW-Sitzung für den Anbieter %2.</span><span class="sxs-lookup"><span data-stu-id="7ac2f-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="7ac2f-116">Details</span><span class="sxs-lookup"><span data-stu-id="7ac2f-116">Details</span></span>  
  
|<span data-ttu-id="7ac2f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7ac2f-117">Data Item Name</span></span>|<span data-ttu-id="7ac2f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7ac2f-118">Data Item Type</span></span>|<span data-ttu-id="7ac2f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ac2f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7ac2f-120">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="7ac2f-120">Exception</span></span>|<span data-ttu-id="7ac2f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ac2f-121">xs:string</span></span>|<span data-ttu-id="7ac2f-122">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="7ac2f-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="7ac2f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7ac2f-123">AppDomain</span></span>|<span data-ttu-id="7ac2f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ac2f-124">xs:string</span></span>|<span data-ttu-id="7ac2f-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7ac2f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
