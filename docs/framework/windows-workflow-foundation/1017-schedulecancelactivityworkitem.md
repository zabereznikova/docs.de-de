---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924487"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="bd5f8-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="bd5f8-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bd5f8-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bd5f8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd5f8-104">ID</span><span class="sxs-lookup"><span data-stu-id="bd5f8-104">ID</span></span>|<span data-ttu-id="bd5f8-105">1017</span><span class="sxs-lookup"><span data-stu-id="bd5f8-105">1017</span></span>|  
|<span data-ttu-id="bd5f8-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bd5f8-106">Keywords</span></span>|<span data-ttu-id="bd5f8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bd5f8-107">WFRuntime</span></span>|  
|<span data-ttu-id="bd5f8-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bd5f8-108">Level</span></span>|<span data-ttu-id="bd5f8-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="bd5f8-109">Verbose</span></span>|  
|<span data-ttu-id="bd5f8-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bd5f8-110">Channel</span></span>|<span data-ttu-id="bd5f8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bd5f8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bd5f8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd5f8-112">Description</span></span>  
 <span data-ttu-id="bd5f8-113">Gibt an, dass ein CancelActivityWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="bd5f8-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bd5f8-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="bd5f8-114">Message</span></span>  
 <span data-ttu-id="bd5f8-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CancelActivityWorkItem geplant.</span><span class="sxs-lookup"><span data-stu-id="bd5f8-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bd5f8-116">Details</span><span class="sxs-lookup"><span data-stu-id="bd5f8-116">Details</span></span>  
  
|<span data-ttu-id="bd5f8-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bd5f8-117">Data Item Name</span></span>|<span data-ttu-id="bd5f8-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bd5f8-118">Data Item Type</span></span>|<span data-ttu-id="bd5f8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd5f8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bd5f8-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="bd5f8-120">Activity</span></span>|<span data-ttu-id="bd5f8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5f8-121">xs:string</span></span>|<span data-ttu-id="bd5f8-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bd5f8-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bd5f8-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bd5f8-123">DisplayName</span></span>|<span data-ttu-id="bd5f8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5f8-124">xs:string</span></span>|<span data-ttu-id="bd5f8-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bd5f8-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bd5f8-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bd5f8-126">InstanceId</span></span>|<span data-ttu-id="bd5f8-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5f8-127">xs:string</span></span>|<span data-ttu-id="bd5f8-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bd5f8-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bd5f8-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bd5f8-129">AppDomain</span></span>|<span data-ttu-id="bd5f8-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5f8-130">xs:string</span></span>|<span data-ttu-id="bd5f8-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bd5f8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
