---
title: 2577 - TryCatchExceptionDuringCancelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1e851a50c9677b2f10ea3478c3599706007d4d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="45af4-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="45af4-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="45af4-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="45af4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45af4-104">ID</span><span class="sxs-lookup"><span data-stu-id="45af4-104">ID</span></span>|<span data-ttu-id="45af4-105">2577</span><span class="sxs-lookup"><span data-stu-id="45af4-105">2577</span></span>|  
|<span data-ttu-id="45af4-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="45af4-106">Keywords</span></span>|<span data-ttu-id="45af4-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="45af4-107">WFActivities</span></span>|  
|<span data-ttu-id="45af4-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="45af4-108">Level</span></span>|<span data-ttu-id="45af4-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="45af4-109">Warning</span></span>|  
|<span data-ttu-id="45af4-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="45af4-110">Channel</span></span>|<span data-ttu-id="45af4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="45af4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45af4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45af4-112">Description</span></span>  
 <span data-ttu-id="45af4-113">Gibt an, dass eine untergeordnete Aktivität der TryCatch-Aktivität während des Abbruchs eine Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="45af4-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45af4-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="45af4-114">Message</span></span>  
 <span data-ttu-id="45af4-115">Eine untergeordnete Aktivität der TryCatch-Aktivität '%1' hat während des Abbruchs eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="45af4-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45af4-116">Details</span><span class="sxs-lookup"><span data-stu-id="45af4-116">Details</span></span>  
  
|<span data-ttu-id="45af4-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="45af4-117">Data Item Name</span></span>|<span data-ttu-id="45af4-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="45af4-118">Data Item Type</span></span>|<span data-ttu-id="45af4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45af4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45af4-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="45af4-120">DisplayName</span></span>|<span data-ttu-id="45af4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="45af4-121">xs:string</span></span>|<span data-ttu-id="45af4-122">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="45af4-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="45af4-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45af4-123">AppDomain</span></span>|<span data-ttu-id="45af4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="45af4-124">xs:string</span></span>|<span data-ttu-id="45af4-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="45af4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
