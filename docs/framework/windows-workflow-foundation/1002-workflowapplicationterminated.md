---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="45d1b-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="45d1b-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="45d1b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="45d1b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45d1b-104">ID</span><span class="sxs-lookup"><span data-stu-id="45d1b-104">ID</span></span>|<span data-ttu-id="45d1b-105">1002</span><span class="sxs-lookup"><span data-stu-id="45d1b-105">1002</span></span>|  
|<span data-ttu-id="45d1b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="45d1b-106">Keywords</span></span>|<span data-ttu-id="45d1b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45d1b-107">WFRuntime</span></span>|  
|<span data-ttu-id="45d1b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="45d1b-108">Level</span></span>|<span data-ttu-id="45d1b-109">Information</span><span class="sxs-lookup"><span data-stu-id="45d1b-109">Information</span></span>|  
|<span data-ttu-id="45d1b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="45d1b-110">Channel</span></span>|<span data-ttu-id="45d1b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="45d1b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45d1b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45d1b-112">Description</span></span>  
 <span data-ttu-id="45d1b-113">Gibt an, dass eine Workflowanwendung im Faulted-Zustand einer Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="45d1b-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45d1b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="45d1b-114">Message</span></span>  
 <span data-ttu-id="45d1b-115">WorkflowApplication-ID: '%1' wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="45d1b-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="45d1b-116">Sie wurde im Faulted-Status mit einer Ausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="45d1b-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45d1b-117">Details</span><span class="sxs-lookup"><span data-stu-id="45d1b-117">Details</span></span>  
  
|<span data-ttu-id="45d1b-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="45d1b-118">Data Item Name</span></span>|<span data-ttu-id="45d1b-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="45d1b-119">Data Item Type</span></span>|<span data-ttu-id="45d1b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45d1b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45d1b-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="45d1b-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="45d1b-122">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="45d1b-122">The workflow application id</span></span>|  
|<span data-ttu-id="45d1b-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="45d1b-123">Exception</span></span>|`xs:string`|<span data-ttu-id="45d1b-124">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="45d1b-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="45d1b-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45d1b-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="45d1b-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="45d1b-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
