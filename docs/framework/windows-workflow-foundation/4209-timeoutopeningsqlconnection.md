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
ms.openlocfilehash: 86d971a2e5f1257281c453e7eb0c2dc1755098d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="99796-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="99796-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="99796-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="99796-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99796-104">ID</span><span class="sxs-lookup"><span data-stu-id="99796-104">ID</span></span>|<span data-ttu-id="99796-105">4209</span><span class="sxs-lookup"><span data-stu-id="99796-105">4209</span></span>|  
|<span data-ttu-id="99796-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="99796-106">Keywords</span></span>|<span data-ttu-id="99796-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="99796-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="99796-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="99796-108">Level</span></span>|<span data-ttu-id="99796-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="99796-109">Error</span></span>|  
|<span data-ttu-id="99796-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="99796-110">Channel</span></span>|<span data-ttu-id="99796-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="99796-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="99796-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99796-112">Description</span></span>  
 <span data-ttu-id="99796-113">Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="99796-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="99796-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="99796-114">Message</span></span>  
 <span data-ttu-id="99796-115">Timeout beim Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="99796-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="99796-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="99796-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="99796-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="99796-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="99796-118">Details</span><span class="sxs-lookup"><span data-stu-id="99796-118">Details</span></span>  
  
|<span data-ttu-id="99796-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="99796-119">Data Item Name</span></span>|<span data-ttu-id="99796-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="99796-120">Data Item Type</span></span>|<span data-ttu-id="99796-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99796-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="99796-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="99796-122">Timeout</span></span>|<span data-ttu-id="99796-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="99796-123">xs:string</span></span>|<span data-ttu-id="99796-124">Der Timeoutwert zum Öffnen der SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="99796-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="99796-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="99796-125">AppDomain</span></span>|<span data-ttu-id="99796-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="99796-126">xs:string</span></span>|<span data-ttu-id="99796-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="99796-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
