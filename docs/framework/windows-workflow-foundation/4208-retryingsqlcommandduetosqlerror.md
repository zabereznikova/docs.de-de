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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01db76802b96bd32e8a01cf86b1e682defe97a06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="ca3f6-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="ca3f6-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="ca3f6-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ca3f6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca3f6-104">ID</span><span class="sxs-lookup"><span data-stu-id="ca3f6-104">ID</span></span>|<span data-ttu-id="ca3f6-105">4208</span><span class="sxs-lookup"><span data-stu-id="ca3f6-105">4208</span></span>|  
|<span data-ttu-id="ca3f6-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ca3f6-106">Keywords</span></span>|<span data-ttu-id="ca3f6-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="ca3f6-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="ca3f6-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ca3f6-108">Level</span></span>|<span data-ttu-id="ca3f6-109">Information</span><span class="sxs-lookup"><span data-stu-id="ca3f6-109">Information</span></span>|  
|<span data-ttu-id="ca3f6-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ca3f6-110">Channel</span></span>|<span data-ttu-id="ca3f6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ca3f6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ca3f6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca3f6-112">Description</span></span>  
 <span data-ttu-id="ca3f6-113">Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.</span><span class="sxs-lookup"><span data-stu-id="ca3f6-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ca3f6-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ca3f6-114">Message</span></span>  
 <span data-ttu-id="ca3f6-115">Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.</span><span class="sxs-lookup"><span data-stu-id="ca3f6-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ca3f6-116">Details</span><span class="sxs-lookup"><span data-stu-id="ca3f6-116">Details</span></span>  
  
|<span data-ttu-id="ca3f6-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ca3f6-117">Data Item Name</span></span>|<span data-ttu-id="ca3f6-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ca3f6-118">Data Item Type</span></span>|<span data-ttu-id="ca3f6-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca3f6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ca3f6-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="ca3f6-120">ErrorNumber</span></span>|<span data-ttu-id="ca3f6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ca3f6-121">xs:string</span></span>|<span data-ttu-id="ca3f6-122">Die SQL-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="ca3f6-122">The SQL error number.</span></span>|  
|<span data-ttu-id="ca3f6-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ca3f6-123">AppDomain</span></span>|<span data-ttu-id="ca3f6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ca3f6-124">xs:string</span></span>|<span data-ttu-id="ca3f6-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ca3f6-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
