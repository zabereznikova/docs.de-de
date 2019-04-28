---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774217"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="f5adf-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="f5adf-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="f5adf-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f5adf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5adf-104">ID</span><span class="sxs-lookup"><span data-stu-id="f5adf-104">ID</span></span>|<span data-ttu-id="f5adf-105">4212</span><span class="sxs-lookup"><span data-stu-id="f5adf-105">4212</span></span>|  
|<span data-ttu-id="f5adf-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f5adf-106">Keywords</span></span>|<span data-ttu-id="f5adf-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f5adf-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f5adf-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f5adf-108">Level</span></span>|<span data-ttu-id="f5adf-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="f5adf-109">Warning</span></span>|  
|<span data-ttu-id="f5adf-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f5adf-110">Channel</span></span>|<span data-ttu-id="f5adf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f5adf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5adf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5adf-112">Description</span></span>  
 <span data-ttu-id="f5adf-113">Im SQL-Anbieter ist ein Timeout aufgetreten bei dem Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f5adf-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5adf-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f5adf-114">Message</span></span>  
 <span data-ttu-id="f5adf-115">Timeout beim Versuch, die Instanzsperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f5adf-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="f5adf-116">Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f5adf-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="f5adf-117">Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.</span><span class="sxs-lookup"><span data-stu-id="f5adf-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5adf-118">Details</span><span class="sxs-lookup"><span data-stu-id="f5adf-118">Details</span></span>  
  
|<span data-ttu-id="f5adf-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f5adf-119">Data Item Name</span></span>|<span data-ttu-id="f5adf-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f5adf-120">Data Item Type</span></span>|<span data-ttu-id="f5adf-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5adf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5adf-122">Delay</span><span class="sxs-lookup"><span data-stu-id="f5adf-122">Delay</span></span>|<span data-ttu-id="f5adf-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5adf-123">xs:string</span></span>|<span data-ttu-id="f5adf-124">Die Verzögerung zwischen den Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="f5adf-124">The delay between retries.</span></span>|  
|<span data-ttu-id="f5adf-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5adf-125">AppDomain</span></span>|<span data-ttu-id="f5adf-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5adf-126">xs:string</span></span>|<span data-ttu-id="f5adf-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f5adf-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
