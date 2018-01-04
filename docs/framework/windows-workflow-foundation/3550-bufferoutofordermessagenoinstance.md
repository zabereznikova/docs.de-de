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
ms.workload: dotnet
ms.openlocfilehash: 435a6a4390d52555d353a25ac119934087cf9c87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="fb78b-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="fb78b-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="fb78b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fb78b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb78b-104">ID</span><span class="sxs-lookup"><span data-stu-id="fb78b-104">ID</span></span>|<span data-ttu-id="fb78b-105">3550</span><span class="sxs-lookup"><span data-stu-id="fb78b-105">3550</span></span>|  
|<span data-ttu-id="fb78b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fb78b-106">Keywords</span></span>|<span data-ttu-id="fb78b-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="fb78b-107">WFServices</span></span>|  
|<span data-ttu-id="fb78b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fb78b-108">Level</span></span>|<span data-ttu-id="fb78b-109">Information</span><span class="sxs-lookup"><span data-stu-id="fb78b-109">Information</span></span>|  
|<span data-ttu-id="fb78b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fb78b-110">Channel</span></span>|<span data-ttu-id="fb78b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fb78b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fb78b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb78b-112">Description</span></span>  
 <span data-ttu-id="fb78b-113">Gibt an, dass ein gepufferter Empfang fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="fb78b-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="fb78b-114">Der Vorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb78b-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fb78b-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="fb78b-115">Message</span></span>  
 <span data-ttu-id="fb78b-116">Vorgang '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb78b-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="fb78b-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb78b-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fb78b-118">Details</span><span class="sxs-lookup"><span data-stu-id="fb78b-118">Details</span></span>  
  
|<span data-ttu-id="fb78b-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fb78b-119">Data Item Name</span></span>|<span data-ttu-id="fb78b-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fb78b-120">Data Item Type</span></span>|<span data-ttu-id="fb78b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb78b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fb78b-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="fb78b-122">OperationName</span></span>|<span data-ttu-id="fb78b-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb78b-123">xs:string</span></span>|<span data-ttu-id="fb78b-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="fb78b-124">The name of the operation.</span></span>|  
|<span data-ttu-id="fb78b-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fb78b-125">AppDomain</span></span>|<span data-ttu-id="fb78b-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb78b-126">xs:string</span></span>|<span data-ttu-id="fb78b-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fb78b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
