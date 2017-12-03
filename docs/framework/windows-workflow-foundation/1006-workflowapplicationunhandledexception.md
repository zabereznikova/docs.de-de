---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a2dad3135de6d3d96328ea039aa36906addb217
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="bf024-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="bf024-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="bf024-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bf024-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf024-104">ID</span><span class="sxs-lookup"><span data-stu-id="bf024-104">ID</span></span>|<span data-ttu-id="bf024-105">1006</span><span class="sxs-lookup"><span data-stu-id="bf024-105">1006</span></span>|  
|<span data-ttu-id="bf024-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bf024-106">Keywords</span></span>|<span data-ttu-id="bf024-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bf024-107">WFRuntime</span></span>|  
|<span data-ttu-id="bf024-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bf024-108">Level</span></span>|<span data-ttu-id="bf024-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="bf024-109">Error</span></span>|  
|<span data-ttu-id="bf024-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bf024-110">Channel</span></span>|<span data-ttu-id="bf024-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bf024-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bf024-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf024-112">Description</span></span>  
 <span data-ttu-id="bf024-113">Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bf024-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bf024-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="bf024-114">Message</span></span>  
 <span data-ttu-id="bf024-115">WorkflowInstance-Id: "%1" hat eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bf024-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="bf024-116">Die Ausnahme stammt von der Aktivität '%2', DisplayName: "%3".</span><span class="sxs-lookup"><span data-stu-id="bf024-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="bf024-117">Die folgende Aktion durchzuführenden: %4.</span><span class="sxs-lookup"><span data-stu-id="bf024-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bf024-118">Details</span><span class="sxs-lookup"><span data-stu-id="bf024-118">Details</span></span>  
  
|<span data-ttu-id="bf024-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bf024-119">Data Item Name</span></span>|<span data-ttu-id="bf024-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bf024-120">Data Item Type</span></span>|<span data-ttu-id="bf024-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf024-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bf024-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="bf024-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="bf024-123">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="bf024-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="bf024-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="bf024-124">Exception</span></span>|`xs:string`|<span data-ttu-id="bf024-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="bf024-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="bf024-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bf024-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bf024-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bf024-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
