---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97a2f68ed921ccc251e1dc316d633d2520efc643
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="a481b-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="a481b-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="a481b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a481b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a481b-104">ID</span><span class="sxs-lookup"><span data-stu-id="a481b-104">ID</span></span>|<span data-ttu-id="a481b-105">4207</span><span class="sxs-lookup"><span data-stu-id="a481b-105">4207</span></span>|  
|<span data-ttu-id="a481b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a481b-106">Keywords</span></span>|<span data-ttu-id="a481b-107">Kontingent, WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="a481b-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="a481b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a481b-108">Level</span></span>|<span data-ttu-id="a481b-109">Information</span><span class="sxs-lookup"><span data-stu-id="a481b-109">Information</span></span>|  
|<span data-ttu-id="a481b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a481b-110">Channel</span></span>|<span data-ttu-id="a481b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a481b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a481b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a481b-112">Description</span></span>  
 <span data-ttu-id="a481b-113">Gibt an, dass der SQL-Anbieter nicht weiter versucht, einen SQL-Befehl abzurufen, da die maximale Anzahl an Wiederholungsversuchen ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a481b-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a481b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a481b-114">Message</span></span>  
 <span data-ttu-id="a481b-115">Es wird nicht weiter versucht, einen SQL-Befehl abzurufen, da die maximale Anzahl an Wiederholungsversuchen ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a481b-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a481b-116">Details</span><span class="sxs-lookup"><span data-stu-id="a481b-116">Details</span></span>  
  
|<span data-ttu-id="a481b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a481b-117">Data Item Name</span></span>|<span data-ttu-id="a481b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a481b-118">Data Item Type</span></span>|<span data-ttu-id="a481b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a481b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a481b-120">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a481b-120">AppDomain</span></span>|<span data-ttu-id="a481b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a481b-121">xs:string</span></span>|<span data-ttu-id="a481b-122">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a481b-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
