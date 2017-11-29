---
title: 1033 - StartRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0de8e45a592cae49060f976b28a7a7bcf8781265
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="4988c-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="4988c-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4988c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4988c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4988c-104">ID</span><span class="sxs-lookup"><span data-stu-id="4988c-104">ID</span></span>|<span data-ttu-id="4988c-105">1033</span><span class="sxs-lookup"><span data-stu-id="4988c-105">1033</span></span>|  
|<span data-ttu-id="4988c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4988c-106">Keywords</span></span>|<span data-ttu-id="4988c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4988c-107">WFRuntime</span></span>|  
|<span data-ttu-id="4988c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4988c-108">Level</span></span>|<span data-ttu-id="4988c-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="4988c-109">Verbose</span></span>|  
|<span data-ttu-id="4988c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4988c-110">Channel</span></span>|<span data-ttu-id="4988c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4988c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4988c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4988c-112">Description</span></span>  
 <span data-ttu-id="4988c-113">Gibt an, dass ein RuntimeWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="4988c-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4988c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4988c-114">Message</span></span>  
 <span data-ttu-id="4988c-115">Die Ausführung einer Laufzeitarbeitsaufgabe für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="4988c-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4988c-116">Details</span><span class="sxs-lookup"><span data-stu-id="4988c-116">Details</span></span>  
  
|<span data-ttu-id="4988c-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4988c-117">Data Item Name</span></span>|<span data-ttu-id="4988c-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4988c-118">Data Item Type</span></span>|<span data-ttu-id="4988c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4988c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4988c-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="4988c-120">Activity</span></span>|<span data-ttu-id="4988c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4988c-121">xs:string</span></span>|<span data-ttu-id="4988c-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4988c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4988c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4988c-123">DisplayName</span></span>|<span data-ttu-id="4988c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4988c-124">xs:string</span></span>|<span data-ttu-id="4988c-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4988c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4988c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4988c-126">InstanceId</span></span>|<span data-ttu-id="4988c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4988c-127">xs:string</span></span>|<span data-ttu-id="4988c-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4988c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4988c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4988c-129">AppDomain</span></span>|<span data-ttu-id="4988c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4988c-130">xs:string</span></span>|<span data-ttu-id="4988c-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4988c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
