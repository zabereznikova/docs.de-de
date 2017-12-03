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
ms.openlocfilehash: b3bfe7547fafb17503c972646d344263117d9d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="079aa-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="079aa-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="079aa-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="079aa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="079aa-104">ID</span><span class="sxs-lookup"><span data-stu-id="079aa-104">ID</span></span>|<span data-ttu-id="079aa-105">4208</span><span class="sxs-lookup"><span data-stu-id="079aa-105">4208</span></span>|  
|<span data-ttu-id="079aa-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="079aa-106">Keywords</span></span>|<span data-ttu-id="079aa-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="079aa-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="079aa-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="079aa-108">Level</span></span>|<span data-ttu-id="079aa-109">Information</span><span class="sxs-lookup"><span data-stu-id="079aa-109">Information</span></span>|  
|<span data-ttu-id="079aa-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="079aa-110">Channel</span></span>|<span data-ttu-id="079aa-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="079aa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="079aa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="079aa-112">Description</span></span>  
 <span data-ttu-id="079aa-113">Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.</span><span class="sxs-lookup"><span data-stu-id="079aa-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="079aa-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="079aa-114">Message</span></span>  
 <span data-ttu-id="079aa-115">Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.</span><span class="sxs-lookup"><span data-stu-id="079aa-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="079aa-116">Details</span><span class="sxs-lookup"><span data-stu-id="079aa-116">Details</span></span>  
  
|<span data-ttu-id="079aa-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="079aa-117">Data Item Name</span></span>|<span data-ttu-id="079aa-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="079aa-118">Data Item Type</span></span>|<span data-ttu-id="079aa-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="079aa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="079aa-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="079aa-120">ErrorNumber</span></span>|<span data-ttu-id="079aa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="079aa-121">xs:string</span></span>|<span data-ttu-id="079aa-122">Die SQL-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="079aa-122">The SQL error number.</span></span>|  
|<span data-ttu-id="079aa-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="079aa-123">AppDomain</span></span>|<span data-ttu-id="079aa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="079aa-124">xs:string</span></span>|<span data-ttu-id="079aa-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="079aa-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
