---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513164"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="8d5eb-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="8d5eb-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="8d5eb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8d5eb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d5eb-104">ID</span><span class="sxs-lookup"><span data-stu-id="8d5eb-104">ID</span></span>|<span data-ttu-id="8d5eb-105">4209</span><span class="sxs-lookup"><span data-stu-id="8d5eb-105">4209</span></span>|  
|<span data-ttu-id="8d5eb-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8d5eb-106">Keywords</span></span>|<span data-ttu-id="8d5eb-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="8d5eb-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="8d5eb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8d5eb-108">Level</span></span>|<span data-ttu-id="8d5eb-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="8d5eb-109">Error</span></span>|  
|<span data-ttu-id="8d5eb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8d5eb-110">Channel</span></span>|<span data-ttu-id="8d5eb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8d5eb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8d5eb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d5eb-112">Description</span></span>  
 <span data-ttu-id="8d5eb-113">Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8d5eb-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8d5eb-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8d5eb-114">Message</span></span>  
 <span data-ttu-id="8d5eb-115">Timeout beim Versuch, eine SQL-Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8d5eb-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="8d5eb-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8d5eb-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="8d5eb-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="8d5eb-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8d5eb-118">Details</span><span class="sxs-lookup"><span data-stu-id="8d5eb-118">Details</span></span>  
  
|<span data-ttu-id="8d5eb-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8d5eb-119">Data Item Name</span></span>|<span data-ttu-id="8d5eb-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8d5eb-120">Data Item Type</span></span>|<span data-ttu-id="8d5eb-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d5eb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8d5eb-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="8d5eb-122">Timeout</span></span>|<span data-ttu-id="8d5eb-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5eb-123">xs:string</span></span>|<span data-ttu-id="8d5eb-124">Der Timeoutwert zum Öffnen der SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="8d5eb-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="8d5eb-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8d5eb-125">AppDomain</span></span>|<span data-ttu-id="8d5eb-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5eb-126">xs:string</span></span>|<span data-ttu-id="8d5eb-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8d5eb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
