---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280415"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="30c1f-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="30c1f-102">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="30c1f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="30c1f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30c1f-104">id</span><span class="sxs-lookup"><span data-stu-id="30c1f-104">ID</span></span>|<span data-ttu-id="30c1f-105">4208</span><span class="sxs-lookup"><span data-stu-id="30c1f-105">4208</span></span>|  
|<span data-ttu-id="30c1f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="30c1f-106">Keywords</span></span>|<span data-ttu-id="30c1f-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="30c1f-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="30c1f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="30c1f-108">Level</span></span>|<span data-ttu-id="30c1f-109">Information</span><span class="sxs-lookup"><span data-stu-id="30c1f-109">Information</span></span>|  
|<span data-ttu-id="30c1f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="30c1f-110">Channel</span></span>|<span data-ttu-id="30c1f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="30c1f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30c1f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30c1f-112">Description</span></span>  

 <span data-ttu-id="30c1f-113">Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.</span><span class="sxs-lookup"><span data-stu-id="30c1f-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30c1f-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="30c1f-114">Message</span></span>  

 <span data-ttu-id="30c1f-115">Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.</span><span class="sxs-lookup"><span data-stu-id="30c1f-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30c1f-116">Details</span><span class="sxs-lookup"><span data-stu-id="30c1f-116">Details</span></span>  
  
|<span data-ttu-id="30c1f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="30c1f-117">Data Item Name</span></span>|<span data-ttu-id="30c1f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="30c1f-118">Data Item Type</span></span>|<span data-ttu-id="30c1f-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30c1f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30c1f-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="30c1f-120">ErrorNumber</span></span>|<span data-ttu-id="30c1f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="30c1f-121">xs:string</span></span>|<span data-ttu-id="30c1f-122">Die SQL-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="30c1f-122">The SQL error number.</span></span>|  
|<span data-ttu-id="30c1f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30c1f-123">AppDomain</span></span>|<span data-ttu-id="30c1f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="30c1f-124">xs:string</span></span>|<span data-ttu-id="30c1f-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="30c1f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
