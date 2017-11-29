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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f87e99585ccbdf3b89653f026860e7b66dc6c9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="d0d19-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="d0d19-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="d0d19-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0d19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0d19-104">ID</span><span class="sxs-lookup"><span data-stu-id="d0d19-104">ID</span></span>|<span data-ttu-id="d0d19-105">4209</span><span class="sxs-lookup"><span data-stu-id="d0d19-105">4209</span></span>|  
|<span data-ttu-id="d0d19-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d0d19-106">Keywords</span></span>|<span data-ttu-id="d0d19-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="d0d19-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="d0d19-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d0d19-108">Level</span></span>|<span data-ttu-id="d0d19-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="d0d19-109">Error</span></span>|  
|<span data-ttu-id="d0d19-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d0d19-110">Channel</span></span>|<span data-ttu-id="d0d19-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d0d19-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0d19-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0d19-112">Description</span></span>  
 <span data-ttu-id="d0d19-113">Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d0d19-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0d19-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d0d19-114">Message</span></span>  
 <span data-ttu-id="d0d19-115">Timeout beim Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d0d19-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="d0d19-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d0d19-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="d0d19-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="d0d19-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0d19-118">Details</span><span class="sxs-lookup"><span data-stu-id="d0d19-118">Details</span></span>  
  
|<span data-ttu-id="d0d19-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d0d19-119">Data Item Name</span></span>|<span data-ttu-id="d0d19-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d0d19-120">Data Item Type</span></span>|<span data-ttu-id="d0d19-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0d19-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0d19-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="d0d19-122">Timeout</span></span>|<span data-ttu-id="d0d19-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0d19-123">xs:string</span></span>|<span data-ttu-id="d0d19-124">Der Timeoutwert zum Öffnen der SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="d0d19-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="d0d19-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0d19-125">AppDomain</span></span>|<span data-ttu-id="d0d19-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0d19-126">xs:string</span></span>|<span data-ttu-id="d0d19-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d0d19-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
