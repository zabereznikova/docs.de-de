---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: b9cfceb12d56f93c0f9726849e34f4333f1399ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239639"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="588c7-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="588c7-102">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="588c7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="588c7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="588c7-104">id</span><span class="sxs-lookup"><span data-stu-id="588c7-104">ID</span></span>|<span data-ttu-id="588c7-105">1012</span><span class="sxs-lookup"><span data-stu-id="588c7-105">1012</span></span>|  
|<span data-ttu-id="588c7-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="588c7-106">Keywords</span></span>|<span data-ttu-id="588c7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="588c7-107">WFRuntime</span></span>|  
|<span data-ttu-id="588c7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="588c7-108">Level</span></span>|<span data-ttu-id="588c7-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="588c7-109">Verbose</span></span>|  
|<span data-ttu-id="588c7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="588c7-110">Channel</span></span>|<span data-ttu-id="588c7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="588c7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="588c7-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="588c7-112">Description</span></span>  

 <span data-ttu-id="588c7-113">Gibt an, dass ein ExecuteActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="588c7-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="588c7-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="588c7-114">Message</span></span>  

 <span data-ttu-id="588c7-115">Die Ausführung eines ExecuteActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="588c7-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="588c7-116">Details</span><span class="sxs-lookup"><span data-stu-id="588c7-116">Details</span></span>  
  
|<span data-ttu-id="588c7-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="588c7-117">Data Item Name</span></span>|<span data-ttu-id="588c7-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="588c7-118">Data Item Type</span></span>|<span data-ttu-id="588c7-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="588c7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="588c7-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="588c7-120">Activity</span></span>|<span data-ttu-id="588c7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="588c7-121">xs:string</span></span>|<span data-ttu-id="588c7-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="588c7-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="588c7-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="588c7-123">DisplayName</span></span>|<span data-ttu-id="588c7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="588c7-124">xs:string</span></span>|<span data-ttu-id="588c7-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="588c7-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="588c7-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="588c7-126">InstanceId</span></span>|<span data-ttu-id="588c7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="588c7-127">xs:string</span></span>|<span data-ttu-id="588c7-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="588c7-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="588c7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="588c7-129">AppDomain</span></span>|<span data-ttu-id="588c7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="588c7-130">xs:string</span></span>|<span data-ttu-id="588c7-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="588c7-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
