---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774347"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="c46fd-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="c46fd-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="c46fd-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c46fd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c46fd-104">ID</span><span class="sxs-lookup"><span data-stu-id="c46fd-104">ID</span></span>|<span data-ttu-id="c46fd-105">4203</span><span class="sxs-lookup"><span data-stu-id="c46fd-105">4203</span></span>|  
|<span data-ttu-id="c46fd-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c46fd-106">Keywords</span></span>|<span data-ttu-id="c46fd-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c46fd-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c46fd-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="c46fd-108">Level</span></span>|<span data-ttu-id="c46fd-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="c46fd-109">Error</span></span>|  
|<span data-ttu-id="c46fd-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="c46fd-110">Channel</span></span>|<span data-ttu-id="c46fd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c46fd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c46fd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c46fd-112">Description</span></span>  
 <span data-ttu-id="c46fd-113">Gibt an, dass der SQL-Anbieter die Sperre nicht verlängern konnte, da die Gültigkeit der Sperre bereits abgelaufen war oder der Sperrenbesitzer gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="c46fd-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="c46fd-114">Das SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="c46fd-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c46fd-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="c46fd-115">Message</span></span>  
 <span data-ttu-id="c46fd-116">Die Gültigkeit der Sperre konnte nicht verlängert werden. Die Sperre ist abgelaufen, oder der Besitzer wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c46fd-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="c46fd-117">SqlWorkflowInstanceStore wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="c46fd-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c46fd-118">Details</span><span class="sxs-lookup"><span data-stu-id="c46fd-118">Details</span></span>  
  
|<span data-ttu-id="c46fd-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="c46fd-119">Data Item Name</span></span>|<span data-ttu-id="c46fd-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="c46fd-120">Data Item Type</span></span>|<span data-ttu-id="c46fd-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c46fd-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c46fd-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c46fd-122">AppDomain</span></span>|<span data-ttu-id="c46fd-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c46fd-123">xs:string</span></span>|<span data-ttu-id="c46fd-124">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c46fd-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
