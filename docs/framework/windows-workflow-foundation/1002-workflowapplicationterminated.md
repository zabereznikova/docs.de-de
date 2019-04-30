---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008654"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="61c3e-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="61c3e-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="61c3e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="61c3e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61c3e-104">ID</span><span class="sxs-lookup"><span data-stu-id="61c3e-104">ID</span></span>|<span data-ttu-id="61c3e-105">1002</span><span class="sxs-lookup"><span data-stu-id="61c3e-105">1002</span></span>|  
|<span data-ttu-id="61c3e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="61c3e-106">Keywords</span></span>|<span data-ttu-id="61c3e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="61c3e-107">WFRuntime</span></span>|  
|<span data-ttu-id="61c3e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="61c3e-108">Level</span></span>|<span data-ttu-id="61c3e-109">Information</span><span class="sxs-lookup"><span data-stu-id="61c3e-109">Information</span></span>|  
|<span data-ttu-id="61c3e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="61c3e-110">Channel</span></span>|<span data-ttu-id="61c3e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="61c3e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="61c3e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61c3e-112">Description</span></span>  
 <span data-ttu-id="61c3e-113">Gibt an, dass eine Workflowanwendung im Faulted-Zustand einer Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="61c3e-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="61c3e-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="61c3e-114">Message</span></span>  
 <span data-ttu-id="61c3e-115">WorkflowApplication-ID: '%1' wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="61c3e-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="61c3e-116">Sie wurde im Faulted-Status mit einer Ausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="61c3e-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="61c3e-117">Details</span><span class="sxs-lookup"><span data-stu-id="61c3e-117">Details</span></span>  
  
|<span data-ttu-id="61c3e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="61c3e-118">Data Item Name</span></span>|<span data-ttu-id="61c3e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="61c3e-119">Data Item Type</span></span>|<span data-ttu-id="61c3e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61c3e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="61c3e-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="61c3e-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="61c3e-122">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="61c3e-122">The workflow application id</span></span>|  
|<span data-ttu-id="61c3e-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="61c3e-123">Exception</span></span>|`xs:string`|<span data-ttu-id="61c3e-124">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="61c3e-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="61c3e-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="61c3e-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="61c3e-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="61c3e-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
