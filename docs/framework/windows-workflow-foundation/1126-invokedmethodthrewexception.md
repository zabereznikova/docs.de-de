---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512293"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="a38e9-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="a38e9-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="a38e9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a38e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a38e9-104">ID</span><span class="sxs-lookup"><span data-stu-id="a38e9-104">ID</span></span>|<span data-ttu-id="a38e9-105">1126</span><span class="sxs-lookup"><span data-stu-id="a38e9-105">1126</span></span>|  
|<span data-ttu-id="a38e9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a38e9-106">Keywords</span></span>|<span data-ttu-id="a38e9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a38e9-107">WFRuntime</span></span>|  
|<span data-ttu-id="a38e9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a38e9-108">Level</span></span>|<span data-ttu-id="a38e9-109">Information</span><span class="sxs-lookup"><span data-stu-id="a38e9-109">Information</span></span>|  
|<span data-ttu-id="a38e9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a38e9-110">Channel</span></span>|<span data-ttu-id="a38e9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a38e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a38e9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a38e9-112">Description</span></span>  
 <span data-ttu-id="a38e9-113">Gibt an, dass von der Methode, die von der InvokeMethod-Aktivität aufgerufen wurde, eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a38e9-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a38e9-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a38e9-114">Message</span></span>  
 <span data-ttu-id="a38e9-115">In der von der Aktivität '%1' aufgerufenen Methode wurde eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a38e9-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="a38e9-116">%2</span><span class="sxs-lookup"><span data-stu-id="a38e9-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="a38e9-117">Details</span><span class="sxs-lookup"><span data-stu-id="a38e9-117">Details</span></span>  
  
|<span data-ttu-id="a38e9-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a38e9-118">Data Item Name</span></span>|<span data-ttu-id="a38e9-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a38e9-119">Data Item Type</span></span>|<span data-ttu-id="a38e9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a38e9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a38e9-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a38e9-121">InvokeMethod</span></span>|<span data-ttu-id="a38e9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a38e9-122">xs:string</span></span>|<span data-ttu-id="a38e9-123">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a38e9-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="a38e9-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="a38e9-124">Exception</span></span>|<span data-ttu-id="a38e9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a38e9-125">xs:string</span></span>|<span data-ttu-id="a38e9-126">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a38e9-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="a38e9-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a38e9-127">AppDomain</span></span>|<span data-ttu-id="a38e9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a38e9-128">xs:string</span></span>|<span data-ttu-id="a38e9-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a38e9-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
