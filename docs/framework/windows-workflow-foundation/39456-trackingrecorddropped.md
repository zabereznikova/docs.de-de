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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3e663cced42252112e1948f4907bc8c81ef941f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="50b59-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="50b59-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="50b59-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="50b59-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50b59-104">ID</span><span class="sxs-lookup"><span data-stu-id="50b59-104">ID</span></span>|<span data-ttu-id="50b59-105">39456</span><span class="sxs-lookup"><span data-stu-id="50b59-105">39456</span></span>|  
|<span data-ttu-id="50b59-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="50b59-106">Keywords</span></span>|<span data-ttu-id="50b59-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="50b59-107">WFTracking</span></span>|  
|<span data-ttu-id="50b59-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="50b59-108">Level</span></span>|<span data-ttu-id="50b59-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="50b59-109">Warning</span></span>|  
|<span data-ttu-id="50b59-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="50b59-110">Channel</span></span>|<span data-ttu-id="50b59-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="50b59-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50b59-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50b59-112">Description</span></span>  
 <span data-ttu-id="50b59-113">Gibt an, dass ein Nachverfolgungsdatensatz gelöscht wurde, weil sein Größe den maximal zulässigen Wert des ETW-Sitzungsanbieters überschreitet.</span><span class="sxs-lookup"><span data-stu-id="50b59-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="50b59-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="50b59-114">Message</span></span>  
 <span data-ttu-id="50b59-115">Die Größe des Überwachungsdatensatzes %1 überschreitet das zulässige Maximum der ETW-Sitzung für den Anbieter %2.</span><span class="sxs-lookup"><span data-stu-id="50b59-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="50b59-116">Details</span><span class="sxs-lookup"><span data-stu-id="50b59-116">Details</span></span>  
  
|<span data-ttu-id="50b59-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="50b59-117">Data Item Name</span></span>|<span data-ttu-id="50b59-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="50b59-118">Data Item Type</span></span>|<span data-ttu-id="50b59-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50b59-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="50b59-120">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="50b59-120">Exception</span></span>|<span data-ttu-id="50b59-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="50b59-121">xs:string</span></span>|<span data-ttu-id="50b59-122">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="50b59-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="50b59-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="50b59-123">AppDomain</span></span>|<span data-ttu-id="50b59-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="50b59-124">xs:string</span></span>|<span data-ttu-id="50b59-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="50b59-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
