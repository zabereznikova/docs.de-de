---
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 4c9ae5fd386fc93ea19578097aa4e0afdda527e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511055"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="ced04-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="ced04-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="ced04-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ced04-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ced04-104">ID</span><span class="sxs-lookup"><span data-stu-id="ced04-104">ID</span></span>|<span data-ttu-id="ced04-105">1104</span><span class="sxs-lookup"><span data-stu-id="ced04-105">1104</span></span>|  
|<span data-ttu-id="ced04-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ced04-106">Keywords</span></span>|<span data-ttu-id="ced04-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ced04-107">WFRuntime</span></span>|  
|<span data-ttu-id="ced04-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ced04-108">Level</span></span>|<span data-ttu-id="ced04-109">Information</span><span class="sxs-lookup"><span data-stu-id="ced04-109">Information</span></span>|  
|<span data-ttu-id="ced04-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ced04-110">Channel</span></span>|<span data-ttu-id="ced04-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ced04-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ced04-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ced04-112">Description</span></span>  
 <span data-ttu-id="ced04-113">Gibt an, dass eine Workflowaktivität fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ced04-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ced04-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ced04-114">Message</span></span>  
 <span data-ttu-id="ced04-115">WorkflowInstance-ID: '%1' E2E-Aktivität</span><span class="sxs-lookup"><span data-stu-id="ced04-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="ced04-116">Details</span><span class="sxs-lookup"><span data-stu-id="ced04-116">Details</span></span>  
  
|<span data-ttu-id="ced04-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ced04-117">Data Item Name</span></span>|<span data-ttu-id="ced04-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ced04-118">Data Item Type</span></span>|<span data-ttu-id="ced04-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ced04-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ced04-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ced04-120">WorkflowInstanceId</span></span>|<span data-ttu-id="ced04-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ced04-121">xs:string</span></span>|<span data-ttu-id="ced04-122">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="ced04-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="ced04-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ced04-123">AppDomain</span></span>|<span data-ttu-id="ced04-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ced04-124">xs:string</span></span>|<span data-ttu-id="ced04-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ced04-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
