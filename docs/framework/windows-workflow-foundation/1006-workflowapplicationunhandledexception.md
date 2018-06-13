---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510756"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="4023f-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="4023f-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="4023f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4023f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4023f-104">ID</span><span class="sxs-lookup"><span data-stu-id="4023f-104">ID</span></span>|<span data-ttu-id="4023f-105">1006</span><span class="sxs-lookup"><span data-stu-id="4023f-105">1006</span></span>|  
|<span data-ttu-id="4023f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4023f-106">Keywords</span></span>|<span data-ttu-id="4023f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4023f-107">WFRuntime</span></span>|  
|<span data-ttu-id="4023f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4023f-108">Level</span></span>|<span data-ttu-id="4023f-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="4023f-109">Error</span></span>|  
|<span data-ttu-id="4023f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4023f-110">Channel</span></span>|<span data-ttu-id="4023f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4023f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4023f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4023f-112">Description</span></span>  
 <span data-ttu-id="4023f-113">Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4023f-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4023f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4023f-114">Message</span></span>  
 <span data-ttu-id="4023f-115">WorkflowInstance-Id: "%1" hat eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4023f-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="4023f-116">Die Ausnahme stammt von der Aktivität '%2', DisplayName: "%3".</span><span class="sxs-lookup"><span data-stu-id="4023f-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="4023f-117">Die folgende Aktion durchzuführenden: %4.</span><span class="sxs-lookup"><span data-stu-id="4023f-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4023f-118">Details</span><span class="sxs-lookup"><span data-stu-id="4023f-118">Details</span></span>  
  
|<span data-ttu-id="4023f-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4023f-119">Data Item Name</span></span>|<span data-ttu-id="4023f-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4023f-120">Data Item Type</span></span>|<span data-ttu-id="4023f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4023f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4023f-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4023f-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="4023f-123">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="4023f-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4023f-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="4023f-124">Exception</span></span>|`xs:string`|<span data-ttu-id="4023f-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="4023f-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="4023f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4023f-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4023f-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4023f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
