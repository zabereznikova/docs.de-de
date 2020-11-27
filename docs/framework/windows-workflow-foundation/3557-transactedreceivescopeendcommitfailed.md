---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263658"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="ee3cd-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="ee3cd-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="ee3cd-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ee3cd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee3cd-104">id</span><span class="sxs-lookup"><span data-stu-id="ee3cd-104">ID</span></span>|<span data-ttu-id="ee3cd-105">3557</span><span class="sxs-lookup"><span data-stu-id="ee3cd-105">3557</span></span>|  
|<span data-ttu-id="ee3cd-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ee3cd-106">Keywords</span></span>|<span data-ttu-id="ee3cd-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ee3cd-107">WFServices</span></span>|  
|<span data-ttu-id="ee3cd-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ee3cd-108">Level</span></span>|<span data-ttu-id="ee3cd-109">Information</span><span class="sxs-lookup"><span data-stu-id="ee3cd-109">Information</span></span>|  
|<span data-ttu-id="ee3cd-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ee3cd-110">Channel</span></span>|<span data-ttu-id="ee3cd-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ee3cd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ee3cd-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ee3cd-112">Description</span></span>  

 <span data-ttu-id="ee3cd-113">Gibt an, dass der Aufruf von EndCommit für eine CommittableTransaction eine TransactionException ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ee3cd-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ee3cd-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="ee3cd-114">Message</span></span>  

 <span data-ttu-id="ee3cd-115">Der Aufruf von EndCommit für die CommittableTransaction mit ID = '%1' hat eine TransactionException mit der folgenden Meldung ausgelöst: '%2'.</span><span class="sxs-lookup"><span data-stu-id="ee3cd-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ee3cd-116">Details</span><span class="sxs-lookup"><span data-stu-id="ee3cd-116">Details</span></span>  
  
|<span data-ttu-id="ee3cd-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ee3cd-117">Data Item Name</span></span>|<span data-ttu-id="ee3cd-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ee3cd-118">Data Item Type</span></span>|<span data-ttu-id="ee3cd-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ee3cd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ee3cd-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="ee3cd-120">TransactionId</span></span>|<span data-ttu-id="ee3cd-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee3cd-121">xs:string</span></span>|<span data-ttu-id="ee3cd-122">Die ID der CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="ee3cd-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="ee3cd-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="ee3cd-123">Exception</span></span>|<span data-ttu-id="ee3cd-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee3cd-124">xs:string</span></span>|<span data-ttu-id="ee3cd-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="ee3cd-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="ee3cd-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ee3cd-126">AppDomain</span></span>|<span data-ttu-id="ee3cd-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee3cd-127">xs:string</span></span>|<span data-ttu-id="ee3cd-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ee3cd-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
