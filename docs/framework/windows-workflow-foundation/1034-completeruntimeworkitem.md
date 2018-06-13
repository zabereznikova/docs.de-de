---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: bd49c608a8f6a6caab6975850507a00a2c0edb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509690"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="81e3a-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="81e3a-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="81e3a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="81e3a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81e3a-104">ID</span><span class="sxs-lookup"><span data-stu-id="81e3a-104">ID</span></span>|<span data-ttu-id="81e3a-105">1034</span><span class="sxs-lookup"><span data-stu-id="81e3a-105">1034</span></span>|  
|<span data-ttu-id="81e3a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="81e3a-106">Keywords</span></span>|<span data-ttu-id="81e3a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="81e3a-107">WFRuntime</span></span>|  
|<span data-ttu-id="81e3a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="81e3a-108">Level</span></span>|<span data-ttu-id="81e3a-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="81e3a-109">Verbose</span></span>|  
|<span data-ttu-id="81e3a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="81e3a-110">Channel</span></span>|<span data-ttu-id="81e3a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="81e3a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="81e3a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81e3a-112">Description</span></span>  
 <span data-ttu-id="81e3a-113">Gibt an, dass ein RuntimeWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="81e3a-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="81e3a-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="81e3a-114">Message</span></span>  
 <span data-ttu-id="81e3a-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine Laufzeitarbeitsaufgabe abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="81e3a-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="81e3a-116">Details</span><span class="sxs-lookup"><span data-stu-id="81e3a-116">Details</span></span>  
  
|<span data-ttu-id="81e3a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="81e3a-117">Data Item Name</span></span>|<span data-ttu-id="81e3a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="81e3a-118">Data Item Type</span></span>|<span data-ttu-id="81e3a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81e3a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="81e3a-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="81e3a-120">Activity</span></span>|<span data-ttu-id="81e3a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="81e3a-121">xs:string</span></span>|<span data-ttu-id="81e3a-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="81e3a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="81e3a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="81e3a-123">DisplayName</span></span>|<span data-ttu-id="81e3a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="81e3a-124">xs:string</span></span>|<span data-ttu-id="81e3a-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="81e3a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="81e3a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="81e3a-126">InstanceId</span></span>|<span data-ttu-id="81e3a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="81e3a-127">xs:string</span></span>|<span data-ttu-id="81e3a-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="81e3a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="81e3a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="81e3a-129">AppDomain</span></span>|<span data-ttu-id="81e3a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="81e3a-130">xs:string</span></span>|<span data-ttu-id="81e3a-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="81e3a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
