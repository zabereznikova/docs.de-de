---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 654f961088c371ab53e4a81f40e3c63335efb1a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239587"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="ea0d4-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ea0d4-102">1013 - CompleteExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="ea0d4-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ea0d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea0d4-104">id</span><span class="sxs-lookup"><span data-stu-id="ea0d4-104">ID</span></span>|<span data-ttu-id="ea0d4-105">1013</span><span class="sxs-lookup"><span data-stu-id="ea0d4-105">1013</span></span>|  
|<span data-ttu-id="ea0d4-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ea0d4-106">Keywords</span></span>|<span data-ttu-id="ea0d4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ea0d4-107">WFRuntime</span></span>|  
|<span data-ttu-id="ea0d4-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ea0d4-108">Level</span></span>|<span data-ttu-id="ea0d4-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="ea0d4-109">Verbose</span></span>|  
|<span data-ttu-id="ea0d4-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ea0d4-110">Channel</span></span>|<span data-ttu-id="ea0d4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ea0d4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ea0d4-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea0d4-112">Description</span></span>  

 <span data-ttu-id="ea0d4-113">Gibt an, dass ein ExecuteActivityWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ea0d4-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="ea0d4-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="ea0d4-114">Message</span></span>  

 <span data-ttu-id="ea0d4-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ea0d4-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ea0d4-116">Details</span><span class="sxs-lookup"><span data-stu-id="ea0d4-116">Details</span></span>  
  
|<span data-ttu-id="ea0d4-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ea0d4-117">Data Item Name</span></span>|<span data-ttu-id="ea0d4-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ea0d4-118">Data Item Type</span></span>|<span data-ttu-id="ea0d4-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea0d4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ea0d4-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="ea0d4-120">Activity</span></span>|<span data-ttu-id="ea0d4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea0d4-121">xs:string</span></span>|<span data-ttu-id="ea0d4-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ea0d4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ea0d4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ea0d4-123">DisplayName</span></span>|<span data-ttu-id="ea0d4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea0d4-124">xs:string</span></span>|<span data-ttu-id="ea0d4-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ea0d4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ea0d4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ea0d4-126">InstanceId</span></span>|<span data-ttu-id="ea0d4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea0d4-127">xs:string</span></span>|<span data-ttu-id="ea0d4-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ea0d4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ea0d4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ea0d4-129">AppDomain</span></span>|<span data-ttu-id="ea0d4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea0d4-130">xs:string</span></span>|<span data-ttu-id="ea0d4-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ea0d4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
