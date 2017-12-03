---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="6a7a9-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="6a7a9-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="6a7a9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6a7a9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a7a9-104">ID</span><span class="sxs-lookup"><span data-stu-id="6a7a9-104">ID</span></span>|<span data-ttu-id="6a7a9-105">3550</span><span class="sxs-lookup"><span data-stu-id="6a7a9-105">3550</span></span>|  
|<span data-ttu-id="6a7a9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6a7a9-106">Keywords</span></span>|<span data-ttu-id="6a7a9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="6a7a9-107">WFServices</span></span>|  
|<span data-ttu-id="6a7a9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6a7a9-108">Level</span></span>|<span data-ttu-id="6a7a9-109">Information</span><span class="sxs-lookup"><span data-stu-id="6a7a9-109">Information</span></span>|  
|<span data-ttu-id="6a7a9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6a7a9-110">Channel</span></span>|<span data-ttu-id="6a7a9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6a7a9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6a7a9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a7a9-112">Description</span></span>  
 <span data-ttu-id="6a7a9-113">Gibt an, dass ein gepufferter Empfang fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="6a7a9-114">Der Vorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6a7a9-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="6a7a9-115">Message</span></span>  
 <span data-ttu-id="6a7a9-116">Vorgang '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="6a7a9-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6a7a9-118">Details</span><span class="sxs-lookup"><span data-stu-id="6a7a9-118">Details</span></span>  
  
|<span data-ttu-id="6a7a9-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6a7a9-119">Data Item Name</span></span>|<span data-ttu-id="6a7a9-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6a7a9-120">Data Item Type</span></span>|<span data-ttu-id="6a7a9-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a7a9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6a7a9-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="6a7a9-122">OperationName</span></span>|<span data-ttu-id="6a7a9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a7a9-123">xs:string</span></span>|<span data-ttu-id="6a7a9-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-124">The name of the operation.</span></span>|  
|<span data-ttu-id="6a7a9-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6a7a9-125">AppDomain</span></span>|<span data-ttu-id="6a7a9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a7a9-126">xs:string</span></span>|<span data-ttu-id="6a7a9-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6a7a9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
