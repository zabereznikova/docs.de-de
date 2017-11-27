---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f497d777221a98b38603b2ced29342651b1020b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="1e470-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="1e470-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="1e470-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1e470-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e470-104">ID</span><span class="sxs-lookup"><span data-stu-id="1e470-104">ID</span></span>|<span data-ttu-id="1e470-105">1036</span><span class="sxs-lookup"><span data-stu-id="1e470-105">1036</span></span>|  
|<span data-ttu-id="1e470-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1e470-106">Keywords</span></span>|<span data-ttu-id="1e470-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1e470-107">WFRuntime</span></span>|  
|<span data-ttu-id="1e470-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1e470-108">Level</span></span>|<span data-ttu-id="1e470-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="1e470-109">Verbose</span></span>|  
|<span data-ttu-id="1e470-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1e470-110">Channel</span></span>|<span data-ttu-id="1e470-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1e470-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1e470-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e470-112">Description</span></span>  
 <span data-ttu-id="1e470-113">Gibt an, dass eine Aktivität den Abschluss der Ablauftransaktion geplant hat.</span><span class="sxs-lookup"><span data-stu-id="1e470-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1e470-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1e470-114">Message</span></span>  
 <span data-ttu-id="1e470-115">Die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat den Abschluss der Laufzeittransaktion geplant.</span><span class="sxs-lookup"><span data-stu-id="1e470-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1e470-116">Details</span><span class="sxs-lookup"><span data-stu-id="1e470-116">Details</span></span>  
  
|<span data-ttu-id="1e470-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1e470-117">Data Item Name</span></span>|<span data-ttu-id="1e470-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1e470-118">Data Item Type</span></span>|<span data-ttu-id="1e470-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e470-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1e470-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="1e470-120">Activity</span></span>|<span data-ttu-id="1e470-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e470-121">xs:string</span></span>|<span data-ttu-id="1e470-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1e470-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="1e470-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1e470-123">DisplayName</span></span>|<span data-ttu-id="1e470-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e470-124">xs:string</span></span>|<span data-ttu-id="1e470-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1e470-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="1e470-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1e470-126">InstanceId</span></span>|<span data-ttu-id="1e470-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e470-127">xs:string</span></span>|<span data-ttu-id="1e470-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1e470-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1e470-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1e470-129">AppDomain</span></span>|<span data-ttu-id="1e470-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1e470-130">xs:string</span></span>|<span data-ttu-id="1e470-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e470-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
