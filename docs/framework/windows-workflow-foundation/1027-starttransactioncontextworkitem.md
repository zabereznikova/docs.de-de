---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510808"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="fe3ae-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="fe3ae-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fe3ae-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fe3ae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe3ae-104">ID</span><span class="sxs-lookup"><span data-stu-id="fe3ae-104">ID</span></span>|<span data-ttu-id="fe3ae-105">1027</span><span class="sxs-lookup"><span data-stu-id="fe3ae-105">1027</span></span>|  
|<span data-ttu-id="fe3ae-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fe3ae-106">Keywords</span></span>|<span data-ttu-id="fe3ae-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fe3ae-107">WFRuntime</span></span>|  
|<span data-ttu-id="fe3ae-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fe3ae-108">Level</span></span>|<span data-ttu-id="fe3ae-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="fe3ae-109">Verbose</span></span>|  
|<span data-ttu-id="fe3ae-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fe3ae-110">Channel</span></span>|<span data-ttu-id="fe3ae-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fe3ae-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe3ae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3ae-112">Description</span></span>  
 <span data-ttu-id="fe3ae-113">Gibt an, dass ein TransactionContextWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="fe3ae-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe3ae-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="fe3ae-114">Message</span></span>  
 <span data-ttu-id="fe3ae-115">Die Ausführung von TransactionContextWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="fe3ae-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe3ae-116">Details</span><span class="sxs-lookup"><span data-stu-id="fe3ae-116">Details</span></span>  
  
|<span data-ttu-id="fe3ae-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fe3ae-117">Data Item Name</span></span>|<span data-ttu-id="fe3ae-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fe3ae-118">Data Item Type</span></span>|<span data-ttu-id="fe3ae-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3ae-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe3ae-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="fe3ae-120">Activity</span></span>|<span data-ttu-id="fe3ae-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe3ae-121">xs:string</span></span>|<span data-ttu-id="fe3ae-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fe3ae-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fe3ae-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fe3ae-123">DisplayName</span></span>|<span data-ttu-id="fe3ae-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe3ae-124">xs:string</span></span>|<span data-ttu-id="fe3ae-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fe3ae-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fe3ae-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fe3ae-126">InstanceId</span></span>|<span data-ttu-id="fe3ae-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe3ae-127">xs:string</span></span>|<span data-ttu-id="fe3ae-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="fe3ae-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fe3ae-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe3ae-129">AppDomain</span></span>|<span data-ttu-id="fe3ae-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe3ae-130">xs:string</span></span>|<span data-ttu-id="fe3ae-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fe3ae-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
