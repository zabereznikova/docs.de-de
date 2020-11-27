---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 5e6a5f9d21435fee8309bd222443407e50ec2cee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263606"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="21938-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="21938-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="21938-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="21938-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21938-104">id</span><span class="sxs-lookup"><span data-stu-id="21938-104">ID</span></span>|<span data-ttu-id="21938-105">3551</span><span class="sxs-lookup"><span data-stu-id="21938-105">3551</span></span>|  
|<span data-ttu-id="21938-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="21938-106">Keywords</span></span>|<span data-ttu-id="21938-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="21938-107">WFServices</span></span>|  
|<span data-ttu-id="21938-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="21938-108">Level</span></span>|<span data-ttu-id="21938-109">Information</span><span class="sxs-lookup"><span data-stu-id="21938-109">Information</span></span>|  
|<span data-ttu-id="21938-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="21938-110">Channel</span></span>|<span data-ttu-id="21938-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="21938-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="21938-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21938-112">Description</span></span>  

 <span data-ttu-id="21938-113">Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="21938-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="21938-114">Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="21938-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="21938-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="21938-115">Message</span></span>  

 <span data-ttu-id="21938-116">Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="21938-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="21938-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="21938-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="21938-118">Details</span><span class="sxs-lookup"><span data-stu-id="21938-118">Details</span></span>  
  
|<span data-ttu-id="21938-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="21938-119">Data Item Name</span></span>|<span data-ttu-id="21938-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="21938-120">Data Item Type</span></span>|<span data-ttu-id="21938-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21938-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="21938-122">Vorgangsname</span><span class="sxs-lookup"><span data-stu-id="21938-122">OperationName</span></span>|<span data-ttu-id="21938-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="21938-123">xs:string</span></span>|<span data-ttu-id="21938-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="21938-124">The name of the operation.</span></span>|  
|<span data-ttu-id="21938-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="21938-125">ServiceInstanceId</span></span>|<span data-ttu-id="21938-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="21938-126">xs:string</span></span>|<span data-ttu-id="21938-127">Die ID der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="21938-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="21938-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="21938-128">AppDomain</span></span>|<span data-ttu-id="21938-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="21938-129">xs:string</span></span>|<span data-ttu-id="21938-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="21938-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
