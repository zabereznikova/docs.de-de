---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238677"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="11e53-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="11e53-102">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="11e53-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="11e53-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11e53-104">id</span><span class="sxs-lookup"><span data-stu-id="11e53-104">ID</span></span>|<span data-ttu-id="11e53-105">4209</span><span class="sxs-lookup"><span data-stu-id="11e53-105">4209</span></span>|  
|<span data-ttu-id="11e53-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="11e53-106">Keywords</span></span>|<span data-ttu-id="11e53-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="11e53-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="11e53-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="11e53-108">Level</span></span>|<span data-ttu-id="11e53-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="11e53-109">Error</span></span>|  
|<span data-ttu-id="11e53-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="11e53-110">Channel</span></span>|<span data-ttu-id="11e53-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="11e53-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11e53-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11e53-112">Description</span></span>  

 <span data-ttu-id="11e53-113">Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11e53-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11e53-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="11e53-114">Message</span></span>  

 <span data-ttu-id="11e53-115">Timeout beim Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11e53-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="11e53-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="11e53-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="11e53-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="11e53-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11e53-118">Details</span><span class="sxs-lookup"><span data-stu-id="11e53-118">Details</span></span>  
  
|<span data-ttu-id="11e53-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="11e53-119">Data Item Name</span></span>|<span data-ttu-id="11e53-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="11e53-120">Data Item Type</span></span>|<span data-ttu-id="11e53-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11e53-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11e53-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="11e53-122">Timeout</span></span>|<span data-ttu-id="11e53-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="11e53-123">xs:string</span></span>|<span data-ttu-id="11e53-124">Der Timeoutwert zum Öffnen der SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="11e53-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="11e53-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11e53-125">AppDomain</span></span>|<span data-ttu-id="11e53-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="11e53-126">xs:string</span></span>|<span data-ttu-id="11e53-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11e53-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
