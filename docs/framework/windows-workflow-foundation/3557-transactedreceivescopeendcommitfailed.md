---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774451"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="24953-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="24953-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="24953-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="24953-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24953-104">ID</span><span class="sxs-lookup"><span data-stu-id="24953-104">ID</span></span>|<span data-ttu-id="24953-105">3557</span><span class="sxs-lookup"><span data-stu-id="24953-105">3557</span></span>|  
|<span data-ttu-id="24953-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="24953-106">Keywords</span></span>|<span data-ttu-id="24953-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="24953-107">WFServices</span></span>|  
|<span data-ttu-id="24953-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="24953-108">Level</span></span>|<span data-ttu-id="24953-109">Information</span><span class="sxs-lookup"><span data-stu-id="24953-109">Information</span></span>|  
|<span data-ttu-id="24953-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="24953-110">Channel</span></span>|<span data-ttu-id="24953-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="24953-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="24953-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24953-112">Description</span></span>  
 <span data-ttu-id="24953-113">Gibt an, dass der Aufruf von EndCommit für eine CommittableTransaction eine TransactionException ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="24953-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="24953-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="24953-114">Message</span></span>  
 <span data-ttu-id="24953-115">Der Aufruf von EndCommit für die CommittableTransaction mit ID = '%1' hat eine TransactionException mit der folgenden Meldung ausgelöst: '%2'.</span><span class="sxs-lookup"><span data-stu-id="24953-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="24953-116">Details</span><span class="sxs-lookup"><span data-stu-id="24953-116">Details</span></span>  
  
|<span data-ttu-id="24953-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="24953-117">Data Item Name</span></span>|<span data-ttu-id="24953-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="24953-118">Data Item Type</span></span>|<span data-ttu-id="24953-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24953-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="24953-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="24953-120">TransactionId</span></span>|<span data-ttu-id="24953-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="24953-121">xs:string</span></span>|<span data-ttu-id="24953-122">Die ID der CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="24953-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="24953-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="24953-123">Exception</span></span>|<span data-ttu-id="24953-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="24953-124">xs:string</span></span>|<span data-ttu-id="24953-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="24953-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="24953-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="24953-126">AppDomain</span></span>|<span data-ttu-id="24953-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="24953-127">xs:string</span></span>|<span data-ttu-id="24953-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="24953-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
