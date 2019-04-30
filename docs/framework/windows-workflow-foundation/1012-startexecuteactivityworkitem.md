---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924578"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="f85ec-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f85ec-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f85ec-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f85ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f85ec-104">ID</span><span class="sxs-lookup"><span data-stu-id="f85ec-104">ID</span></span>|<span data-ttu-id="f85ec-105">1012</span><span class="sxs-lookup"><span data-stu-id="f85ec-105">1012</span></span>|  
|<span data-ttu-id="f85ec-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f85ec-106">Keywords</span></span>|<span data-ttu-id="f85ec-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f85ec-107">WFRuntime</span></span>|  
|<span data-ttu-id="f85ec-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f85ec-108">Level</span></span>|<span data-ttu-id="f85ec-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="f85ec-109">Verbose</span></span>|  
|<span data-ttu-id="f85ec-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f85ec-110">Channel</span></span>|<span data-ttu-id="f85ec-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f85ec-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f85ec-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f85ec-112">Description</span></span>  
 <span data-ttu-id="f85ec-113">Gibt an, dass ein ExecuteActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="f85ec-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f85ec-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f85ec-114">Message</span></span>  
 <span data-ttu-id="f85ec-115">Die Ausführung eines ExecuteActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="f85ec-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f85ec-116">Details</span><span class="sxs-lookup"><span data-stu-id="f85ec-116">Details</span></span>  
  
|<span data-ttu-id="f85ec-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f85ec-117">Data Item Name</span></span>|<span data-ttu-id="f85ec-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f85ec-118">Data Item Type</span></span>|<span data-ttu-id="f85ec-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f85ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f85ec-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="f85ec-120">Activity</span></span>|<span data-ttu-id="f85ec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f85ec-121">xs:string</span></span>|<span data-ttu-id="f85ec-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f85ec-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f85ec-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f85ec-123">DisplayName</span></span>|<span data-ttu-id="f85ec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f85ec-124">xs:string</span></span>|<span data-ttu-id="f85ec-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f85ec-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f85ec-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f85ec-126">InstanceId</span></span>|<span data-ttu-id="f85ec-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f85ec-127">xs:string</span></span>|<span data-ttu-id="f85ec-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f85ec-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f85ec-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f85ec-129">AppDomain</span></span>|<span data-ttu-id="f85ec-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f85ec-130">xs:string</span></span>|<span data-ttu-id="f85ec-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f85ec-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
