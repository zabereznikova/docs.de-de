---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924006"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="d5e53-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="d5e53-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="d5e53-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d5e53-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5e53-104">ID</span><span class="sxs-lookup"><span data-stu-id="d5e53-104">ID</span></span>|<span data-ttu-id="d5e53-105">1126</span><span class="sxs-lookup"><span data-stu-id="d5e53-105">1126</span></span>|  
|<span data-ttu-id="d5e53-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d5e53-106">Keywords</span></span>|<span data-ttu-id="d5e53-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d5e53-107">WFRuntime</span></span>|  
|<span data-ttu-id="d5e53-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d5e53-108">Level</span></span>|<span data-ttu-id="d5e53-109">Information</span><span class="sxs-lookup"><span data-stu-id="d5e53-109">Information</span></span>|  
|<span data-ttu-id="d5e53-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d5e53-110">Channel</span></span>|<span data-ttu-id="d5e53-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d5e53-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d5e53-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5e53-112">Description</span></span>  
 <span data-ttu-id="d5e53-113">Gibt an, dass von der Methode, die von der InvokeMethod-Aktivität aufgerufen wurde, eine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="d5e53-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d5e53-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d5e53-114">Message</span></span>  
 <span data-ttu-id="d5e53-115">In der von der Aktivität '%1' aufgerufenen Methode wurde eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d5e53-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="d5e53-116">%2</span><span class="sxs-lookup"><span data-stu-id="d5e53-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="d5e53-117">Details</span><span class="sxs-lookup"><span data-stu-id="d5e53-117">Details</span></span>  
  
|<span data-ttu-id="d5e53-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d5e53-118">Data Item Name</span></span>|<span data-ttu-id="d5e53-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d5e53-119">Data Item Type</span></span>|<span data-ttu-id="d5e53-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5e53-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d5e53-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d5e53-121">InvokeMethod</span></span>|<span data-ttu-id="d5e53-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5e53-122">xs:string</span></span>|<span data-ttu-id="d5e53-123">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d5e53-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d5e53-124">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d5e53-124">Exception</span></span>|<span data-ttu-id="d5e53-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5e53-125">xs:string</span></span>|<span data-ttu-id="d5e53-126">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="d5e53-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="d5e53-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d5e53-127">AppDomain</span></span>|<span data-ttu-id="d5e53-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d5e53-128">xs:string</span></span>|<span data-ttu-id="d5e53-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d5e53-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
