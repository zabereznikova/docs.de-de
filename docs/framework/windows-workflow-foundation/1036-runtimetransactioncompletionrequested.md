---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510392"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="6f39b-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="6f39b-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="6f39b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6f39b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f39b-104">ID</span><span class="sxs-lookup"><span data-stu-id="6f39b-104">ID</span></span>|<span data-ttu-id="6f39b-105">1036</span><span class="sxs-lookup"><span data-stu-id="6f39b-105">1036</span></span>|  
|<span data-ttu-id="6f39b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6f39b-106">Keywords</span></span>|<span data-ttu-id="6f39b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6f39b-107">WFRuntime</span></span>|  
|<span data-ttu-id="6f39b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6f39b-108">Level</span></span>|<span data-ttu-id="6f39b-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="6f39b-109">Verbose</span></span>|  
|<span data-ttu-id="6f39b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6f39b-110">Channel</span></span>|<span data-ttu-id="6f39b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6f39b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6f39b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f39b-112">Description</span></span>  
 <span data-ttu-id="6f39b-113">Gibt an, dass eine Aktivität den Abschluss der Ablauftransaktion geplant hat.</span><span class="sxs-lookup"><span data-stu-id="6f39b-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6f39b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="6f39b-114">Message</span></span>  
 <span data-ttu-id="6f39b-115">Die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat den Abschluss der Laufzeittransaktion geplant.</span><span class="sxs-lookup"><span data-stu-id="6f39b-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6f39b-116">Details</span><span class="sxs-lookup"><span data-stu-id="6f39b-116">Details</span></span>  
  
|<span data-ttu-id="6f39b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6f39b-117">Data Item Name</span></span>|<span data-ttu-id="6f39b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6f39b-118">Data Item Type</span></span>|<span data-ttu-id="6f39b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f39b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6f39b-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="6f39b-120">Activity</span></span>|<span data-ttu-id="6f39b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f39b-121">xs:string</span></span>|<span data-ttu-id="6f39b-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6f39b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="6f39b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6f39b-123">DisplayName</span></span>|<span data-ttu-id="6f39b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f39b-124">xs:string</span></span>|<span data-ttu-id="6f39b-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6f39b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="6f39b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="6f39b-126">InstanceId</span></span>|<span data-ttu-id="6f39b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f39b-127">xs:string</span></span>|<span data-ttu-id="6f39b-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6f39b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="6f39b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6f39b-129">AppDomain</span></span>|<span data-ttu-id="6f39b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f39b-130">xs:string</span></span>|<span data-ttu-id="6f39b-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6f39b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
