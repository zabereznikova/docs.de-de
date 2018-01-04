---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 743b16232e239929f75e269faa16799a37043495
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="bff62-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="bff62-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bff62-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bff62-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bff62-104">ID</span><span class="sxs-lookup"><span data-stu-id="bff62-104">ID</span></span>|<span data-ttu-id="bff62-105">1034</span><span class="sxs-lookup"><span data-stu-id="bff62-105">1034</span></span>|  
|<span data-ttu-id="bff62-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bff62-106">Keywords</span></span>|<span data-ttu-id="bff62-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bff62-107">WFRuntime</span></span>|  
|<span data-ttu-id="bff62-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bff62-108">Level</span></span>|<span data-ttu-id="bff62-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="bff62-109">Verbose</span></span>|  
|<span data-ttu-id="bff62-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bff62-110">Channel</span></span>|<span data-ttu-id="bff62-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bff62-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bff62-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bff62-112">Description</span></span>  
 <span data-ttu-id="bff62-113">Gibt an, dass ein RuntimeWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="bff62-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bff62-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="bff62-114">Message</span></span>  
 <span data-ttu-id="bff62-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine Laufzeitarbeitsaufgabe abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bff62-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bff62-116">Details</span><span class="sxs-lookup"><span data-stu-id="bff62-116">Details</span></span>  
  
|<span data-ttu-id="bff62-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bff62-117">Data Item Name</span></span>|<span data-ttu-id="bff62-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bff62-118">Data Item Type</span></span>|<span data-ttu-id="bff62-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bff62-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bff62-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="bff62-120">Activity</span></span>|<span data-ttu-id="bff62-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bff62-121">xs:string</span></span>|<span data-ttu-id="bff62-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bff62-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bff62-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bff62-123">DisplayName</span></span>|<span data-ttu-id="bff62-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bff62-124">xs:string</span></span>|<span data-ttu-id="bff62-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bff62-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bff62-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bff62-126">InstanceId</span></span>|<span data-ttu-id="bff62-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bff62-127">xs:string</span></span>|<span data-ttu-id="bff62-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bff62-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bff62-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bff62-129">AppDomain</span></span>|<span data-ttu-id="bff62-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bff62-130">xs:string</span></span>|<span data-ttu-id="bff62-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bff62-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
