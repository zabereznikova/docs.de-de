---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509614"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="7f7c0-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="7f7c0-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7f7c0-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7f7c0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f7c0-104">ID</span><span class="sxs-lookup"><span data-stu-id="7f7c0-104">ID</span></span>|<span data-ttu-id="7f7c0-105">1011</span><span class="sxs-lookup"><span data-stu-id="7f7c0-105">1011</span></span>|  
|<span data-ttu-id="7f7c0-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7f7c0-106">Keywords</span></span>|<span data-ttu-id="7f7c0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7f7c0-107">WFRuntime</span></span>|  
|<span data-ttu-id="7f7c0-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7f7c0-108">Level</span></span>|<span data-ttu-id="7f7c0-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="7f7c0-109">Verbose</span></span>|  
|<span data-ttu-id="7f7c0-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7f7c0-110">Channel</span></span>|<span data-ttu-id="7f7c0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7f7c0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7f7c0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f7c0-112">Description</span></span>  
 <span data-ttu-id="7f7c0-113">Gibt an, dass eine ExecuteActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="7f7c0-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7f7c0-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="7f7c0-114">Message</span></span>  
 <span data-ttu-id="7f7c0-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="7f7c0-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7f7c0-116">Details</span><span class="sxs-lookup"><span data-stu-id="7f7c0-116">Details</span></span>  
  
|<span data-ttu-id="7f7c0-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7f7c0-117">Data Item Name</span></span>|<span data-ttu-id="7f7c0-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7f7c0-118">Data Item Type</span></span>|<span data-ttu-id="7f7c0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f7c0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7f7c0-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="7f7c0-120">Activity</span></span>|<span data-ttu-id="7f7c0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f7c0-121">xs:string</span></span>|<span data-ttu-id="7f7c0-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7f7c0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="7f7c0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7f7c0-123">DisplayName</span></span>|<span data-ttu-id="7f7c0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f7c0-124">xs:string</span></span>|<span data-ttu-id="7f7c0-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7f7c0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="7f7c0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7f7c0-126">InstanceId</span></span>|<span data-ttu-id="7f7c0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f7c0-127">xs:string</span></span>|<span data-ttu-id="7f7c0-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7f7c0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7f7c0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7f7c0-129">AppDomain</span></span>|<span data-ttu-id="7f7c0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f7c0-130">xs:string</span></span>|<span data-ttu-id="7f7c0-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7f7c0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
