---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510078"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="d5f36-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="d5f36-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="d5f36-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d5f36-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5f36-104">ID</span><span class="sxs-lookup"><span data-stu-id="d5f36-104">ID</span></span>|<span data-ttu-id="d5f36-105">1002</span><span class="sxs-lookup"><span data-stu-id="d5f36-105">1002</span></span>|  
|<span data-ttu-id="d5f36-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d5f36-106">Keywords</span></span>|<span data-ttu-id="d5f36-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d5f36-107">WFRuntime</span></span>|  
|<span data-ttu-id="d5f36-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d5f36-108">Level</span></span>|<span data-ttu-id="d5f36-109">Information</span><span class="sxs-lookup"><span data-stu-id="d5f36-109">Information</span></span>|  
|<span data-ttu-id="d5f36-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d5f36-110">Channel</span></span>|<span data-ttu-id="d5f36-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d5f36-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d5f36-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5f36-112">Description</span></span>  
 <span data-ttu-id="d5f36-113">Gibt an, dass eine Workflowanwendung im Faulted-Zustand einer Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d5f36-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d5f36-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d5f36-114">Message</span></span>  
 <span data-ttu-id="d5f36-115">WorkflowApplication-ID: '%1' wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="d5f36-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="d5f36-116">Sie wurde im Faulted-Status mit einer Ausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d5f36-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d5f36-117">Details</span><span class="sxs-lookup"><span data-stu-id="d5f36-117">Details</span></span>  
  
|<span data-ttu-id="d5f36-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d5f36-118">Data Item Name</span></span>|<span data-ttu-id="d5f36-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d5f36-119">Data Item Type</span></span>|<span data-ttu-id="d5f36-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5f36-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d5f36-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="d5f36-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="d5f36-122">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="d5f36-122">The workflow application id</span></span>|  
|<span data-ttu-id="d5f36-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d5f36-123">Exception</span></span>|`xs:string`|<span data-ttu-id="d5f36-124">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="d5f36-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="d5f36-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d5f36-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d5f36-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d5f36-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
