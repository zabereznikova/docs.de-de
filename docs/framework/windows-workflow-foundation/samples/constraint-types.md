---
title: Einschränkungstypen
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 202a2c7b3a3fc400552e42c8606457964af66af2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506611"
---
# <a name="constraint-types"></a><span data-ttu-id="36bca-102">Einschränkungstypen</span><span class="sxs-lookup"><span data-stu-id="36bca-102">Constraint Types</span></span>
<span data-ttu-id="36bca-103">In diesem Beispiel werden zwei verschiedene Möglichkeiten zum Anwenden von Einschränkungen auf einen Workflow veranschaulicht. Eine Möglichkeit besteht darin, dies innerhalb der Aktivität auszuführen (Build), die andere Möglichkeit besteht darin, dies außerhalb der Aktivität auszuführen (Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="36bca-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="36bca-104">In diesem Szenario möchte ein Aktivitätsautor (von einem Drittanbieter-Softwareunternehmen) die Beziehung zwischen zwei Argumenten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="36bca-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="36bca-105">In diesem Fall sollten die Kosten kleiner oder gleich dem Preis sein.</span><span class="sxs-lookup"><span data-stu-id="36bca-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="36bca-106">Dies ist eine allgemeine Validierungsbuildeinschränkung.</span><span class="sxs-lookup"><span data-stu-id="36bca-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="36bca-107">Dann möchte ein Geschäftsbesitzer dieser generischen Aktivität eine Validierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36bca-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="36bca-108">Der Großteil der Produkte soll 9,99 Euro oder weniger kosten.</span><span class="sxs-lookup"><span data-stu-id="36bca-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="36bca-109">Deshalb verwendet er eine Richtlinieneinschränkung, die auf der `CreateProduct`-Aktivität basiert.</span><span class="sxs-lookup"><span data-stu-id="36bca-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="36bca-110">Im Beispiel:</span><span class="sxs-lookup"><span data-stu-id="36bca-110">In the sample:</span></span>  
  
 <span data-ttu-id="36bca-111">Der Aktivitätsautor (Build) muss Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="36bca-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="36bca-112">Eine Einschränkung erstellen (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="36bca-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="36bca-113">An dieser Stelle befindet sich die Validierungslogik.</span><span class="sxs-lookup"><span data-stu-id="36bca-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="36bca-114">Die `System.Activities.CodeActivity.OnGetConstraints()` überschreiben und die Einschränkung (`PriceGreaterThanCost`) den Einschränkungen <xref:System.Collections.IList> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36bca-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="36bca-115">Der Workflowautor (Richtlinie) muss Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="36bca-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="36bca-116">Einen Workflow mit einer Instanz der Aktivität erstellen, um (`CreateProduct`) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="36bca-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="36bca-117">Eine Einschränkung erstellen (`MaxPrice`).</span><span class="sxs-lookup"><span data-stu-id="36bca-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="36bca-118">Eine Instanz von <xref:System.Activities.Validation.ValidationSettings> erstellen (`validationSettings`) und die Einschränkung (`MaxPrice`) der Auflistung `AdditionalConstraints` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36bca-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="36bca-119">Hier kann der Workflowautor jeder Aktivität, z. B. einer Sequenz oder Parallele, Richtlinieneinschränkungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36bca-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="36bca-120"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufrufen, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.ValidationError>-Objekten zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="36bca-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="36bca-121">(Optional) Die <xref:System.Activities.Validation.ValidationError>-Objekte drucken.</span><span class="sxs-lookup"><span data-stu-id="36bca-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="36bca-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="36bca-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="36bca-123">Öffnen Sie die Beispielprojektmappe ConstraintTypes.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36bca-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="36bca-124">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="36bca-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="36bca-125">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="36bca-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="36bca-126">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="36bca-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="36bca-127">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="36bca-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="36bca-128">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="36bca-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`