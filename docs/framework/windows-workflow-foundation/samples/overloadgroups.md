---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a5ab416dc484dddc0b6aa0ec25757921815c723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="overloadgroups"></a><span data-ttu-id="a9fa5-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="a9fa5-102">OverloadGroups</span></span>
<span data-ttu-id="a9fa5-103">Dieses Beispiel besteht aus einer Aktivität (`CreateLocation`), die zwei interessante Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="a9fa5-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="a9fa5-104">Sie verfügt über erforderliche und optionale Argumente.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="a9fa5-105">Sie ermöglicht dem Benutzer, einen von zwei unterschiedlichen Argumentsätzen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="a9fa5-106">Dieses Verhalten wird mit den folgenden beiden Funktionen erzielt:</span><span class="sxs-lookup"><span data-stu-id="a9fa5-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="a9fa5-107">`[isRequired]` überprüft, ob eine Eigenschaft einer bestimmten Aktivität zugewiesen ist; falls nicht, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="a9fa5-108">`[OverloadGroup]` setzt einen Satz von Argumenten zusammen, damit der Benutzer der Aktivität eine Auswahl zwischen diesen treffen kann.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="a9fa5-109">Der Benutzer kann keine Argumente aus anderen Überladungsgruppen in der gleichen Instanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="a9fa5-110">Rufen Sie nach dem einrichtigen unterschiedlicher Workflows, <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> welche gibt eine <xref:System.Activities.Validation.ValidationResults> Auflistung von <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`.</span></span> <span data-ttu-id="a9fa5-111">Drucken der <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` Objekte in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-111">Print the <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a9fa5-112">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a9fa5-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a9fa5-113">Öffnen der **OverloadGroups.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9fa5-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a9fa5-114">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9fa5-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9fa5-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9fa5-117">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9fa5-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a9fa5-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## <a name="see-also"></a><span data-ttu-id="a9fa5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9fa5-119">See Also</span></span>
