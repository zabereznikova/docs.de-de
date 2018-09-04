---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 0773e76d36b25ad5485cc8912c7012815412de9f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514135"
---
# <a name="overloadgroups"></a><span data-ttu-id="a740b-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="a740b-102">OverloadGroups</span></span>
<span data-ttu-id="a740b-103">Dieses Beispiel besteht aus einer Aktivität (`CreateLocation`), die zwei interessante Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="a740b-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="a740b-104">Sie verfügt über erforderliche und optionale Argumente.</span><span class="sxs-lookup"><span data-stu-id="a740b-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="a740b-105">Sie ermöglicht dem Benutzer, einen von zwei unterschiedlichen Argumentsätzen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a740b-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="a740b-106">Dieses Verhalten wird mit den folgenden beiden Funktionen erzielt:</span><span class="sxs-lookup"><span data-stu-id="a740b-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="a740b-107">`[isRequired]` überprüft, ob eine Eigenschaft einer bestimmten Aktivität zugewiesen ist; falls nicht, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a740b-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="a740b-108">`[OverloadGroup]` setzt einen Satz von Argumenten zusammen, damit der Benutzer der Aktivität eine Auswahl zwischen diesen treffen kann.</span><span class="sxs-lookup"><span data-stu-id="a740b-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="a740b-109">Der Benutzer kann keine Argumente aus anderen Überladungsgruppen in der gleichen Instanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="a740b-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="a740b-110">Rufen Sie nach dem Einrichtigen unterschiedlicher Workflows <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> auf, wodurch eine <xref:System.Activities.Validation.ValidationResults>-Auflistung von <xref:System.Activities.Validation.Constraint> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a740b-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="a740b-111">Geben Sie die <xref:System.Activities.Validation.Constraint>-Objekte auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="a740b-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a740b-112">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a740b-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a740b-113">Öffnen der **OverloadGroups.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a740b-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a740b-114">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="a740b-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a740b-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a740b-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a740b-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a740b-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a740b-117">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="a740b-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a740b-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a740b-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
