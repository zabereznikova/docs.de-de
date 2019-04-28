---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774412"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="93554-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="93554-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="93554-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="93554-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93554-104">ID</span><span class="sxs-lookup"><span data-stu-id="93554-104">ID</span></span>|<span data-ttu-id="93554-105">39458</span><span class="sxs-lookup"><span data-stu-id="93554-105">39458</span></span>|  
|<span data-ttu-id="93554-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="93554-106">Keywords</span></span>|<span data-ttu-id="93554-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="93554-107">WFTracking</span></span>|  
|<span data-ttu-id="93554-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="93554-108">Level</span></span>|<span data-ttu-id="93554-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="93554-109">Warning</span></span>|  
|<span data-ttu-id="93554-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="93554-110">Channel</span></span>|<span data-ttu-id="93554-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="93554-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93554-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93554-112">Description</span></span>  
 <span data-ttu-id="93554-113">Gibt an, dass ein Nachverfolgungsdatensatz abgeschnitten wurde.</span><span class="sxs-lookup"><span data-stu-id="93554-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="93554-114">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="93554-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="93554-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="93554-115">Message</span></span>  
 <span data-ttu-id="93554-116">Abgeschnittener Überwachungsdatensatz %1 wurde in die ETW-Sitzung mit Anbieter %2 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="93554-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="93554-117">Variablen, Anmerkungen und Benutzerdaten wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="93554-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="93554-118">Details</span><span class="sxs-lookup"><span data-stu-id="93554-118">Details</span></span>  
  
|<span data-ttu-id="93554-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="93554-119">Data Item Name</span></span>|<span data-ttu-id="93554-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="93554-120">Data Item Type</span></span>|<span data-ttu-id="93554-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93554-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="93554-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="93554-122">RecordNumber</span></span>|<span data-ttu-id="93554-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="93554-123">xs:string</span></span>|<span data-ttu-id="93554-124">Die Nummer des Nachverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="93554-124">The tracking record number.</span></span>|  
|<span data-ttu-id="93554-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="93554-125">ProviderId</span></span>|<span data-ttu-id="93554-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="93554-126">xs:string</span></span>|<span data-ttu-id="93554-127">Die ETW-Anbieter-ID.</span><span class="sxs-lookup"><span data-stu-id="93554-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="93554-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="93554-128">AppDomain</span></span>|<span data-ttu-id="93554-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="93554-129">xs:string</span></span>|<span data-ttu-id="93554-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="93554-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
