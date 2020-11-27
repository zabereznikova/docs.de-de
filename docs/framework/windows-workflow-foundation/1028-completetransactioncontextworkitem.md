---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 2fc509dac7e13f30f74c24d8b98cba55ed5f8e1d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275114"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="6a772-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="6a772-102">1028 - CompleteTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="6a772-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6a772-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a772-104">id</span><span class="sxs-lookup"><span data-stu-id="6a772-104">ID</span></span>|<span data-ttu-id="6a772-105">1028</span><span class="sxs-lookup"><span data-stu-id="6a772-105">1028</span></span>|  
|<span data-ttu-id="6a772-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="6a772-106">Keywords</span></span>|<span data-ttu-id="6a772-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6a772-107">WFRuntime</span></span>|  
|<span data-ttu-id="6a772-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6a772-108">Level</span></span>|<span data-ttu-id="6a772-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="6a772-109">Verbose</span></span>|  
|<span data-ttu-id="6a772-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6a772-110">Channel</span></span>|<span data-ttu-id="6a772-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6a772-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6a772-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a772-112">Description</span></span>  

 <span data-ttu-id="6a772-113">Gibt an, dass ein TransactionContextWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6a772-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6a772-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="6a772-114">Message</span></span>  

 <span data-ttu-id="6a772-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6a772-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6a772-116">Details</span><span class="sxs-lookup"><span data-stu-id="6a772-116">Details</span></span>  
  
|<span data-ttu-id="6a772-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6a772-117">Data Item Name</span></span>|<span data-ttu-id="6a772-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6a772-118">Data Item Type</span></span>|<span data-ttu-id="6a772-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a772-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6a772-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="6a772-120">Activity</span></span>|<span data-ttu-id="6a772-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a772-121">xs:string</span></span>|<span data-ttu-id="6a772-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a772-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="6a772-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6a772-123">DisplayName</span></span>|<span data-ttu-id="6a772-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a772-124">xs:string</span></span>|<span data-ttu-id="6a772-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a772-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="6a772-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="6a772-126">InstanceId</span></span>|<span data-ttu-id="6a772-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a772-127">xs:string</span></span>|<span data-ttu-id="6a772-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a772-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="6a772-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6a772-129">AppDomain</span></span>|<span data-ttu-id="6a772-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a772-130">xs:string</span></span>|<span data-ttu-id="6a772-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6a772-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
