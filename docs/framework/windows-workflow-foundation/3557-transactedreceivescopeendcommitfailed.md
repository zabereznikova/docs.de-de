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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ea57cc60f9626763308267a98624c825f8312b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="f4785-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="f4785-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="f4785-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f4785-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4785-104">ID</span><span class="sxs-lookup"><span data-stu-id="f4785-104">ID</span></span>|<span data-ttu-id="f4785-105">3557</span><span class="sxs-lookup"><span data-stu-id="f4785-105">3557</span></span>|  
|<span data-ttu-id="f4785-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f4785-106">Keywords</span></span>|<span data-ttu-id="f4785-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f4785-107">WFServices</span></span>|  
|<span data-ttu-id="f4785-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f4785-108">Level</span></span>|<span data-ttu-id="f4785-109">Information</span><span class="sxs-lookup"><span data-stu-id="f4785-109">Information</span></span>|  
|<span data-ttu-id="f4785-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f4785-110">Channel</span></span>|<span data-ttu-id="f4785-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f4785-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4785-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4785-112">Description</span></span>  
 <span data-ttu-id="f4785-113">Gibt an, dass der Aufruf von EndCommit für eine CommittableTransaction eine TransactionException ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f4785-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4785-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f4785-114">Message</span></span>  
 <span data-ttu-id="f4785-115">Der Aufruf von EndCommit für die CommittableTransaction mit ID = '%1' hat eine TransactionException mit der folgenden Meldung ausgelöst: '%2'.</span><span class="sxs-lookup"><span data-stu-id="f4785-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4785-116">Details</span><span class="sxs-lookup"><span data-stu-id="f4785-116">Details</span></span>  
  
|<span data-ttu-id="f4785-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f4785-117">Data Item Name</span></span>|<span data-ttu-id="f4785-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f4785-118">Data Item Type</span></span>|<span data-ttu-id="f4785-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4785-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4785-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="f4785-120">TransactionId</span></span>|<span data-ttu-id="f4785-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4785-121">xs:string</span></span>|<span data-ttu-id="f4785-122">Die ID der CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="f4785-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="f4785-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="f4785-123">Exception</span></span>|<span data-ttu-id="f4785-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4785-124">xs:string</span></span>|<span data-ttu-id="f4785-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f4785-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="f4785-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4785-126">AppDomain</span></span>|<span data-ttu-id="f4785-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4785-127">xs:string</span></span>|<span data-ttu-id="f4785-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f4785-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
