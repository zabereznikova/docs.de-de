---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc505a4e0e79b37f9adff41b80dcba55215576f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="c2c1d-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="c2c1d-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="c2c1d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c2c1d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2c1d-104">ID</span><span class="sxs-lookup"><span data-stu-id="c2c1d-104">ID</span></span>|<span data-ttu-id="c2c1d-105">3551</span><span class="sxs-lookup"><span data-stu-id="c2c1d-105">3551</span></span>|  
|<span data-ttu-id="c2c1d-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c2c1d-106">Keywords</span></span>|<span data-ttu-id="c2c1d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="c2c1d-107">WFServices</span></span>|  
|<span data-ttu-id="c2c1d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="c2c1d-108">Level</span></span>|<span data-ttu-id="c2c1d-109">Information</span><span class="sxs-lookup"><span data-stu-id="c2c1d-109">Information</span></span>|  
|<span data-ttu-id="c2c1d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="c2c1d-110">Channel</span></span>|<span data-ttu-id="c2c1d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c2c1d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c2c1d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2c1d-112">Description</span></span>  
 <span data-ttu-id="c2c1d-113">Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="c2c1d-114">Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c2c1d-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="c2c1d-115">Message</span></span>  
 <span data-ttu-id="c2c1d-116">Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="c2c1d-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c2c1d-118">Details</span><span class="sxs-lookup"><span data-stu-id="c2c1d-118">Details</span></span>  
  
|<span data-ttu-id="c2c1d-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="c2c1d-119">Data Item Name</span></span>|<span data-ttu-id="c2c1d-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="c2c1d-120">Data Item Type</span></span>|<span data-ttu-id="c2c1d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2c1d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c2c1d-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="c2c1d-122">OperationName</span></span>|<span data-ttu-id="c2c1d-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c2c1d-123">xs:string</span></span>|<span data-ttu-id="c2c1d-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-124">The name of the operation.</span></span>|  
|<span data-ttu-id="c2c1d-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="c2c1d-125">ServiceInstanceId</span></span>|<span data-ttu-id="c2c1d-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c2c1d-126">xs:string</span></span>|<span data-ttu-id="c2c1d-127">Die ID der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="c2c1d-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c2c1d-128">AppDomain</span></span>|<span data-ttu-id="c2c1d-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="c2c1d-129">xs:string</span></span>|<span data-ttu-id="c2c1d-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c2c1d-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
