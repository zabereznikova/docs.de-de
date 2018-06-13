---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509293"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="642b8-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="642b8-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="642b8-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="642b8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="642b8-104">ID</span><span class="sxs-lookup"><span data-stu-id="642b8-104">ID</span></span>|<span data-ttu-id="642b8-105">1005</span><span class="sxs-lookup"><span data-stu-id="642b8-105">1005</span></span>|  
|<span data-ttu-id="642b8-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="642b8-106">Keywords</span></span>|<span data-ttu-id="642b8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="642b8-107">WFRuntime</span></span>|  
|<span data-ttu-id="642b8-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="642b8-108">Level</span></span>|<span data-ttu-id="642b8-109">Information</span><span class="sxs-lookup"><span data-stu-id="642b8-109">Information</span></span>|  
|<span data-ttu-id="642b8-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="642b8-110">Channel</span></span>|<span data-ttu-id="642b8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="642b8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="642b8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="642b8-112">Description</span></span>  
 <span data-ttu-id="642b8-113">Gibt an, dass sich eine Workflowanwendung im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="642b8-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="642b8-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="642b8-114">Message</span></span>  
 <span data-ttu-id="642b8-115">WorkflowApplication-ID: '%1 ' ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="642b8-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="642b8-116">Details</span><span class="sxs-lookup"><span data-stu-id="642b8-116">Details</span></span>  
  
|<span data-ttu-id="642b8-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="642b8-117">Data Item Name</span></span>|<span data-ttu-id="642b8-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="642b8-118">Data Item Type</span></span>|<span data-ttu-id="642b8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="642b8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="642b8-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="642b8-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="642b8-121">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="642b8-121">The workflow application id</span></span>|  
|<span data-ttu-id="642b8-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="642b8-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="642b8-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="642b8-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
