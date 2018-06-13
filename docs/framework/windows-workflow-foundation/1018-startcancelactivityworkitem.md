---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510652"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="0603b-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0603b-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0603b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0603b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0603b-104">ID</span><span class="sxs-lookup"><span data-stu-id="0603b-104">ID</span></span>|<span data-ttu-id="0603b-105">1018</span><span class="sxs-lookup"><span data-stu-id="0603b-105">1018</span></span>|  
|<span data-ttu-id="0603b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0603b-106">Keywords</span></span>|<span data-ttu-id="0603b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0603b-107">WFRuntime</span></span>|  
|<span data-ttu-id="0603b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0603b-108">Level</span></span>|<span data-ttu-id="0603b-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="0603b-109">Verbose</span></span>|  
|<span data-ttu-id="0603b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0603b-110">Channel</span></span>|<span data-ttu-id="0603b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0603b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0603b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0603b-112">Description</span></span>  
 <span data-ttu-id="0603b-113">Gibt an, dass ein CancelActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="0603b-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0603b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0603b-114">Message</span></span>  
 <span data-ttu-id="0603b-115">Die Ausführung einer CancelActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="0603b-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0603b-116">Details</span><span class="sxs-lookup"><span data-stu-id="0603b-116">Details</span></span>  
  
|<span data-ttu-id="0603b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0603b-117">Data Item Name</span></span>|<span data-ttu-id="0603b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0603b-118">Data Item Type</span></span>|<span data-ttu-id="0603b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0603b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0603b-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="0603b-120">Activity</span></span>|<span data-ttu-id="0603b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0603b-121">xs:string</span></span>|<span data-ttu-id="0603b-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0603b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0603b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0603b-123">DisplayName</span></span>|<span data-ttu-id="0603b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0603b-124">xs:string</span></span>|<span data-ttu-id="0603b-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0603b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0603b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0603b-126">InstanceId</span></span>|<span data-ttu-id="0603b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0603b-127">xs:string</span></span>|<span data-ttu-id="0603b-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0603b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0603b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0603b-129">AppDomain</span></span>|<span data-ttu-id="0603b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0603b-130">xs:string</span></span>|<span data-ttu-id="0603b-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0603b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
