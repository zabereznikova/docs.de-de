---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51374a25ee11b3344e950670cc7882db42d39779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="b3495-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="b3495-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="b3495-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b3495-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3495-104">ID</span><span class="sxs-lookup"><span data-stu-id="b3495-104">ID</span></span>|<span data-ttu-id="b3495-105">4208</span><span class="sxs-lookup"><span data-stu-id="b3495-105">4208</span></span>|  
|<span data-ttu-id="b3495-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b3495-106">Keywords</span></span>|<span data-ttu-id="b3495-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b3495-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b3495-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b3495-108">Level</span></span>|<span data-ttu-id="b3495-109">Information</span><span class="sxs-lookup"><span data-stu-id="b3495-109">Information</span></span>|  
|<span data-ttu-id="b3495-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b3495-110">Channel</span></span>|<span data-ttu-id="b3495-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b3495-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b3495-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3495-112">Description</span></span>  
 <span data-ttu-id="b3495-113">Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.</span><span class="sxs-lookup"><span data-stu-id="b3495-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b3495-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b3495-114">Message</span></span>  
 <span data-ttu-id="b3495-115">Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.</span><span class="sxs-lookup"><span data-stu-id="b3495-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b3495-116">Details</span><span class="sxs-lookup"><span data-stu-id="b3495-116">Details</span></span>  
  
|<span data-ttu-id="b3495-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b3495-117">Data Item Name</span></span>|<span data-ttu-id="b3495-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b3495-118">Data Item Type</span></span>|<span data-ttu-id="b3495-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3495-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b3495-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="b3495-120">ErrorNumber</span></span>|<span data-ttu-id="b3495-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b3495-121">xs:string</span></span>|<span data-ttu-id="b3495-122">Die SQL-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="b3495-122">The SQL error number.</span></span>|  
|<span data-ttu-id="b3495-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b3495-123">AppDomain</span></span>|<span data-ttu-id="b3495-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b3495-124">xs:string</span></span>|<span data-ttu-id="b3495-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3495-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
