---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513928"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="7291f-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="7291f-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="7291f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7291f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7291f-104">ID</span><span class="sxs-lookup"><span data-stu-id="7291f-104">ID</span></span>|<span data-ttu-id="7291f-105">4203</span><span class="sxs-lookup"><span data-stu-id="7291f-105">4203</span></span>|  
|<span data-ttu-id="7291f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7291f-106">Keywords</span></span>|<span data-ttu-id="7291f-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="7291f-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="7291f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7291f-108">Level</span></span>|<span data-ttu-id="7291f-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="7291f-109">Error</span></span>|  
|<span data-ttu-id="7291f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7291f-110">Channel</span></span>|<span data-ttu-id="7291f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7291f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7291f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7291f-112">Description</span></span>  
 <span data-ttu-id="7291f-113">Gibt an, dass der SQL-Anbieter die Sperre nicht verlängern konnte, da die Gültigkeit der Sperre bereits abgelaufen war oder der Sperrenbesitzer gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="7291f-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="7291f-114">Das SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="7291f-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7291f-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="7291f-115">Message</span></span>  
 <span data-ttu-id="7291f-116">Die Gültigkeit der Sperre konnte nicht verlängert werden. Die Sperre ist abgelaufen, oder der Besitzer wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7291f-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="7291f-117">SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="7291f-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7291f-118">Details</span><span class="sxs-lookup"><span data-stu-id="7291f-118">Details</span></span>  
  
|<span data-ttu-id="7291f-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7291f-119">Data Item Name</span></span>|<span data-ttu-id="7291f-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7291f-120">Data Item Type</span></span>|<span data-ttu-id="7291f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7291f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7291f-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7291f-122">AppDomain</span></span>|<span data-ttu-id="7291f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7291f-123">xs:string</span></span>|<span data-ttu-id="7291f-124">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7291f-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
