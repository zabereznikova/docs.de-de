---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42d22a7187adc712c0f236111cecac89dd59e2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="ecb01-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="ecb01-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="ecb01-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ecb01-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecb01-104">ID</span><span class="sxs-lookup"><span data-stu-id="ecb01-104">ID</span></span>|<span data-ttu-id="ecb01-105">1005</span><span class="sxs-lookup"><span data-stu-id="ecb01-105">1005</span></span>|  
|<span data-ttu-id="ecb01-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ecb01-106">Keywords</span></span>|<span data-ttu-id="ecb01-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ecb01-107">WFRuntime</span></span>|  
|<span data-ttu-id="ecb01-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ecb01-108">Level</span></span>|<span data-ttu-id="ecb01-109">Information</span><span class="sxs-lookup"><span data-stu-id="ecb01-109">Information</span></span>|  
|<span data-ttu-id="ecb01-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ecb01-110">Channel</span></span>|<span data-ttu-id="ecb01-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ecb01-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecb01-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecb01-112">Description</span></span>  
 <span data-ttu-id="ecb01-113">Gibt an, dass sich eine Workflowanwendung im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="ecb01-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecb01-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ecb01-114">Message</span></span>  
 <span data-ttu-id="ecb01-115">WorkflowApplication-ID: '%1 ' ist im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="ecb01-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecb01-116">Details</span><span class="sxs-lookup"><span data-stu-id="ecb01-116">Details</span></span>  
  
|<span data-ttu-id="ecb01-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ecb01-117">Data Item Name</span></span>|<span data-ttu-id="ecb01-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ecb01-118">Data Item Type</span></span>|<span data-ttu-id="ecb01-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecb01-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecb01-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ecb01-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="ecb01-121">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="ecb01-121">The workflow application id</span></span>|  
|<span data-ttu-id="ecb01-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ecb01-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ecb01-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ecb01-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
