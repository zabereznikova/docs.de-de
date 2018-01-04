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
ms.workload: dotnet
ms.openlocfilehash: 8fabe6f2c023bf9b997d2a4e19b4a3755c93f408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="90c49-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="90c49-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="90c49-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="90c49-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90c49-104">ID</span><span class="sxs-lookup"><span data-stu-id="90c49-104">ID</span></span>|<span data-ttu-id="90c49-105">4203</span><span class="sxs-lookup"><span data-stu-id="90c49-105">4203</span></span>|  
|<span data-ttu-id="90c49-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="90c49-106">Keywords</span></span>|<span data-ttu-id="90c49-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="90c49-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="90c49-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="90c49-108">Level</span></span>|<span data-ttu-id="90c49-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="90c49-109">Error</span></span>|  
|<span data-ttu-id="90c49-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="90c49-110">Channel</span></span>|<span data-ttu-id="90c49-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="90c49-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="90c49-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90c49-112">Description</span></span>  
 <span data-ttu-id="90c49-113">Gibt an, dass der SQL-Anbieter die Sperre nicht verlängern konnte, da die Gültigkeit der Sperre bereits abgelaufen war oder der Sperrenbesitzer gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="90c49-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="90c49-114">Das SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="90c49-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="90c49-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="90c49-115">Message</span></span>  
 <span data-ttu-id="90c49-116">Die Gültigkeit der Sperre konnte nicht verlängert werden. Die Sperre ist abgelaufen, oder der Besitzer wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="90c49-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="90c49-117">SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="90c49-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="90c49-118">Details</span><span class="sxs-lookup"><span data-stu-id="90c49-118">Details</span></span>  
  
|<span data-ttu-id="90c49-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="90c49-119">Data Item Name</span></span>|<span data-ttu-id="90c49-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="90c49-120">Data Item Type</span></span>|<span data-ttu-id="90c49-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90c49-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="90c49-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="90c49-122">AppDomain</span></span>|<span data-ttu-id="90c49-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="90c49-123">xs:string</span></span>|<span data-ttu-id="90c49-124">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="90c49-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
