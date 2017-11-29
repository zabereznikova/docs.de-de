---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1f9f1066f1948411d584a2dee1af2129aa3a103
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="29cfa-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="29cfa-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="29cfa-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29cfa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29cfa-104">ID</span><span class="sxs-lookup"><span data-stu-id="29cfa-104">ID</span></span>|<span data-ttu-id="29cfa-105">3557</span><span class="sxs-lookup"><span data-stu-id="29cfa-105">3557</span></span>|  
|<span data-ttu-id="29cfa-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29cfa-106">Keywords</span></span>|<span data-ttu-id="29cfa-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="29cfa-107">WFServices</span></span>|  
|<span data-ttu-id="29cfa-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="29cfa-108">Level</span></span>|<span data-ttu-id="29cfa-109">Information</span><span class="sxs-lookup"><span data-stu-id="29cfa-109">Information</span></span>|  
|<span data-ttu-id="29cfa-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="29cfa-110">Channel</span></span>|<span data-ttu-id="29cfa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="29cfa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="29cfa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29cfa-112">Description</span></span>  
 <span data-ttu-id="29cfa-113">Gibt an, dass der Aufruf von EndCommit für eine CommittableTransaction eine TransactionException ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="29cfa-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="29cfa-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="29cfa-114">Message</span></span>  
 <span data-ttu-id="29cfa-115">Der Aufruf von EndCommit für die CommittableTransaction mit ID = '%1' hat eine TransactionException mit der folgenden Meldung ausgelöst: '%2'.</span><span class="sxs-lookup"><span data-stu-id="29cfa-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="29cfa-116">Details</span><span class="sxs-lookup"><span data-stu-id="29cfa-116">Details</span></span>  
  
|<span data-ttu-id="29cfa-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="29cfa-117">Data Item Name</span></span>|<span data-ttu-id="29cfa-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="29cfa-118">Data Item Type</span></span>|<span data-ttu-id="29cfa-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29cfa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="29cfa-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="29cfa-120">TransactionId</span></span>|<span data-ttu-id="29cfa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="29cfa-121">xs:string</span></span>|<span data-ttu-id="29cfa-122">Die ID der CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="29cfa-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="29cfa-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="29cfa-123">Exception</span></span>|<span data-ttu-id="29cfa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="29cfa-124">xs:string</span></span>|<span data-ttu-id="29cfa-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="29cfa-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="29cfa-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="29cfa-126">AppDomain</span></span>|<span data-ttu-id="29cfa-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="29cfa-127">xs:string</span></span>|<span data-ttu-id="29cfa-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="29cfa-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
