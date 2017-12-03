---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2a150b9e9c78a9ce1f5e20b962a58ef2d5dde9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="d49fa-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="d49fa-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d49fa-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d49fa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d49fa-104">ID</span><span class="sxs-lookup"><span data-stu-id="d49fa-104">ID</span></span>|<span data-ttu-id="d49fa-105">1032</span><span class="sxs-lookup"><span data-stu-id="d49fa-105">1032</span></span>|  
|<span data-ttu-id="d49fa-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d49fa-106">Keywords</span></span>|<span data-ttu-id="d49fa-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d49fa-107">WFRuntime</span></span>|  
|<span data-ttu-id="d49fa-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d49fa-108">Level</span></span>|<span data-ttu-id="d49fa-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="d49fa-109">Verbose</span></span>|  
|<span data-ttu-id="d49fa-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d49fa-110">Channel</span></span>|<span data-ttu-id="d49fa-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d49fa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d49fa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d49fa-112">Description</span></span>  
 <span data-ttu-id="d49fa-113">Gibt an, dass ein RuntimeWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="d49fa-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d49fa-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d49fa-114">Message</span></span>  
 <span data-ttu-id="d49fa-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine Laufzeitarbeitsaufgabe geplant.</span><span class="sxs-lookup"><span data-stu-id="d49fa-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d49fa-116">Details</span><span class="sxs-lookup"><span data-stu-id="d49fa-116">Details</span></span>  
  
|<span data-ttu-id="d49fa-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d49fa-117">Data Item Name</span></span>|<span data-ttu-id="d49fa-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d49fa-118">Data Item Type</span></span>|<span data-ttu-id="d49fa-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d49fa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d49fa-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="d49fa-120">Activity</span></span>|<span data-ttu-id="d49fa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d49fa-121">xs:string</span></span>|<span data-ttu-id="d49fa-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d49fa-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d49fa-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d49fa-123">DisplayName</span></span>|<span data-ttu-id="d49fa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d49fa-124">xs:string</span></span>|<span data-ttu-id="d49fa-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d49fa-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d49fa-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d49fa-126">InstanceId</span></span>|<span data-ttu-id="d49fa-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d49fa-127">xs:string</span></span>|<span data-ttu-id="d49fa-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d49fa-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d49fa-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d49fa-129">AppDomain</span></span>|<span data-ttu-id="d49fa-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d49fa-130">xs:string</span></span>|<span data-ttu-id="d49fa-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d49fa-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
