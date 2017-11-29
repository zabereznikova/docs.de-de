---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 297b3ad9a677d28d12d1b00fdaeec8ec94842263
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="b4f54-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="b4f54-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="b4f54-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b4f54-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4f54-104">ID</span><span class="sxs-lookup"><span data-stu-id="b4f54-104">ID</span></span>|<span data-ttu-id="b4f54-105">1008</span><span class="sxs-lookup"><span data-stu-id="b4f54-105">1008</span></span>|  
|<span data-ttu-id="b4f54-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b4f54-106">Keywords</span></span>|<span data-ttu-id="b4f54-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b4f54-107">WFRuntime</span></span>|  
|<span data-ttu-id="b4f54-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b4f54-108">Level</span></span>|<span data-ttu-id="b4f54-109">Information</span><span class="sxs-lookup"><span data-stu-id="b4f54-109">Information</span></span>|  
|<span data-ttu-id="b4f54-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b4f54-110">Channel</span></span>|<span data-ttu-id="b4f54-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b4f54-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4f54-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4f54-112">Description</span></span>  
 <span data-ttu-id="b4f54-113">Gibt an, dass eine Workflowanwendung entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b4f54-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4f54-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b4f54-114">Message</span></span>  
 <span data-ttu-id="b4f54-115">WorkflowInstance-ID: '%1 ' wurde entladen.</span><span class="sxs-lookup"><span data-stu-id="b4f54-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4f54-116">Details</span><span class="sxs-lookup"><span data-stu-id="b4f54-116">Details</span></span>  
  
|<span data-ttu-id="b4f54-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b4f54-117">Data Item Name</span></span>|<span data-ttu-id="b4f54-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b4f54-118">Data Item Type</span></span>|<span data-ttu-id="b4f54-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4f54-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4f54-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="b4f54-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="b4f54-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="b4f54-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="b4f54-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b4f54-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b4f54-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b4f54-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
