---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: cb5671ce7a30a7096104ba0ca6c4f36bed6b93f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275231"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="3e80d-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="3e80d-102">1027 - StartTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="3e80d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3e80d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e80d-104">id</span><span class="sxs-lookup"><span data-stu-id="3e80d-104">ID</span></span>|<span data-ttu-id="3e80d-105">1027</span><span class="sxs-lookup"><span data-stu-id="3e80d-105">1027</span></span>|  
|<span data-ttu-id="3e80d-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="3e80d-106">Keywords</span></span>|<span data-ttu-id="3e80d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3e80d-107">WFRuntime</span></span>|  
|<span data-ttu-id="3e80d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3e80d-108">Level</span></span>|<span data-ttu-id="3e80d-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="3e80d-109">Verbose</span></span>|  
|<span data-ttu-id="3e80d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3e80d-110">Channel</span></span>|<span data-ttu-id="3e80d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3e80d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e80d-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e80d-112">Description</span></span>  

 <span data-ttu-id="3e80d-113">Gibt an, dass ein TransactionContextWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="3e80d-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e80d-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="3e80d-114">Message</span></span>  

 <span data-ttu-id="3e80d-115">Die Ausführung von TransactionContextWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="3e80d-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e80d-116">Details</span><span class="sxs-lookup"><span data-stu-id="3e80d-116">Details</span></span>  
  
|<span data-ttu-id="3e80d-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3e80d-117">Data Item Name</span></span>|<span data-ttu-id="3e80d-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3e80d-118">Data Item Type</span></span>|<span data-ttu-id="3e80d-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e80d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e80d-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="3e80d-120">Activity</span></span>|<span data-ttu-id="3e80d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e80d-121">xs:string</span></span>|<span data-ttu-id="3e80d-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3e80d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3e80d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3e80d-123">DisplayName</span></span>|<span data-ttu-id="3e80d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e80d-124">xs:string</span></span>|<span data-ttu-id="3e80d-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3e80d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3e80d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3e80d-126">InstanceId</span></span>|<span data-ttu-id="3e80d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e80d-127">xs:string</span></span>|<span data-ttu-id="3e80d-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3e80d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3e80d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3e80d-129">AppDomain</span></span>|<span data-ttu-id="3e80d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e80d-130">xs:string</span></span>|<span data-ttu-id="3e80d-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3e80d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
