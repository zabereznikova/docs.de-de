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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 112063d5cd550f438541b2d775eaa49124d9cc02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="2ea4f-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="2ea4f-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="2ea4f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2ea4f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ea4f-104">ID</span><span class="sxs-lookup"><span data-stu-id="2ea4f-104">ID</span></span>|<span data-ttu-id="2ea4f-105">1036</span><span class="sxs-lookup"><span data-stu-id="2ea4f-105">1036</span></span>|  
|<span data-ttu-id="2ea4f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2ea4f-106">Keywords</span></span>|<span data-ttu-id="2ea4f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2ea4f-107">WFRuntime</span></span>|  
|<span data-ttu-id="2ea4f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2ea4f-108">Level</span></span>|<span data-ttu-id="2ea4f-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="2ea4f-109">Verbose</span></span>|  
|<span data-ttu-id="2ea4f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2ea4f-110">Channel</span></span>|<span data-ttu-id="2ea4f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2ea4f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2ea4f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ea4f-112">Description</span></span>  
 <span data-ttu-id="2ea4f-113">Gibt an, dass eine Aktivität den Abschluss der Ablauftransaktion geplant hat.</span><span class="sxs-lookup"><span data-stu-id="2ea4f-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2ea4f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="2ea4f-114">Message</span></span>  
 <span data-ttu-id="2ea4f-115">Die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat den Abschluss der Laufzeittransaktion geplant.</span><span class="sxs-lookup"><span data-stu-id="2ea4f-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2ea4f-116">Details</span><span class="sxs-lookup"><span data-stu-id="2ea4f-116">Details</span></span>  
  
|<span data-ttu-id="2ea4f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2ea4f-117">Data Item Name</span></span>|<span data-ttu-id="2ea4f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2ea4f-118">Data Item Type</span></span>|<span data-ttu-id="2ea4f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ea4f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2ea4f-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="2ea4f-120">Activity</span></span>|<span data-ttu-id="2ea4f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ea4f-121">xs:string</span></span>|<span data-ttu-id="2ea4f-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2ea4f-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2ea4f-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2ea4f-123">DisplayName</span></span>|<span data-ttu-id="2ea4f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ea4f-124">xs:string</span></span>|<span data-ttu-id="2ea4f-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2ea4f-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2ea4f-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2ea4f-126">InstanceId</span></span>|<span data-ttu-id="2ea4f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ea4f-127">xs:string</span></span>|<span data-ttu-id="2ea4f-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2ea4f-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2ea4f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2ea4f-129">AppDomain</span></span>|<span data-ttu-id="2ea4f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ea4f-130">xs:string</span></span>|<span data-ttu-id="2ea4f-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2ea4f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
