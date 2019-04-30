---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924240"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="aa787-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="aa787-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="aa787-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa787-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa787-104">ID</span><span class="sxs-lookup"><span data-stu-id="aa787-104">ID</span></span>|<span data-ttu-id="aa787-105">1033</span><span class="sxs-lookup"><span data-stu-id="aa787-105">1033</span></span>|  
|<span data-ttu-id="aa787-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="aa787-106">Keywords</span></span>|<span data-ttu-id="aa787-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aa787-107">WFRuntime</span></span>|  
|<span data-ttu-id="aa787-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="aa787-108">Level</span></span>|<span data-ttu-id="aa787-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="aa787-109">Verbose</span></span>|  
|<span data-ttu-id="aa787-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="aa787-110">Channel</span></span>|<span data-ttu-id="aa787-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aa787-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa787-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa787-112">Description</span></span>  
 <span data-ttu-id="aa787-113">Gibt an, dass ein RuntimeWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="aa787-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa787-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="aa787-114">Message</span></span>  
 <span data-ttu-id="aa787-115">Die Ausführung eines Laufzeitarbeitselements für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="aa787-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa787-116">Details</span><span class="sxs-lookup"><span data-stu-id="aa787-116">Details</span></span>  
  
|<span data-ttu-id="aa787-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="aa787-117">Data Item Name</span></span>|<span data-ttu-id="aa787-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="aa787-118">Data Item Type</span></span>|<span data-ttu-id="aa787-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa787-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa787-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="aa787-120">Activity</span></span>|<span data-ttu-id="aa787-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa787-121">xs:string</span></span>|<span data-ttu-id="aa787-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa787-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="aa787-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="aa787-123">DisplayName</span></span>|<span data-ttu-id="aa787-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa787-124">xs:string</span></span>|<span data-ttu-id="aa787-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa787-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="aa787-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="aa787-126">InstanceId</span></span>|<span data-ttu-id="aa787-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa787-127">xs:string</span></span>|<span data-ttu-id="aa787-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="aa787-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="aa787-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa787-129">AppDomain</span></span>|<span data-ttu-id="aa787-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa787-130">xs:string</span></span>|<span data-ttu-id="aa787-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aa787-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
