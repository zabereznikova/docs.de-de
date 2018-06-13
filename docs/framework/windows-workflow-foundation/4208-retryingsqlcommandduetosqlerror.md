---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511594"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="b2f8c-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="b2f8c-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="b2f8c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b2f8c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2f8c-104">ID</span><span class="sxs-lookup"><span data-stu-id="b2f8c-104">ID</span></span>|<span data-ttu-id="b2f8c-105">4208</span><span class="sxs-lookup"><span data-stu-id="b2f8c-105">4208</span></span>|  
|<span data-ttu-id="b2f8c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b2f8c-106">Keywords</span></span>|<span data-ttu-id="b2f8c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b2f8c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b2f8c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b2f8c-108">Level</span></span>|<span data-ttu-id="b2f8c-109">Information</span><span class="sxs-lookup"><span data-stu-id="b2f8c-109">Information</span></span>|  
|<span data-ttu-id="b2f8c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b2f8c-110">Channel</span></span>|<span data-ttu-id="b2f8c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b2f8c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b2f8c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2f8c-112">Description</span></span>  
 <span data-ttu-id="b2f8c-113">Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.</span><span class="sxs-lookup"><span data-stu-id="b2f8c-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b2f8c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b2f8c-114">Message</span></span>  
 <span data-ttu-id="b2f8c-115">Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.</span><span class="sxs-lookup"><span data-stu-id="b2f8c-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b2f8c-116">Details</span><span class="sxs-lookup"><span data-stu-id="b2f8c-116">Details</span></span>  
  
|<span data-ttu-id="b2f8c-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b2f8c-117">Data Item Name</span></span>|<span data-ttu-id="b2f8c-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b2f8c-118">Data Item Type</span></span>|<span data-ttu-id="b2f8c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2f8c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b2f8c-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="b2f8c-120">ErrorNumber</span></span>|<span data-ttu-id="b2f8c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b2f8c-121">xs:string</span></span>|<span data-ttu-id="b2f8c-122">Die SQL-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="b2f8c-122">The SQL error number.</span></span>|  
|<span data-ttu-id="b2f8c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b2f8c-123">AppDomain</span></span>|<span data-ttu-id="b2f8c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b2f8c-124">xs:string</span></span>|<span data-ttu-id="b2f8c-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b2f8c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
