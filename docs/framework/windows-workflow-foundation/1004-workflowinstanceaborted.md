---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d1eaf3cf107a6b5e244cc2d9372ee68d387ef6c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510665"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="f6b10-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="f6b10-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="f6b10-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f6b10-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6b10-104">ID</span><span class="sxs-lookup"><span data-stu-id="f6b10-104">ID</span></span>|<span data-ttu-id="f6b10-105">1004</span><span class="sxs-lookup"><span data-stu-id="f6b10-105">1004</span></span>|  
|<span data-ttu-id="f6b10-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f6b10-106">Keywords</span></span>|<span data-ttu-id="f6b10-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f6b10-107">WFRuntime</span></span>|  
|<span data-ttu-id="f6b10-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f6b10-108">Level</span></span>|<span data-ttu-id="f6b10-109">Information</span><span class="sxs-lookup"><span data-stu-id="f6b10-109">Information</span></span>|  
|<span data-ttu-id="f6b10-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f6b10-110">Channel</span></span>|<span data-ttu-id="f6b10-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f6b10-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f6b10-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6b10-112">Description</span></span>  
 <span data-ttu-id="f6b10-113">Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="f6b10-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f6b10-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f6b10-114">Message</span></span>  
 <span data-ttu-id="f6b10-115">WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="f6b10-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f6b10-116">Details</span><span class="sxs-lookup"><span data-stu-id="f6b10-116">Details</span></span>  
  
|<span data-ttu-id="f6b10-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f6b10-117">Data Item Name</span></span>|<span data-ttu-id="f6b10-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f6b10-118">Data Item Type</span></span>|<span data-ttu-id="f6b10-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6b10-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f6b10-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f6b10-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f6b10-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="f6b10-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f6b10-122">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="f6b10-122">Exception</span></span>|`xs:string`|<span data-ttu-id="f6b10-123">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f6b10-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="f6b10-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f6b10-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f6b10-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f6b10-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
