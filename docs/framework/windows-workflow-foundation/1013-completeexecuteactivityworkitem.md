---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925189"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="07447-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="07447-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="07447-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="07447-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07447-104">ID</span><span class="sxs-lookup"><span data-stu-id="07447-104">ID</span></span>|<span data-ttu-id="07447-105">1013</span><span class="sxs-lookup"><span data-stu-id="07447-105">1013</span></span>|  
|<span data-ttu-id="07447-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="07447-106">Keywords</span></span>|<span data-ttu-id="07447-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="07447-107">WFRuntime</span></span>|  
|<span data-ttu-id="07447-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="07447-108">Level</span></span>|<span data-ttu-id="07447-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="07447-109">Verbose</span></span>|  
|<span data-ttu-id="07447-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="07447-110">Channel</span></span>|<span data-ttu-id="07447-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="07447-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07447-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07447-112">Description</span></span>  
 <span data-ttu-id="07447-113">Gibt an, dass ein ExecuteActivityWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="07447-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="07447-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="07447-114">Message</span></span>  
 <span data-ttu-id="07447-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="07447-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07447-116">Details</span><span class="sxs-lookup"><span data-stu-id="07447-116">Details</span></span>  
  
|<span data-ttu-id="07447-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="07447-117">Data Item Name</span></span>|<span data-ttu-id="07447-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="07447-118">Data Item Type</span></span>|<span data-ttu-id="07447-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07447-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07447-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="07447-120">Activity</span></span>|<span data-ttu-id="07447-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="07447-121">xs:string</span></span>|<span data-ttu-id="07447-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07447-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="07447-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="07447-123">DisplayName</span></span>|<span data-ttu-id="07447-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="07447-124">xs:string</span></span>|<span data-ttu-id="07447-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07447-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="07447-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="07447-126">InstanceId</span></span>|<span data-ttu-id="07447-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="07447-127">xs:string</span></span>|<span data-ttu-id="07447-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07447-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="07447-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07447-129">AppDomain</span></span>|<span data-ttu-id="07447-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="07447-130">xs:string</span></span>|<span data-ttu-id="07447-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="07447-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
