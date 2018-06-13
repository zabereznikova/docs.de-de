---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509794"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="ff709-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="ff709-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="ff709-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ff709-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff709-104">ID</span><span class="sxs-lookup"><span data-stu-id="ff709-104">ID</span></span>|<span data-ttu-id="ff709-105">1001</span><span class="sxs-lookup"><span data-stu-id="ff709-105">1001</span></span>|  
|<span data-ttu-id="ff709-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ff709-106">Keywords</span></span>|<span data-ttu-id="ff709-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ff709-107">WFRuntime</span></span>|  
|<span data-ttu-id="ff709-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ff709-108">Level</span></span>|<span data-ttu-id="ff709-109">Information</span><span class="sxs-lookup"><span data-stu-id="ff709-109">Information</span></span>|  
|<span data-ttu-id="ff709-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ff709-110">Channel</span></span>|<span data-ttu-id="ff709-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ff709-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff709-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff709-112">Description</span></span>  
 <span data-ttu-id="ff709-113">Gibt an, dass eine Workflowanwendung im Closed-Zustand beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ff709-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff709-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ff709-114">Message</span></span>  
 <span data-ttu-id="ff709-115">WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Closed' abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ff709-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff709-116">Details</span><span class="sxs-lookup"><span data-stu-id="ff709-116">Details</span></span>  
  
|<span data-ttu-id="ff709-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ff709-117">Data Item Name</span></span>|<span data-ttu-id="ff709-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ff709-118">Data Item Type</span></span>|<span data-ttu-id="ff709-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff709-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff709-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ff709-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="ff709-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="ff709-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="ff709-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ff709-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ff709-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ff709-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
