---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510065"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="0658c-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="0658c-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0658c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0658c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0658c-104">ID</span><span class="sxs-lookup"><span data-stu-id="0658c-104">ID</span></span>|<span data-ttu-id="0658c-105">1033</span><span class="sxs-lookup"><span data-stu-id="0658c-105">1033</span></span>|  
|<span data-ttu-id="0658c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0658c-106">Keywords</span></span>|<span data-ttu-id="0658c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0658c-107">WFRuntime</span></span>|  
|<span data-ttu-id="0658c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0658c-108">Level</span></span>|<span data-ttu-id="0658c-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="0658c-109">Verbose</span></span>|  
|<span data-ttu-id="0658c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0658c-110">Channel</span></span>|<span data-ttu-id="0658c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0658c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0658c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0658c-112">Description</span></span>  
 <span data-ttu-id="0658c-113">Gibt an, dass ein RuntimeWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="0658c-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0658c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0658c-114">Message</span></span>  
 <span data-ttu-id="0658c-115">Die Ausführung einer Laufzeitarbeitsaufgabe für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="0658c-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0658c-116">Details</span><span class="sxs-lookup"><span data-stu-id="0658c-116">Details</span></span>  
  
|<span data-ttu-id="0658c-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0658c-117">Data Item Name</span></span>|<span data-ttu-id="0658c-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0658c-118">Data Item Type</span></span>|<span data-ttu-id="0658c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0658c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0658c-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="0658c-120">Activity</span></span>|<span data-ttu-id="0658c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0658c-121">xs:string</span></span>|<span data-ttu-id="0658c-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0658c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0658c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0658c-123">DisplayName</span></span>|<span data-ttu-id="0658c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0658c-124">xs:string</span></span>|<span data-ttu-id="0658c-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0658c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0658c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0658c-126">InstanceId</span></span>|<span data-ttu-id="0658c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0658c-127">xs:string</span></span>|<span data-ttu-id="0658c-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0658c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0658c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0658c-129">AppDomain</span></span>|<span data-ttu-id="0658c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0658c-130">xs:string</span></span>|<span data-ttu-id="0658c-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0658c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
