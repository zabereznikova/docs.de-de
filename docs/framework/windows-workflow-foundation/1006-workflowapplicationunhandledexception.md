---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239833"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="2cb86-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="2cb86-102">1006 - WorkflowApplicationUnhandledException</span></span>

## <a name="properties"></a><span data-ttu-id="2cb86-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2cb86-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cb86-104">id</span><span class="sxs-lookup"><span data-stu-id="2cb86-104">ID</span></span>|<span data-ttu-id="2cb86-105">1006</span><span class="sxs-lookup"><span data-stu-id="2cb86-105">1006</span></span>|  
|<span data-ttu-id="2cb86-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2cb86-106">Keywords</span></span>|<span data-ttu-id="2cb86-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2cb86-107">WFRuntime</span></span>|  
|<span data-ttu-id="2cb86-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2cb86-108">Level</span></span>|<span data-ttu-id="2cb86-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="2cb86-109">Error</span></span>|  
|<span data-ttu-id="2cb86-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2cb86-110">Channel</span></span>|<span data-ttu-id="2cb86-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2cb86-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2cb86-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2cb86-112">Description</span></span>  

 <span data-ttu-id="2cb86-113">Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2cb86-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2cb86-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="2cb86-114">Message</span></span>  

 <span data-ttu-id="2cb86-115">WorkflowInstance-ID: ' %1 ' hat eine nicht behandelte Ausnahme gefunden.</span><span class="sxs-lookup"><span data-stu-id="2cb86-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="2cb86-116">Die Ausnahme stammt aus der Aktivität ' %2 ', Display Name: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="2cb86-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="2cb86-117">Die folgende Aktion wird ausgeführt: %4.</span><span class="sxs-lookup"><span data-stu-id="2cb86-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2cb86-118">Details</span><span class="sxs-lookup"><span data-stu-id="2cb86-118">Details</span></span>  
  
|<span data-ttu-id="2cb86-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2cb86-119">Data Item Name</span></span>|<span data-ttu-id="2cb86-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2cb86-120">Data Item Type</span></span>|<span data-ttu-id="2cb86-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2cb86-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2cb86-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2cb86-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2cb86-123">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="2cb86-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="2cb86-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="2cb86-124">Exception</span></span>|`xs:string`|<span data-ttu-id="2cb86-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="2cb86-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="2cb86-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2cb86-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2cb86-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2cb86-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
