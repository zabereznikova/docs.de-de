---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239938"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="9c837-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="9c837-102">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="9c837-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9c837-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c837-104">id</span><span class="sxs-lookup"><span data-stu-id="9c837-104">ID</span></span>|<span data-ttu-id="9c837-105">1002</span><span class="sxs-lookup"><span data-stu-id="9c837-105">1002</span></span>|  
|<span data-ttu-id="9c837-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9c837-106">Keywords</span></span>|<span data-ttu-id="9c837-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9c837-107">WFRuntime</span></span>|  
|<span data-ttu-id="9c837-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9c837-108">Level</span></span>|<span data-ttu-id="9c837-109">Information</span><span class="sxs-lookup"><span data-stu-id="9c837-109">Information</span></span>|  
|<span data-ttu-id="9c837-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9c837-110">Channel</span></span>|<span data-ttu-id="9c837-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9c837-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9c837-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c837-112">Description</span></span>  

 <span data-ttu-id="9c837-113">Gibt an, dass eine Workflowanwendung im Faulted-Zustand einer Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9c837-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9c837-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="9c837-114">Message</span></span>  

 <span data-ttu-id="9c837-115">WorkflowApplication-ID: '%1' wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="9c837-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="9c837-116">Sie wurde im Faulted-Status mit einer Ausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9c837-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9c837-117">Details</span><span class="sxs-lookup"><span data-stu-id="9c837-117">Details</span></span>  
  
|<span data-ttu-id="9c837-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9c837-118">Data Item Name</span></span>|<span data-ttu-id="9c837-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9c837-119">Data Item Type</span></span>|<span data-ttu-id="9c837-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c837-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9c837-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="9c837-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="9c837-122">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="9c837-122">The workflow application id</span></span>|  
|<span data-ttu-id="9c837-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="9c837-123">Exception</span></span>|`xs:string`|<span data-ttu-id="9c837-124">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="9c837-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="9c837-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9c837-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9c837-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c837-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
