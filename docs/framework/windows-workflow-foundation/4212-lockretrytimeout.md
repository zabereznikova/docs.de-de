---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511266"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="78d56-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="78d56-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="78d56-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="78d56-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78d56-104">ID</span><span class="sxs-lookup"><span data-stu-id="78d56-104">ID</span></span>|<span data-ttu-id="78d56-105">4212</span><span class="sxs-lookup"><span data-stu-id="78d56-105">4212</span></span>|  
|<span data-ttu-id="78d56-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="78d56-106">Keywords</span></span>|<span data-ttu-id="78d56-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="78d56-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="78d56-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="78d56-108">Level</span></span>|<span data-ttu-id="78d56-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="78d56-109">Warning</span></span>|  
|<span data-ttu-id="78d56-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="78d56-110">Channel</span></span>|<span data-ttu-id="78d56-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="78d56-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78d56-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78d56-112">Description</span></span>  
 <span data-ttu-id="78d56-113">Im SQL-Anbieter ist ein Timeout aufgetreten bei dem Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="78d56-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78d56-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="78d56-114">Message</span></span>  
 <span data-ttu-id="78d56-115">Timeout beim Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="78d56-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="78d56-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="78d56-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="78d56-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="78d56-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="78d56-118">Details</span><span class="sxs-lookup"><span data-stu-id="78d56-118">Details</span></span>  
  
|<span data-ttu-id="78d56-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="78d56-119">Data Item Name</span></span>|<span data-ttu-id="78d56-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="78d56-120">Data Item Type</span></span>|<span data-ttu-id="78d56-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78d56-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78d56-122">Delay</span><span class="sxs-lookup"><span data-stu-id="78d56-122">Delay</span></span>|<span data-ttu-id="78d56-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="78d56-123">xs:string</span></span>|<span data-ttu-id="78d56-124">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="78d56-124">The delay between retries.</span></span>|  
|<span data-ttu-id="78d56-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78d56-125">AppDomain</span></span>|<span data-ttu-id="78d56-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="78d56-126">xs:string</span></span>|<span data-ttu-id="78d56-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="78d56-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
