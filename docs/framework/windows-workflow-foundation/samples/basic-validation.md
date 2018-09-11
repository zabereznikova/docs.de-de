---
title: Grundlegende Validierung
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264226"
---
# <a name="basic-validation"></a><span data-ttu-id="5f0d4-102">Grundlegende Validierung</span><span class="sxs-lookup"><span data-stu-id="5f0d4-102">Basic Validation</span></span>
<span data-ttu-id="5f0d4-103">Dieses Beispiel besteht aus einer Aktivität, `CreateProduct`, die überprüft, ob ihr `Cost`-Argument kleiner oder gleich ihrem `Price`-Argument ist.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="5f0d4-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="5f0d4-104">Sample Details</span></span>  
 <span data-ttu-id="5f0d4-105">Es gibt zwei Autoren, die die Validierung verwenden, den Aktivitätsautor (erstellt die Validierungslogik für die Aktivität) und den Workflowautor, der Validierungsdienste in einem bestimmten Workflow aufruft.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="5f0d4-106">In diesem Szenario möchte der Aktivitätsautor erzwingen, dass jede Instanz seiner Aktivität kleinere oder gleiche Kosten als der Preis haben muss.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="5f0d4-107">Der Aktivitätsautor (innerhalb der Aktivität) muss:</span><span class="sxs-lookup"><span data-stu-id="5f0d4-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="5f0d4-108">Eine Einschränkung erstellen (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="5f0d4-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="5f0d4-109">An dieser Stelle befindet sich die Validierungslogik.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="5f0d4-110">Die `System.Activities.CodeActivity.OnGetConstraints()` überschreiben und die Einschränkung (`PriceGreaterThanCost`) den Einschränkungen <xref:System.Collections.IList> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="5f0d4-111">Der Workflowautor (Hauptprogramm) muss:</span><span class="sxs-lookup"><span data-stu-id="5f0d4-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="5f0d4-112">Einen Workflow mit einer Instanz der Aktivität erstellen, um (`CreateProduct`) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="5f0d4-113"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufrufen, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.ValidationError> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="5f0d4-114">(Optional) Die <xref:System.Activities.Validation.ValidationError>-Objekte drucken.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5f0d4-115">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="5f0d4-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5f0d4-116">Öffnen Sie die Projektmappe "BasicValidation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f0d4-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f0d4-117">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f0d4-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5f0d4-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5f0d4-120">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f0d4-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5f0d4-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`