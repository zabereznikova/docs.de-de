---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511386"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="3cb3b-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="3cb3b-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3cb3b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3cb3b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cb3b-104">ID</span><span class="sxs-lookup"><span data-stu-id="3cb3b-104">ID</span></span>|<span data-ttu-id="3cb3b-105">1028</span><span class="sxs-lookup"><span data-stu-id="3cb3b-105">1028</span></span>|  
|<span data-ttu-id="3cb3b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3cb3b-106">Keywords</span></span>|<span data-ttu-id="3cb3b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3cb3b-107">WFRuntime</span></span>|  
|<span data-ttu-id="3cb3b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3cb3b-108">Level</span></span>|<span data-ttu-id="3cb3b-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="3cb3b-109">Verbose</span></span>|  
|<span data-ttu-id="3cb3b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3cb3b-110">Channel</span></span>|<span data-ttu-id="3cb3b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3cb3b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3cb3b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cb3b-112">Description</span></span>  
 <span data-ttu-id="3cb3b-113">Gibt an, dass ein TransactionContextWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3cb3b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3cb3b-114">Message</span></span>  
 <span data-ttu-id="3cb3b-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3cb3b-116">Details</span><span class="sxs-lookup"><span data-stu-id="3cb3b-116">Details</span></span>  
  
|<span data-ttu-id="3cb3b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3cb3b-117">Data Item Name</span></span>|<span data-ttu-id="3cb3b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3cb3b-118">Data Item Type</span></span>|<span data-ttu-id="3cb3b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cb3b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3cb3b-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="3cb3b-120">Activity</span></span>|<span data-ttu-id="3cb3b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cb3b-121">xs:string</span></span>|<span data-ttu-id="3cb3b-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3cb3b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cb3b-123">DisplayName</span></span>|<span data-ttu-id="3cb3b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cb3b-124">xs:string</span></span>|<span data-ttu-id="3cb3b-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3cb3b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3cb3b-126">InstanceId</span></span>|<span data-ttu-id="3cb3b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cb3b-127">xs:string</span></span>|<span data-ttu-id="3cb3b-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3cb3b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3cb3b-129">AppDomain</span></span>|<span data-ttu-id="3cb3b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cb3b-130">xs:string</span></span>|<span data-ttu-id="3cb3b-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
