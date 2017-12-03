---
title: 1013 - CompleteExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de9add3f537c1d8ff97c92892197598bcc7a4fe7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="58c04-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="58c04-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="58c04-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="58c04-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58c04-104">ID</span><span class="sxs-lookup"><span data-stu-id="58c04-104">ID</span></span>|<span data-ttu-id="58c04-105">1013</span><span class="sxs-lookup"><span data-stu-id="58c04-105">1013</span></span>|  
|<span data-ttu-id="58c04-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="58c04-106">Keywords</span></span>|<span data-ttu-id="58c04-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="58c04-107">WFRuntime</span></span>|  
|<span data-ttu-id="58c04-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="58c04-108">Level</span></span>|<span data-ttu-id="58c04-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="58c04-109">Verbose</span></span>|  
|<span data-ttu-id="58c04-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="58c04-110">Channel</span></span>|<span data-ttu-id="58c04-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="58c04-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="58c04-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58c04-112">Description</span></span>  
 <span data-ttu-id="58c04-113">Gibt an, dass ein ExecuteActivityWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="58c04-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="58c04-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="58c04-114">Message</span></span>  
 <span data-ttu-id="58c04-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="58c04-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="58c04-116">Details</span><span class="sxs-lookup"><span data-stu-id="58c04-116">Details</span></span>  
  
|<span data-ttu-id="58c04-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="58c04-117">Data Item Name</span></span>|<span data-ttu-id="58c04-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="58c04-118">Data Item Type</span></span>|<span data-ttu-id="58c04-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58c04-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="58c04-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="58c04-120">Activity</span></span>|<span data-ttu-id="58c04-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="58c04-121">xs:string</span></span>|<span data-ttu-id="58c04-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="58c04-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="58c04-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="58c04-123">DisplayName</span></span>|<span data-ttu-id="58c04-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="58c04-124">xs:string</span></span>|<span data-ttu-id="58c04-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="58c04-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="58c04-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="58c04-126">InstanceId</span></span>|<span data-ttu-id="58c04-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="58c04-127">xs:string</span></span>|<span data-ttu-id="58c04-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="58c04-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="58c04-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="58c04-129">AppDomain</span></span>|<span data-ttu-id="58c04-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="58c04-130">xs:string</span></span>|<span data-ttu-id="58c04-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="58c04-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
