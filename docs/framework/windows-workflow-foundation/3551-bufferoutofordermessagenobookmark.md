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
ms.workload: dotnet
ms.openlocfilehash: 5e785e40afcb91620940f952022eda4c4b799f4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="d2718-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="d2718-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="d2718-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d2718-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2718-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2718-104">ID</span></span>|<span data-ttu-id="d2718-105">3551</span><span class="sxs-lookup"><span data-stu-id="d2718-105">3551</span></span>|  
|<span data-ttu-id="d2718-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d2718-106">Keywords</span></span>|<span data-ttu-id="d2718-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d2718-107">WFServices</span></span>|  
|<span data-ttu-id="d2718-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d2718-108">Level</span></span>|<span data-ttu-id="d2718-109">Information</span><span class="sxs-lookup"><span data-stu-id="d2718-109">Information</span></span>|  
|<span data-ttu-id="d2718-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d2718-110">Channel</span></span>|<span data-ttu-id="d2718-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d2718-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2718-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2718-112">Description</span></span>  
 <span data-ttu-id="d2718-113">Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="d2718-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="d2718-114">Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d2718-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2718-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="d2718-115">Message</span></span>  
 <span data-ttu-id="d2718-116">Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2718-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="d2718-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d2718-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2718-118">Details</span><span class="sxs-lookup"><span data-stu-id="d2718-118">Details</span></span>  
  
|<span data-ttu-id="d2718-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d2718-119">Data Item Name</span></span>|<span data-ttu-id="d2718-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d2718-120">Data Item Type</span></span>|<span data-ttu-id="d2718-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2718-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2718-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="d2718-122">OperationName</span></span>|<span data-ttu-id="d2718-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2718-123">xs:string</span></span>|<span data-ttu-id="d2718-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="d2718-124">The name of the operation.</span></span>|  
|<span data-ttu-id="d2718-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="d2718-125">ServiceInstanceId</span></span>|<span data-ttu-id="d2718-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2718-126">xs:string</span></span>|<span data-ttu-id="d2718-127">Die ID der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="d2718-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="d2718-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2718-128">AppDomain</span></span>|<span data-ttu-id="d2718-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2718-129">xs:string</span></span>|<span data-ttu-id="d2718-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d2718-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
