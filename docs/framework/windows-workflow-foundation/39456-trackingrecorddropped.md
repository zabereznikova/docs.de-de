---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: d958b506e057bc0d59f954debdc9da6015bf5f1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273099"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="f6bf1-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="f6bf1-102">39456 - TrackingRecordDropped</span></span>

## <a name="properties"></a><span data-ttu-id="f6bf1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f6bf1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6bf1-104">id</span><span class="sxs-lookup"><span data-stu-id="f6bf1-104">ID</span></span>|<span data-ttu-id="f6bf1-105">39456</span><span class="sxs-lookup"><span data-stu-id="f6bf1-105">39456</span></span>|  
|<span data-ttu-id="f6bf1-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="f6bf1-106">Keywords</span></span>|<span data-ttu-id="f6bf1-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="f6bf1-107">WFTracking</span></span>|  
|<span data-ttu-id="f6bf1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f6bf1-108">Level</span></span>|<span data-ttu-id="f6bf1-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="f6bf1-109">Warning</span></span>|  
|<span data-ttu-id="f6bf1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f6bf1-110">Channel</span></span>|<span data-ttu-id="f6bf1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f6bf1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f6bf1-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6bf1-112">Description</span></span>  

 <span data-ttu-id="f6bf1-113">Gibt an, dass ein Nachverfolgungsdatensatz gelöscht wurde, weil sein Größe den maximal zulässigen Wert des ETW-Sitzungsanbieters überschreitet.</span><span class="sxs-lookup"><span data-stu-id="f6bf1-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f6bf1-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="f6bf1-114">Message</span></span>  

 <span data-ttu-id="f6bf1-115">Die Größe des Überwachungsdatensatzes %1 überschreitet das zulässige Maximum der ETW-Sitzung für den Anbieter %2.</span><span class="sxs-lookup"><span data-stu-id="f6bf1-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="f6bf1-116">Details</span><span class="sxs-lookup"><span data-stu-id="f6bf1-116">Details</span></span>  
  
|<span data-ttu-id="f6bf1-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f6bf1-117">Data Item Name</span></span>|<span data-ttu-id="f6bf1-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f6bf1-118">Data Item Type</span></span>|<span data-ttu-id="f6bf1-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6bf1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f6bf1-120">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="f6bf1-120">Exception</span></span>|<span data-ttu-id="f6bf1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6bf1-121">xs:string</span></span>|<span data-ttu-id="f6bf1-122">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f6bf1-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="f6bf1-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f6bf1-123">AppDomain</span></span>|<span data-ttu-id="f6bf1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6bf1-124">xs:string</span></span>|<span data-ttu-id="f6bf1-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f6bf1-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
