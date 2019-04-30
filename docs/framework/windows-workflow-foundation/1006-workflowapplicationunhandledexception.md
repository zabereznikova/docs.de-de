---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924708"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="d4f6b-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="d4f6b-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="d4f6b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4f6b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4f6b-104">ID</span><span class="sxs-lookup"><span data-stu-id="d4f6b-104">ID</span></span>|<span data-ttu-id="d4f6b-105">1006</span><span class="sxs-lookup"><span data-stu-id="d4f6b-105">1006</span></span>|  
|<span data-ttu-id="d4f6b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d4f6b-106">Keywords</span></span>|<span data-ttu-id="d4f6b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d4f6b-107">WFRuntime</span></span>|  
|<span data-ttu-id="d4f6b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d4f6b-108">Level</span></span>|<span data-ttu-id="d4f6b-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="d4f6b-109">Error</span></span>|  
|<span data-ttu-id="d4f6b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d4f6b-110">Channel</span></span>|<span data-ttu-id="d4f6b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d4f6b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4f6b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4f6b-112">Description</span></span>  
 <span data-ttu-id="d4f6b-113">Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4f6b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d4f6b-114">Message</span></span>  
 <span data-ttu-id="d4f6b-115">WorkflowInstance-Id: "%1" hat eine nicht behandelte Ausnahme festgestellt.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="d4f6b-116">Die Ausnahme stammt aus Aktivität '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="d4f6b-117">Die folgende Aktion wird ausgeführt: %4.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4f6b-118">Details</span><span class="sxs-lookup"><span data-stu-id="d4f6b-118">Details</span></span>  
  
|<span data-ttu-id="d4f6b-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d4f6b-119">Data Item Name</span></span>|<span data-ttu-id="d4f6b-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d4f6b-120">Data Item Type</span></span>|<span data-ttu-id="d4f6b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4f6b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4f6b-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="d4f6b-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="d4f6b-123">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="d4f6b-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d4f6b-124">Exception</span></span>|`xs:string`|<span data-ttu-id="d4f6b-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="d4f6b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4f6b-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d4f6b-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d4f6b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
