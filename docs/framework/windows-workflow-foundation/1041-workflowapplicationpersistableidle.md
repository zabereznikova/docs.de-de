---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924188"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="f594b-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="f594b-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="f594b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f594b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f594b-104">ID</span><span class="sxs-lookup"><span data-stu-id="f594b-104">ID</span></span>|<span data-ttu-id="f594b-105">1041</span><span class="sxs-lookup"><span data-stu-id="f594b-105">1041</span></span>|  
|<span data-ttu-id="f594b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f594b-106">Keywords</span></span>|<span data-ttu-id="f594b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f594b-107">WFRuntime</span></span>|  
|<span data-ttu-id="f594b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f594b-108">Level</span></span>|<span data-ttu-id="f594b-109">Information</span><span class="sxs-lookup"><span data-stu-id="f594b-109">Information</span></span>|  
|<span data-ttu-id="f594b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f594b-110">Channel</span></span>|<span data-ttu-id="f594b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f594b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f594b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f594b-112">Description</span></span>  
 <span data-ttu-id="f594b-113">Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="f594b-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="f594b-114">Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f594b-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f594b-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="f594b-115">Message</span></span>  
 <span data-ttu-id="f594b-116">WorkflowApplication-Id: "%1" ist im Leerlauf und dauerhaft.</span><span class="sxs-lookup"><span data-stu-id="f594b-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="f594b-117">Die folgende Aktion wird ausgeführt: %2.</span><span class="sxs-lookup"><span data-stu-id="f594b-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f594b-118">Details</span><span class="sxs-lookup"><span data-stu-id="f594b-118">Details</span></span>  
  
|<span data-ttu-id="f594b-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f594b-119">Data Item Name</span></span>|<span data-ttu-id="f594b-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f594b-120">Data Item Type</span></span>|<span data-ttu-id="f594b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f594b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f594b-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="f594b-122">WorkflowApplicationId</span></span>|<span data-ttu-id="f594b-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f594b-123">xs:string</span></span>|<span data-ttu-id="f594b-124">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="f594b-124">The workflow application id</span></span>|  
|<span data-ttu-id="f594b-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="f594b-125">ActionTaken</span></span>|<span data-ttu-id="f594b-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f594b-126">xs:string</span></span>|<span data-ttu-id="f594b-127">Die Aktion, die für die Workflowanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f594b-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="f594b-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f594b-128">AppDomain</span></span>|<span data-ttu-id="f594b-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f594b-129">xs:string</span></span>|<span data-ttu-id="f594b-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f594b-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
