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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4bc0d9ab45fe8e2f025c651fce137d6a4255bc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="4274f-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="4274f-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="4274f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4274f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4274f-104">ID</span><span class="sxs-lookup"><span data-stu-id="4274f-104">ID</span></span>|<span data-ttu-id="4274f-105">2577</span><span class="sxs-lookup"><span data-stu-id="4274f-105">2577</span></span>|  
|<span data-ttu-id="4274f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4274f-106">Keywords</span></span>|<span data-ttu-id="4274f-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="4274f-107">WFActivities</span></span>|  
|<span data-ttu-id="4274f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4274f-108">Level</span></span>|<span data-ttu-id="4274f-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="4274f-109">Warning</span></span>|  
|<span data-ttu-id="4274f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4274f-110">Channel</span></span>|<span data-ttu-id="4274f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4274f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4274f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4274f-112">Description</span></span>  
 <span data-ttu-id="4274f-113">Gibt an, dass eine untergeordnete Aktivität der TryCatch-Aktivität während des Abbruchs eine Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="4274f-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4274f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4274f-114">Message</span></span>  
 <span data-ttu-id="4274f-115">Eine untergeordnete Aktivität der TryCatch-Aktivität '%1' hat während des Abbruchs eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4274f-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4274f-116">Details</span><span class="sxs-lookup"><span data-stu-id="4274f-116">Details</span></span>  
  
|<span data-ttu-id="4274f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4274f-117">Data Item Name</span></span>|<span data-ttu-id="4274f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4274f-118">Data Item Type</span></span>|<span data-ttu-id="4274f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4274f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4274f-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4274f-120">DisplayName</span></span>|<span data-ttu-id="4274f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4274f-121">xs:string</span></span>|<span data-ttu-id="4274f-122">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="4274f-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="4274f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4274f-123">AppDomain</span></span>|<span data-ttu-id="4274f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4274f-124">xs:string</span></span>|<span data-ttu-id="4274f-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4274f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
