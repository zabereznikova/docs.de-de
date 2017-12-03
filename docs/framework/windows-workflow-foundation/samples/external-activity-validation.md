---
title: "Externe Aktivitätsvalidierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ebc79fa582a32ccc252e6c22b9b223870da7e44
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="external-activity-validation"></a><span data-ttu-id="9b968-102">Externe Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="9b968-102">External Activity Validation</span></span>
<span data-ttu-id="9b968-103">In diesem Beispiel wird gezeigt, wie einer integrierten Aktivität Validierungslogik hinzugefügt wird, die Sie nicht erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9b968-103">This sample shows how to add validation logic to a built-in activity that you are not the author of.</span></span> <span data-ttu-id="9b968-104">Mit der Validierungslogik wird erzwungen, dass für alle im Workflow vorhandenen <xref:System.Activities.Statements.If>-Aktivitäten entweder die <xref:System.Activities.Statements.If.Then%2A>-Eigenschaft oder die <xref:System.Activities.Statements.If.Else%2A>-Eigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9b968-104">The validation logic consists of enforcing that all <xref:System.Activities.Statements.If> activities present in the workflow either have their <xref:System.Activities.Statements.If.Then%2A> property set or their <xref:System.Activities.Statements.If.Else%2A> property set.</span></span> <span data-ttu-id="9b968-105">Darüber hinaus wird mit der Validierungslogik geprüft, ob alle <xref:System.Activities.Statements.Pick>-Aktivitäten im Workflow mehr als eine Verzweigung aufweisen. Wenn das nicht der Fall ist, wird eine Warnung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b968-105">Also, the validation logic includes checking that all <xref:System.Activities.Statements.Pick> activities present in the workflow have more than one branch, and if that is not the case, a warning is generated.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="9b968-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="9b968-106">Sample details</span></span>  
 <span data-ttu-id="9b968-107">In diesem Beispiel wird ein Workflow mit einer Instanz der einzelnen zu prüfenden Aktivitäten erstellt: die <xref:System.Activities.Statements.If>-Aktivität und die <xref:System.Activities.Statements.Pick>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9b968-107">This sample creates a workflow with an instance of each activity to validate: the <xref:System.Activities.Statements.If> activity and the <xref:System.Activities.Statements.Pick> activity.</span></span> <span data-ttu-id="9b968-108">Für jedes Validierungsverhalten wird eine neue <xref:System.Activities.Validation.Constraint> erstellt.</span><span class="sxs-lookup"><span data-stu-id="9b968-108">A <xref:System.Activities.Validation.Constraint> is created for each validation behavior.</span></span> <span data-ttu-id="9b968-109">Die in diesem Beispiel erstellten Einschränkungen sind `ConstraintError_IfShouldHaveThenOrElse` und `ConstraintWarning_PickHasOneBranch`.</span><span class="sxs-lookup"><span data-stu-id="9b968-109">The constraints created in this sample are `ConstraintError_IfShouldHaveThenOrElse` and `ConstraintWarning_PickHasOneBranch`.</span></span> <span data-ttu-id="9b968-110">Dann werden diese Einschränkungen der `AdditionalConstraints`-Auflistung einer <xref:System.Activities.Validation.ValidationSettings>-Instanz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9b968-110">Next, these constraints are added to the `AdditionalConstraints` collection of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="9b968-111">Abschließend wird die `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>-Methode von <xref:System.Activities.Validation.ActivityValidationServices> aufgerufen, um die Aktivitäten im Workflow zu überprüfen, und die Validierungsergebnisse werden auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b968-111">Finally, the `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method of <xref:System.Activities.Validation.ActivityValidationServices> is called to validate the activities in the workflow and the validation results are printed out to the console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b968-112">Sie können jeder Aktivität Richtlinieneinschränkungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b968-112">You can add policy constraints to any activity.</span></span> <span data-ttu-id="9b968-113">Sie können z. B. einer <xref:System.Activities.Statements.Sequence>-Aktivität oder einer <xref:System.Activities.Statements.Parallel>-Aktivität eine Richtlinieneinschränkung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b968-113">For example, you can add a policy constraint to a <xref:System.Activities.Statements.Sequence> or <xref:System.Activities.Statements.Parallel> activity.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9b968-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b968-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="9b968-115">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ExternalActivityValidation.sln".</span><span class="sxs-lookup"><span data-stu-id="9b968-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExternalActivityValidation.sln file.</span></span>  
  
2.  <span data-ttu-id="9b968-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9b968-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="9b968-117">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9b968-117">To run the solution, press Ctrl+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9b968-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="9b968-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9b968-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9b968-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9b968-120">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="9b968-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9b968-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9b968-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`