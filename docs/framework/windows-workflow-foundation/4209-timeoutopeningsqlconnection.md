---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774269"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="be50c-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="be50c-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="be50c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="be50c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be50c-104">ID</span><span class="sxs-lookup"><span data-stu-id="be50c-104">ID</span></span>|<span data-ttu-id="be50c-105">4209</span><span class="sxs-lookup"><span data-stu-id="be50c-105">4209</span></span>|  
|<span data-ttu-id="be50c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="be50c-106">Keywords</span></span>|<span data-ttu-id="be50c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="be50c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="be50c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="be50c-108">Level</span></span>|<span data-ttu-id="be50c-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="be50c-109">Error</span></span>|  
|<span data-ttu-id="be50c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="be50c-110">Channel</span></span>|<span data-ttu-id="be50c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="be50c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="be50c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be50c-112">Description</span></span>  
 <span data-ttu-id="be50c-113">Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="be50c-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="be50c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="be50c-114">Message</span></span>  
 <span data-ttu-id="be50c-115">Timeout beim Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="be50c-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="be50c-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="be50c-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="be50c-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="be50c-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="be50c-118">Details</span><span class="sxs-lookup"><span data-stu-id="be50c-118">Details</span></span>  
  
|<span data-ttu-id="be50c-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="be50c-119">Data Item Name</span></span>|<span data-ttu-id="be50c-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="be50c-120">Data Item Type</span></span>|<span data-ttu-id="be50c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be50c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="be50c-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="be50c-122">Timeout</span></span>|<span data-ttu-id="be50c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="be50c-123">xs:string</span></span>|<span data-ttu-id="be50c-124">Der Timeoutwert zum Öffnen der SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="be50c-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="be50c-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="be50c-125">AppDomain</span></span>|<span data-ttu-id="be50c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="be50c-126">xs:string</span></span>|<span data-ttu-id="be50c-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="be50c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
