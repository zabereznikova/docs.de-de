---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512160"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="23b7d-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="23b7d-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="23b7d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="23b7d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23b7d-104">ID</span><span class="sxs-lookup"><span data-stu-id="23b7d-104">ID</span></span>|<span data-ttu-id="23b7d-105">3557</span><span class="sxs-lookup"><span data-stu-id="23b7d-105">3557</span></span>|  
|<span data-ttu-id="23b7d-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="23b7d-106">Keywords</span></span>|<span data-ttu-id="23b7d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="23b7d-107">WFServices</span></span>|  
|<span data-ttu-id="23b7d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="23b7d-108">Level</span></span>|<span data-ttu-id="23b7d-109">Information</span><span class="sxs-lookup"><span data-stu-id="23b7d-109">Information</span></span>|  
|<span data-ttu-id="23b7d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="23b7d-110">Channel</span></span>|<span data-ttu-id="23b7d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="23b7d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23b7d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23b7d-112">Description</span></span>  
 <span data-ttu-id="23b7d-113">Gibt an, dass der Aufruf von EndCommit für eine CommittableTransaction eine TransactionException ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="23b7d-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23b7d-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="23b7d-114">Message</span></span>  
 <span data-ttu-id="23b7d-115">Der Aufruf von EndCommit für die CommittableTransaction mit ID = '%1' hat eine TransactionException mit der folgenden Meldung ausgelöst: '%2'.</span><span class="sxs-lookup"><span data-stu-id="23b7d-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23b7d-116">Details</span><span class="sxs-lookup"><span data-stu-id="23b7d-116">Details</span></span>  
  
|<span data-ttu-id="23b7d-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="23b7d-117">Data Item Name</span></span>|<span data-ttu-id="23b7d-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="23b7d-118">Data Item Type</span></span>|<span data-ttu-id="23b7d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23b7d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23b7d-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="23b7d-120">TransactionId</span></span>|<span data-ttu-id="23b7d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="23b7d-121">xs:string</span></span>|<span data-ttu-id="23b7d-122">Die ID der CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="23b7d-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="23b7d-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="23b7d-123">Exception</span></span>|<span data-ttu-id="23b7d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="23b7d-124">xs:string</span></span>|<span data-ttu-id="23b7d-125">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="23b7d-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="23b7d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23b7d-126">AppDomain</span></span>|<span data-ttu-id="23b7d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="23b7d-127">xs:string</span></span>|<span data-ttu-id="23b7d-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="23b7d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
