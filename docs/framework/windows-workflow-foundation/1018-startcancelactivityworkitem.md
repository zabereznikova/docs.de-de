---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008862"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="bbe69-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="bbe69-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bbe69-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bbe69-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbe69-104">ID</span><span class="sxs-lookup"><span data-stu-id="bbe69-104">ID</span></span>|<span data-ttu-id="bbe69-105">1018</span><span class="sxs-lookup"><span data-stu-id="bbe69-105">1018</span></span>|  
|<span data-ttu-id="bbe69-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bbe69-106">Keywords</span></span>|<span data-ttu-id="bbe69-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bbe69-107">WFRuntime</span></span>|  
|<span data-ttu-id="bbe69-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bbe69-108">Level</span></span>|<span data-ttu-id="bbe69-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="bbe69-109">Verbose</span></span>|  
|<span data-ttu-id="bbe69-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bbe69-110">Channel</span></span>|<span data-ttu-id="bbe69-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bbe69-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bbe69-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbe69-112">Description</span></span>  
 <span data-ttu-id="bbe69-113">Gibt an, dass ein CancelActivityWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="bbe69-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bbe69-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="bbe69-114">Message</span></span>  
 <span data-ttu-id="bbe69-115">Die Ausführung einer CancelActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="bbe69-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bbe69-116">Details</span><span class="sxs-lookup"><span data-stu-id="bbe69-116">Details</span></span>  
  
|<span data-ttu-id="bbe69-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bbe69-117">Data Item Name</span></span>|<span data-ttu-id="bbe69-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bbe69-118">Data Item Type</span></span>|<span data-ttu-id="bbe69-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbe69-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bbe69-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="bbe69-120">Activity</span></span>|<span data-ttu-id="bbe69-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bbe69-121">xs:string</span></span>|<span data-ttu-id="bbe69-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bbe69-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bbe69-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bbe69-123">DisplayName</span></span>|<span data-ttu-id="bbe69-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bbe69-124">xs:string</span></span>|<span data-ttu-id="bbe69-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bbe69-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bbe69-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bbe69-126">InstanceId</span></span>|<span data-ttu-id="bbe69-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bbe69-127">xs:string</span></span>|<span data-ttu-id="bbe69-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bbe69-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bbe69-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bbe69-129">AppDomain</span></span>|<span data-ttu-id="bbe69-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bbe69-130">xs:string</span></span>|<span data-ttu-id="bbe69-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bbe69-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
