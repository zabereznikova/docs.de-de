---
title: "Abbruchhandler für kompensierbare Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b39b5d9277767160225a34be9e0c71a36e7b6d78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="f4791-102">Abbruchhandler für kompensierbare Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4791-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="f4791-103">In diesem Beispiel wird die Verwendung eines Abbruchhandlers für eine <xref:System.Activities.Statements.CompensableActivity> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f4791-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="f4791-104">Dieses Beispiel umfasst zwei Szenarien, die die Verwendung des Abbruchs von <xref:System.Activities.Statements.CompensableActivity> veranschaulichen. Das erste Szenario enthält eine kompensierbare Stammaktivität, die drei untergeordnete kompensierbare Aktivitäten enthält.</span><span class="sxs-lookup"><span data-stu-id="f4791-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="f4791-105">Zwei untergeordnete Aktivitäten beenden ihre Aktivitätstextkörper erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f4791-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="f4791-106">Wenn der Textkörper der dritten untergeordneten Aktivität ausgeführt wird, tritt eine Ausnahme auf, die durch das Abbrechen der Verarbeitung der dritten Aktivität behandelt wird. Anschließend wird der Abbruch der Stammaktivität ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f4791-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="f4791-107">Die Logik der Stammaktivität in diesem Beispiel ist, die anderen beiden untergeordneten Aktivitäten zu kompensieren, die bereits abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="f4791-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="f4791-108">Das zweite Szenario veranschaulicht das Ausführen eines <xref:System.Activities.Statements.TryCatch> parallel mit einem <xref:System.Activities.Statements.Delay>, der vor der <xref:System.Activities.Statements.TryCatch>-Verzweigung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4791-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="f4791-109">Die Abschlussbedingung wird auf `true` festgelegt, sobald die erste Verzweigung beendet wurde, woraufhin die andere Verzweigung abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="f4791-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f4791-110">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f4791-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f4791-111">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die CompensationCancellation.sln-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="f4791-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="f4791-112">Erstellen Sie das Beispiel, indem Sie STRG+UMSCHALT+B drücken, oder wählen Sie im Menü Erstellen die Option Projektmappe erstellen aus.</span><span class="sxs-lookup"><span data-stu-id="f4791-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="f4791-113">Führen Sie das Beispiel aus, indem Sie F5 drücken, oder wählen Sie im Menü Debuggen die Option Debugging starten aus.</span><span class="sxs-lookup"><span data-stu-id="f4791-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="f4791-114">Sie können auch STRG+F5 drücken oder im Menü Debuggen die Option Starten ohne Debugging auswählen.</span><span class="sxs-lookup"><span data-stu-id="f4791-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4791-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f4791-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f4791-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f4791-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f4791-117">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f4791-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f4791-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f4791-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`  
  
## <a name="see-also"></a><span data-ttu-id="f4791-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4791-119">See Also</span></span>
