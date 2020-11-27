---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275891"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="9f23c-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="9f23c-102">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="9f23c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9f23c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f23c-104">id</span><span class="sxs-lookup"><span data-stu-id="9f23c-104">ID</span></span>|<span data-ttu-id="9f23c-105">39458</span><span class="sxs-lookup"><span data-stu-id="9f23c-105">39458</span></span>|  
|<span data-ttu-id="9f23c-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9f23c-106">Keywords</span></span>|<span data-ttu-id="9f23c-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="9f23c-107">WFTracking</span></span>|  
|<span data-ttu-id="9f23c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9f23c-108">Level</span></span>|<span data-ttu-id="9f23c-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="9f23c-109">Warning</span></span>|  
|<span data-ttu-id="9f23c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9f23c-110">Channel</span></span>|<span data-ttu-id="9f23c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9f23c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9f23c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f23c-112">Description</span></span>  

 <span data-ttu-id="9f23c-113">Gibt an, dass ein Nachverfolgungsdatensatz abgeschnitten wurde.</span><span class="sxs-lookup"><span data-stu-id="9f23c-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="9f23c-114">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="9f23c-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9f23c-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="9f23c-115">Message</span></span>  

 <span data-ttu-id="9f23c-116">Abgeschnittener Überwachungsdatensatz %1 wurde in die ETW-Sitzung mit Anbieter %2 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f23c-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="9f23c-117">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="9f23c-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="9f23c-118">Details</span><span class="sxs-lookup"><span data-stu-id="9f23c-118">Details</span></span>  
  
|<span data-ttu-id="9f23c-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9f23c-119">Data Item Name</span></span>|<span data-ttu-id="9f23c-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9f23c-120">Data Item Type</span></span>|<span data-ttu-id="9f23c-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f23c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9f23c-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="9f23c-122">RecordNumber</span></span>|<span data-ttu-id="9f23c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f23c-123">xs:string</span></span>|<span data-ttu-id="9f23c-124">Die Nummer des Nachverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="9f23c-124">The tracking record number.</span></span>|  
|<span data-ttu-id="9f23c-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="9f23c-125">ProviderId</span></span>|<span data-ttu-id="9f23c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f23c-126">xs:string</span></span>|<span data-ttu-id="9f23c-127">Die ETW-Anbieter-ID.</span><span class="sxs-lookup"><span data-stu-id="9f23c-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="9f23c-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9f23c-128">AppDomain</span></span>|<span data-ttu-id="9f23c-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f23c-129">xs:string</span></span>|<span data-ttu-id="9f23c-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9f23c-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
