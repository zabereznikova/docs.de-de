---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009954"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="3c428-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="3c428-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="3c428-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3c428-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c428-104">ID</span><span class="sxs-lookup"><span data-stu-id="3c428-104">ID</span></span>|<span data-ttu-id="3c428-105">1131</span><span class="sxs-lookup"><span data-stu-id="3c428-105">1131</span></span>|  
|<span data-ttu-id="3c428-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3c428-106">Keywords</span></span>|<span data-ttu-id="3c428-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3c428-107">WFRuntime</span></span>|  
|<span data-ttu-id="3c428-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3c428-108">Level</span></span>|<span data-ttu-id="3c428-109">Information</span><span class="sxs-lookup"><span data-stu-id="3c428-109">Information</span></span>|  
|<span data-ttu-id="3c428-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3c428-110">Channel</span></span>|<span data-ttu-id="3c428-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3c428-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c428-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c428-112">Description</span></span>  
 <span data-ttu-id="3c428-113">Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c428-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c428-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3c428-114">Message</span></span>  
 <span data-ttu-id="3c428-115">InvokeMethod '%1' - Methode verwendet das asynchrone Muster von '%2' und '%3'.</span><span class="sxs-lookup"><span data-stu-id="3c428-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c428-116">Details</span><span class="sxs-lookup"><span data-stu-id="3c428-116">Details</span></span>  
  
|<span data-ttu-id="3c428-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3c428-117">Data Item Name</span></span>|<span data-ttu-id="3c428-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3c428-118">Data Item Type</span></span>|<span data-ttu-id="3c428-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c428-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c428-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="3c428-120">InvokeMethod</span></span>|<span data-ttu-id="3c428-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c428-121">xs:string</span></span>|<span data-ttu-id="3c428-122">Der Anzeigename der InvokeMethod-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3c428-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="3c428-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="3c428-123">BeginMethod</span></span>|<span data-ttu-id="3c428-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c428-124">xs:string</span></span>|<span data-ttu-id="3c428-125">Der Name der Anfangsmethode.</span><span class="sxs-lookup"><span data-stu-id="3c428-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="3c428-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="3c428-126">EndMethod</span></span>|<span data-ttu-id="3c428-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c428-127">xs:string</span></span>|<span data-ttu-id="3c428-128">Der Name der Endmethode.</span><span class="sxs-lookup"><span data-stu-id="3c428-128">The name of the end method.</span></span>|  
|<span data-ttu-id="3c428-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3c428-129">AppDomain</span></span>|<span data-ttu-id="3c428-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c428-130">xs:string</span></span>|<span data-ttu-id="3c428-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3c428-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
