---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c2214ec48f0c1cba1e3aacad0eaa5a29625f9c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="bea0a-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="bea0a-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="bea0a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bea0a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bea0a-104">ID</span><span class="sxs-lookup"><span data-stu-id="bea0a-104">ID</span></span>|<span data-ttu-id="bea0a-105">4203</span><span class="sxs-lookup"><span data-stu-id="bea0a-105">4203</span></span>|  
|<span data-ttu-id="bea0a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bea0a-106">Keywords</span></span>|<span data-ttu-id="bea0a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="bea0a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="bea0a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="bea0a-108">Level</span></span>|<span data-ttu-id="bea0a-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="bea0a-109">Error</span></span>|  
|<span data-ttu-id="bea0a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="bea0a-110">Channel</span></span>|<span data-ttu-id="bea0a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bea0a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bea0a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bea0a-112">Description</span></span>  
 <span data-ttu-id="bea0a-113">Gibt an, dass der SQL-Anbieter die Sperre nicht verlängern konnte, da die Gültigkeit der Sperre bereits abgelaufen war oder der Sperrenbesitzer gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="bea0a-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="bea0a-114">Das SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="bea0a-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bea0a-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="bea0a-115">Message</span></span>  
 <span data-ttu-id="bea0a-116">Die Gültigkeit der Sperre konnte nicht verlängert werden. Die Sperre ist abgelaufen, oder der Besitzer wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="bea0a-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="bea0a-117">SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="bea0a-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bea0a-118">Details</span><span class="sxs-lookup"><span data-stu-id="bea0a-118">Details</span></span>  
  
|<span data-ttu-id="bea0a-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="bea0a-119">Data Item Name</span></span>|<span data-ttu-id="bea0a-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="bea0a-120">Data Item Type</span></span>|<span data-ttu-id="bea0a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bea0a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bea0a-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bea0a-122">AppDomain</span></span>|<span data-ttu-id="bea0a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="bea0a-123">xs:string</span></span>|<span data-ttu-id="bea0a-124">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bea0a-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
