---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251268"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="423a0-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="423a0-102">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="423a0-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="423a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="423a0-104">id</span><span class="sxs-lookup"><span data-stu-id="423a0-104">ID</span></span>|<span data-ttu-id="423a0-105">4203</span><span class="sxs-lookup"><span data-stu-id="423a0-105">4203</span></span>|  
|<span data-ttu-id="423a0-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="423a0-106">Keywords</span></span>|<span data-ttu-id="423a0-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="423a0-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="423a0-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="423a0-108">Level</span></span>|<span data-ttu-id="423a0-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="423a0-109">Error</span></span>|  
|<span data-ttu-id="423a0-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="423a0-110">Channel</span></span>|<span data-ttu-id="423a0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="423a0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="423a0-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="423a0-112">Description</span></span>  

 <span data-ttu-id="423a0-113">Gibt an, dass der SQL-Anbieter die Sperre nicht verlängern konnte, da die Gültigkeit der Sperre bereits abgelaufen war oder der Sperrenbesitzer gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="423a0-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="423a0-114">Das SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="423a0-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="423a0-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="423a0-115">Message</span></span>  

 <span data-ttu-id="423a0-116">Die Gültigkeit der Sperre konnte nicht verlängert werden. Die Sperre ist abgelaufen, oder der Besitzer wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="423a0-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="423a0-117">SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="423a0-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="423a0-118">Details</span><span class="sxs-lookup"><span data-stu-id="423a0-118">Details</span></span>  
  
|<span data-ttu-id="423a0-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="423a0-119">Data Item Name</span></span>|<span data-ttu-id="423a0-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="423a0-120">Data Item Type</span></span>|<span data-ttu-id="423a0-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="423a0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="423a0-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="423a0-122">AppDomain</span></span>|<span data-ttu-id="423a0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="423a0-123">xs:string</span></span>|<span data-ttu-id="423a0-124">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="423a0-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
