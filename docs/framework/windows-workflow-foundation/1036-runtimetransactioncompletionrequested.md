---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294260"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="b85c3-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="b85c3-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="b85c3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b85c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b85c3-104">id</span><span class="sxs-lookup"><span data-stu-id="b85c3-104">ID</span></span>|<span data-ttu-id="b85c3-105">1036</span><span class="sxs-lookup"><span data-stu-id="b85c3-105">1036</span></span>|  
|<span data-ttu-id="b85c3-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="b85c3-106">Keywords</span></span>|<span data-ttu-id="b85c3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b85c3-107">WFRuntime</span></span>|  
|<span data-ttu-id="b85c3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b85c3-108">Level</span></span>|<span data-ttu-id="b85c3-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="b85c3-109">Verbose</span></span>|  
|<span data-ttu-id="b85c3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b85c3-110">Channel</span></span>|<span data-ttu-id="b85c3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b85c3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b85c3-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b85c3-112">Description</span></span>  

 <span data-ttu-id="b85c3-113">Gibt an, dass eine Aktivität den Abschluss der Ablauftransaktion geplant hat.</span><span class="sxs-lookup"><span data-stu-id="b85c3-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b85c3-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="b85c3-114">Message</span></span>  

 <span data-ttu-id="b85c3-115">Die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat den Abschluss der Laufzeittransaktion geplant.</span><span class="sxs-lookup"><span data-stu-id="b85c3-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b85c3-116">Details</span><span class="sxs-lookup"><span data-stu-id="b85c3-116">Details</span></span>  
  
|<span data-ttu-id="b85c3-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b85c3-117">Data Item Name</span></span>|<span data-ttu-id="b85c3-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b85c3-118">Data Item Type</span></span>|<span data-ttu-id="b85c3-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b85c3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b85c3-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="b85c3-120">Activity</span></span>|<span data-ttu-id="b85c3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b85c3-121">xs:string</span></span>|<span data-ttu-id="b85c3-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b85c3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b85c3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b85c3-123">DisplayName</span></span>|<span data-ttu-id="b85c3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b85c3-124">xs:string</span></span>|<span data-ttu-id="b85c3-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b85c3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b85c3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b85c3-126">InstanceId</span></span>|<span data-ttu-id="b85c3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b85c3-127">xs:string</span></span>|<span data-ttu-id="b85c3-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b85c3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b85c3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b85c3-129">AppDomain</span></span>|<span data-ttu-id="b85c3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b85c3-130">xs:string</span></span>|<span data-ttu-id="b85c3-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b85c3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
