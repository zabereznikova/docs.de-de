---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982253"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="f1790-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f1790-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f1790-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f1790-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1790-104">ID</span><span class="sxs-lookup"><span data-stu-id="f1790-104">ID</span></span>|<span data-ttu-id="f1790-105">1011</span><span class="sxs-lookup"><span data-stu-id="f1790-105">1011</span></span>|  
|<span data-ttu-id="f1790-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f1790-106">Keywords</span></span>|<span data-ttu-id="f1790-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f1790-107">WFRuntime</span></span>|  
|<span data-ttu-id="f1790-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f1790-108">Level</span></span>|<span data-ttu-id="f1790-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="f1790-109">Verbose</span></span>|  
|<span data-ttu-id="f1790-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f1790-110">Channel</span></span>|<span data-ttu-id="f1790-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f1790-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f1790-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1790-112">Description</span></span>  
 <span data-ttu-id="f1790-113">Gibt an, dass eine ExecuteActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="f1790-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f1790-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f1790-114">Message</span></span>  
 <span data-ttu-id="f1790-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="f1790-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f1790-116">Details</span><span class="sxs-lookup"><span data-stu-id="f1790-116">Details</span></span>  
  
|<span data-ttu-id="f1790-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f1790-117">Data Item Name</span></span>|<span data-ttu-id="f1790-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f1790-118">Data Item Type</span></span>|<span data-ttu-id="f1790-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1790-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f1790-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="f1790-120">Activity</span></span>|<span data-ttu-id="f1790-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1790-121">xs:string</span></span>|<span data-ttu-id="f1790-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f1790-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f1790-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f1790-123">DisplayName</span></span>|<span data-ttu-id="f1790-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1790-124">xs:string</span></span>|<span data-ttu-id="f1790-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f1790-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f1790-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f1790-126">InstanceId</span></span>|<span data-ttu-id="f1790-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1790-127">xs:string</span></span>|<span data-ttu-id="f1790-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f1790-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f1790-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f1790-129">AppDomain</span></span>|<span data-ttu-id="f1790-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1790-130">xs:string</span></span>|<span data-ttu-id="f1790-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f1790-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
