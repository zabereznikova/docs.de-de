---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7528c967cbd88f00af448d6163c10e807f603bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="9e9be-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="9e9be-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="9e9be-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9e9be-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e9be-104">ID</span><span class="sxs-lookup"><span data-stu-id="9e9be-104">ID</span></span>|<span data-ttu-id="9e9be-105">4209</span><span class="sxs-lookup"><span data-stu-id="9e9be-105">4209</span></span>|  
|<span data-ttu-id="9e9be-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9e9be-106">Keywords</span></span>|<span data-ttu-id="9e9be-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="9e9be-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="9e9be-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9e9be-108">Level</span></span>|<span data-ttu-id="9e9be-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="9e9be-109">Error</span></span>|  
|<span data-ttu-id="9e9be-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9e9be-110">Channel</span></span>|<span data-ttu-id="9e9be-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9e9be-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9e9be-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e9be-112">Description</span></span>  
 <span data-ttu-id="9e9be-113">Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9e9be-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9e9be-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9e9be-114">Message</span></span>  
 <span data-ttu-id="9e9be-115">Timeout beim Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9e9be-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="9e9be-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9e9be-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="9e9be-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="9e9be-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9e9be-118">Details</span><span class="sxs-lookup"><span data-stu-id="9e9be-118">Details</span></span>  
  
|<span data-ttu-id="9e9be-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9e9be-119">Data Item Name</span></span>|<span data-ttu-id="9e9be-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9e9be-120">Data Item Type</span></span>|<span data-ttu-id="9e9be-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e9be-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9e9be-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="9e9be-122">Timeout</span></span>|<span data-ttu-id="9e9be-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e9be-123">xs:string</span></span>|<span data-ttu-id="9e9be-124">Der Timeoutwert zum Öffnen der SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9e9be-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="9e9be-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9e9be-125">AppDomain</span></span>|<span data-ttu-id="9e9be-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e9be-126">xs:string</span></span>|<span data-ttu-id="9e9be-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9e9be-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
