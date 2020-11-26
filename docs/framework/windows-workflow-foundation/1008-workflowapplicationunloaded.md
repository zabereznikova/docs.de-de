---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239820"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="fe648-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="fe648-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="fe648-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fe648-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe648-104">id</span><span class="sxs-lookup"><span data-stu-id="fe648-104">ID</span></span>|<span data-ttu-id="fe648-105">1008</span><span class="sxs-lookup"><span data-stu-id="fe648-105">1008</span></span>|  
|<span data-ttu-id="fe648-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="fe648-106">Keywords</span></span>|<span data-ttu-id="fe648-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fe648-107">WFRuntime</span></span>|  
|<span data-ttu-id="fe648-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fe648-108">Level</span></span>|<span data-ttu-id="fe648-109">Information</span><span class="sxs-lookup"><span data-stu-id="fe648-109">Information</span></span>|  
|<span data-ttu-id="fe648-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fe648-110">Channel</span></span>|<span data-ttu-id="fe648-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fe648-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe648-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe648-112">Description</span></span>  

 <span data-ttu-id="fe648-113">Gibt an, dass eine Workflowanwendung entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fe648-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe648-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="fe648-114">Message</span></span>  

 <span data-ttu-id="fe648-115">WorkflowInstance-ID: '%1 ' wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="fe648-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe648-116">Details</span><span class="sxs-lookup"><span data-stu-id="fe648-116">Details</span></span>  
  
|<span data-ttu-id="fe648-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fe648-117">Data Item Name</span></span>|<span data-ttu-id="fe648-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fe648-118">Data Item Type</span></span>|<span data-ttu-id="fe648-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe648-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe648-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fe648-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="fe648-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="fe648-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="fe648-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe648-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fe648-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fe648-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
