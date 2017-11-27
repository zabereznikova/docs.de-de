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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ce8b2cd52523d8a2efc94214479ca3c41d2dec4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="efa94-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="efa94-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="efa94-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="efa94-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efa94-104">ID</span><span class="sxs-lookup"><span data-stu-id="efa94-104">ID</span></span>|<span data-ttu-id="efa94-105">3550</span><span class="sxs-lookup"><span data-stu-id="efa94-105">3550</span></span>|  
|<span data-ttu-id="efa94-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="efa94-106">Keywords</span></span>|<span data-ttu-id="efa94-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="efa94-107">WFServices</span></span>|  
|<span data-ttu-id="efa94-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="efa94-108">Level</span></span>|<span data-ttu-id="efa94-109">Information</span><span class="sxs-lookup"><span data-stu-id="efa94-109">Information</span></span>|  
|<span data-ttu-id="efa94-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="efa94-110">Channel</span></span>|<span data-ttu-id="efa94-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="efa94-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="efa94-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efa94-112">Description</span></span>  
 <span data-ttu-id="efa94-113">Gibt an, dass ein gepufferter Empfang fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="efa94-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="efa94-114">Der Vorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="efa94-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="efa94-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="efa94-115">Message</span></span>  
 <span data-ttu-id="efa94-116">Vorgang '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="efa94-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="efa94-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="efa94-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="efa94-118">Details</span><span class="sxs-lookup"><span data-stu-id="efa94-118">Details</span></span>  
  
|<span data-ttu-id="efa94-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="efa94-119">Data Item Name</span></span>|<span data-ttu-id="efa94-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="efa94-120">Data Item Type</span></span>|<span data-ttu-id="efa94-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efa94-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="efa94-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="efa94-122">OperationName</span></span>|<span data-ttu-id="efa94-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="efa94-123">xs:string</span></span>|<span data-ttu-id="efa94-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="efa94-124">The name of the operation.</span></span>|  
|<span data-ttu-id="efa94-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="efa94-125">AppDomain</span></span>|<span data-ttu-id="efa94-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="efa94-126">xs:string</span></span>|<span data-ttu-id="efa94-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="efa94-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
