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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54ef06c3aded628e18325b78f55e80e4470ecd01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="95343-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="95343-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="95343-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="95343-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95343-104">ID</span><span class="sxs-lookup"><span data-stu-id="95343-104">ID</span></span>|<span data-ttu-id="95343-105">1002</span><span class="sxs-lookup"><span data-stu-id="95343-105">1002</span></span>|  
|<span data-ttu-id="95343-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="95343-106">Keywords</span></span>|<span data-ttu-id="95343-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="95343-107">WFRuntime</span></span>|  
|<span data-ttu-id="95343-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="95343-108">Level</span></span>|<span data-ttu-id="95343-109">Information</span><span class="sxs-lookup"><span data-stu-id="95343-109">Information</span></span>|  
|<span data-ttu-id="95343-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="95343-110">Channel</span></span>|<span data-ttu-id="95343-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="95343-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="95343-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95343-112">Description</span></span>  
 <span data-ttu-id="95343-113">Gibt an, dass eine Workflowanwendung im Faulted-Zustand einer Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="95343-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="95343-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="95343-114">Message</span></span>  
 <span data-ttu-id="95343-115">WorkflowApplication-ID: '%1' wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="95343-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="95343-116">Sie wurde im Faulted-Status mit einer Ausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="95343-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="95343-117">Details</span><span class="sxs-lookup"><span data-stu-id="95343-117">Details</span></span>  
  
|<span data-ttu-id="95343-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="95343-118">Data Item Name</span></span>|<span data-ttu-id="95343-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="95343-119">Data Item Type</span></span>|<span data-ttu-id="95343-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95343-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="95343-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="95343-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="95343-122">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="95343-122">The workflow application id</span></span>|  
|<span data-ttu-id="95343-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="95343-123">Exception</span></span>|`xs:string`|<span data-ttu-id="95343-124">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="95343-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="95343-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="95343-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="95343-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="95343-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
