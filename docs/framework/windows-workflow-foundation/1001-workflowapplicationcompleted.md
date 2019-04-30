---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008641"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="a6eca-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="a6eca-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="a6eca-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6eca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6eca-104">ID</span><span class="sxs-lookup"><span data-stu-id="a6eca-104">ID</span></span>|<span data-ttu-id="a6eca-105">1001</span><span class="sxs-lookup"><span data-stu-id="a6eca-105">1001</span></span>|  
|<span data-ttu-id="a6eca-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a6eca-106">Keywords</span></span>|<span data-ttu-id="a6eca-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a6eca-107">WFRuntime</span></span>|  
|<span data-ttu-id="a6eca-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a6eca-108">Level</span></span>|<span data-ttu-id="a6eca-109">Information</span><span class="sxs-lookup"><span data-stu-id="a6eca-109">Information</span></span>|  
|<span data-ttu-id="a6eca-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a6eca-110">Channel</span></span>|<span data-ttu-id="a6eca-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a6eca-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6eca-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6eca-112">Description</span></span>  
 <span data-ttu-id="a6eca-113">Gibt an, dass eine Workflowanwendung im Closed-Zustand beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a6eca-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6eca-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a6eca-114">Message</span></span>  
 <span data-ttu-id="a6eca-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Closed' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a6eca-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6eca-116">Details</span><span class="sxs-lookup"><span data-stu-id="a6eca-116">Details</span></span>  
  
|<span data-ttu-id="a6eca-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a6eca-117">Data Item Name</span></span>|<span data-ttu-id="a6eca-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a6eca-118">Data Item Type</span></span>|<span data-ttu-id="a6eca-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6eca-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6eca-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a6eca-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a6eca-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="a6eca-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a6eca-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a6eca-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a6eca-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6eca-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
