---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510379"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="e0a15-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="e0a15-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e0a15-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e0a15-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0a15-104">ID</span><span class="sxs-lookup"><span data-stu-id="e0a15-104">ID</span></span>|<span data-ttu-id="e0a15-105">1012</span><span class="sxs-lookup"><span data-stu-id="e0a15-105">1012</span></span>|  
|<span data-ttu-id="e0a15-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e0a15-106">Keywords</span></span>|<span data-ttu-id="e0a15-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e0a15-107">WFRuntime</span></span>|  
|<span data-ttu-id="e0a15-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e0a15-108">Level</span></span>|<span data-ttu-id="e0a15-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="e0a15-109">Verbose</span></span>|  
|<span data-ttu-id="e0a15-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e0a15-110">Channel</span></span>|<span data-ttu-id="e0a15-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e0a15-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0a15-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a15-112">Description</span></span>  
 <span data-ttu-id="e0a15-113">Gibt an, dass ein ExecuteActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="e0a15-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0a15-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="e0a15-114">Message</span></span>  
 <span data-ttu-id="e0a15-115">Die Ausführung eines ExecuteActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="e0a15-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0a15-116">Details</span><span class="sxs-lookup"><span data-stu-id="e0a15-116">Details</span></span>  
  
|<span data-ttu-id="e0a15-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e0a15-117">Data Item Name</span></span>|<span data-ttu-id="e0a15-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e0a15-118">Data Item Type</span></span>|<span data-ttu-id="e0a15-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0a15-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0a15-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="e0a15-120">Activity</span></span>|<span data-ttu-id="e0a15-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0a15-121">xs:string</span></span>|<span data-ttu-id="e0a15-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e0a15-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e0a15-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e0a15-123">DisplayName</span></span>|<span data-ttu-id="e0a15-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0a15-124">xs:string</span></span>|<span data-ttu-id="e0a15-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e0a15-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e0a15-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e0a15-126">InstanceId</span></span>|<span data-ttu-id="e0a15-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0a15-127">xs:string</span></span>|<span data-ttu-id="e0a15-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e0a15-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e0a15-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0a15-129">AppDomain</span></span>|<span data-ttu-id="e0a15-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0a15-130">xs:string</span></span>|<span data-ttu-id="e0a15-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e0a15-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
