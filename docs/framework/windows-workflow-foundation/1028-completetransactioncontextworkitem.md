---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008810"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="48587-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="48587-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="48587-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48587-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48587-104">ID</span><span class="sxs-lookup"><span data-stu-id="48587-104">ID</span></span>|<span data-ttu-id="48587-105">1028</span><span class="sxs-lookup"><span data-stu-id="48587-105">1028</span></span>|  
|<span data-ttu-id="48587-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48587-106">Keywords</span></span>|<span data-ttu-id="48587-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48587-107">WFRuntime</span></span>|  
|<span data-ttu-id="48587-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="48587-108">Level</span></span>|<span data-ttu-id="48587-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="48587-109">Verbose</span></span>|  
|<span data-ttu-id="48587-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="48587-110">Channel</span></span>|<span data-ttu-id="48587-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48587-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48587-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48587-112">Description</span></span>  
 <span data-ttu-id="48587-113">Gibt an, dass ein TransactionContextWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="48587-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48587-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="48587-114">Message</span></span>  
 <span data-ttu-id="48587-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein TransactionContextWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="48587-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48587-116">Details</span><span class="sxs-lookup"><span data-stu-id="48587-116">Details</span></span>  
  
|<span data-ttu-id="48587-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="48587-117">Data Item Name</span></span>|<span data-ttu-id="48587-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="48587-118">Data Item Type</span></span>|<span data-ttu-id="48587-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48587-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48587-120">Aktivität</span><span class="sxs-lookup"><span data-stu-id="48587-120">Activity</span></span>|<span data-ttu-id="48587-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-121">xs:string</span></span>|<span data-ttu-id="48587-122">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="48587-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="48587-123">DisplayName</span></span>|<span data-ttu-id="48587-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-124">xs:string</span></span>|<span data-ttu-id="48587-125">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="48587-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="48587-126">InstanceId</span></span>|<span data-ttu-id="48587-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-127">xs:string</span></span>|<span data-ttu-id="48587-128">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="48587-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48587-129">AppDomain</span></span>|<span data-ttu-id="48587-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-130">xs:string</span></span>|<span data-ttu-id="48587-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48587-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
