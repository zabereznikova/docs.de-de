---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509560"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="d42cd-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="d42cd-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="d42cd-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d42cd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d42cd-104">ID</span><span class="sxs-lookup"><span data-stu-id="d42cd-104">ID</span></span>|<span data-ttu-id="d42cd-105">1008</span><span class="sxs-lookup"><span data-stu-id="d42cd-105">1008</span></span>|  
|<span data-ttu-id="d42cd-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d42cd-106">Keywords</span></span>|<span data-ttu-id="d42cd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d42cd-107">WFRuntime</span></span>|  
|<span data-ttu-id="d42cd-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d42cd-108">Level</span></span>|<span data-ttu-id="d42cd-109">Information</span><span class="sxs-lookup"><span data-stu-id="d42cd-109">Information</span></span>|  
|<span data-ttu-id="d42cd-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d42cd-110">Channel</span></span>|<span data-ttu-id="d42cd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d42cd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d42cd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d42cd-112">Description</span></span>  
 <span data-ttu-id="d42cd-113">Gibt an, dass eine Workflowanwendung entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="d42cd-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d42cd-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d42cd-114">Message</span></span>  
 <span data-ttu-id="d42cd-115">WorkflowInstance-ID: '%1 ' wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="d42cd-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d42cd-116">Details</span><span class="sxs-lookup"><span data-stu-id="d42cd-116">Details</span></span>  
  
|<span data-ttu-id="d42cd-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d42cd-117">Data Item Name</span></span>|<span data-ttu-id="d42cd-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d42cd-118">Data Item Type</span></span>|<span data-ttu-id="d42cd-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d42cd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d42cd-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="d42cd-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="d42cd-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="d42cd-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="d42cd-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d42cd-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d42cd-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d42cd-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
