---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774295"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="a6cf6-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="a6cf6-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="a6cf6-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6cf6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6cf6-104">ID</span><span class="sxs-lookup"><span data-stu-id="a6cf6-104">ID</span></span>|<span data-ttu-id="a6cf6-105">4208</span><span class="sxs-lookup"><span data-stu-id="a6cf6-105">4208</span></span>|  
|<span data-ttu-id="a6cf6-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a6cf6-106">Keywords</span></span>|<span data-ttu-id="a6cf6-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="a6cf6-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="a6cf6-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a6cf6-108">Level</span></span>|<span data-ttu-id="a6cf6-109">Information</span><span class="sxs-lookup"><span data-stu-id="a6cf6-109">Information</span></span>|  
|<span data-ttu-id="a6cf6-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a6cf6-110">Channel</span></span>|<span data-ttu-id="a6cf6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a6cf6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6cf6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6cf6-112">Description</span></span>  
 <span data-ttu-id="a6cf6-113">Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.</span><span class="sxs-lookup"><span data-stu-id="a6cf6-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6cf6-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="a6cf6-114">Message</span></span>  
 <span data-ttu-id="a6cf6-115">Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.</span><span class="sxs-lookup"><span data-stu-id="a6cf6-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6cf6-116">Details</span><span class="sxs-lookup"><span data-stu-id="a6cf6-116">Details</span></span>  
  
|<span data-ttu-id="a6cf6-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a6cf6-117">Data Item Name</span></span>|<span data-ttu-id="a6cf6-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a6cf6-118">Data Item Type</span></span>|<span data-ttu-id="a6cf6-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6cf6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6cf6-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="a6cf6-120">ErrorNumber</span></span>|<span data-ttu-id="a6cf6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6cf6-121">xs:string</span></span>|<span data-ttu-id="a6cf6-122">Die SQL-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="a6cf6-122">The SQL error number.</span></span>|  
|<span data-ttu-id="a6cf6-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a6cf6-123">AppDomain</span></span>|<span data-ttu-id="a6cf6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6cf6-124">xs:string</span></span>|<span data-ttu-id="a6cf6-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6cf6-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
