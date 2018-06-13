---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 489d27e05c96d3b3893052254a879d1c9d75788c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515622"
---
# <a name="overloadgroups"></a><span data-ttu-id="4cefb-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="4cefb-102">OverloadGroups</span></span>
<span data-ttu-id="4cefb-103">Dieses Beispiel besteht aus einer Aktivität (`CreateLocation`), die zwei interessante Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="4cefb-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="4cefb-104">Sie verfügt über erforderliche und optionale Argumente.</span><span class="sxs-lookup"><span data-stu-id="4cefb-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="4cefb-105">Sie ermöglicht dem Benutzer, einen von zwei unterschiedlichen Argumentsätzen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4cefb-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="4cefb-106">Dieses Verhalten wird mit den folgenden beiden Funktionen erzielt:</span><span class="sxs-lookup"><span data-stu-id="4cefb-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="4cefb-107">`[isRequired]` überprüft, ob eine Eigenschaft einer bestimmten Aktivität zugewiesen ist; falls nicht, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4cefb-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="4cefb-108">`[OverloadGroup]` setzt einen Satz von Argumenten zusammen, damit der Benutzer der Aktivität eine Auswahl zwischen diesen treffen kann.</span><span class="sxs-lookup"><span data-stu-id="4cefb-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="4cefb-109">Der Benutzer kann keine Argumente aus anderen Überladungsgruppen in der gleichen Instanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cefb-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="4cefb-110">Rufen Sie nach dem Einrichtigen unterschiedlicher Workflows <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> auf, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.Constraint> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4cefb-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="4cefb-111">Geben Sie die <xref:System.Activities.Validation.Constraint>-Objekte auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="4cefb-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4cefb-112">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="4cefb-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4cefb-113">Öffnen der **OverloadGroups.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cefb-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cefb-114">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="4cefb-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4cefb-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="4cefb-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4cefb-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="4cefb-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4cefb-117">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4cefb-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4cefb-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4cefb-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
