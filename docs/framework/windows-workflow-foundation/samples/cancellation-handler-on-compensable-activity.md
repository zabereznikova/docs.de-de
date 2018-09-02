---
title: Abbruchhandler für kompensierbare Aktivität
ms.date: 03/30/2017
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
ms.openlocfilehash: 2f32d10e22be7fdd1e84229a214409df06efa918
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442706"
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="dfb41-102">Abbruchhandler für kompensierbare Aktivität</span><span class="sxs-lookup"><span data-stu-id="dfb41-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="dfb41-103">In diesem Beispiel wird die Verwendung eines Abbruchhandlers für eine <xref:System.Activities.Statements.CompensableActivity> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dfb41-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="dfb41-104">Dieses Beispiel umfasst zwei Szenarien, die die Verwendung des Abbruchs von <xref:System.Activities.Statements.CompensableActivity> veranschaulichen. Das erste Szenario enthält eine kompensierbare Stammaktivität, die drei untergeordnete kompensierbare Aktivitäten enthält.</span><span class="sxs-lookup"><span data-stu-id="dfb41-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="dfb41-105">Zwei untergeordnete Aktivitäten beenden ihre Aktivitätstextkörper erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="dfb41-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="dfb41-106">Wenn der Textkörper der dritten untergeordneten Aktivität ausgeführt wird, tritt eine Ausnahme auf, die durch das Abbrechen der Verarbeitung der dritten Aktivität behandelt wird. Anschließend wird der Abbruch der Stammaktivität ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dfb41-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="dfb41-107">Die Logik der Stammaktivität in diesem Beispiel ist, die anderen beiden untergeordneten Aktivitäten zu kompensieren, die bereits abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="dfb41-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
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
  
 <span data-ttu-id="dfb41-108">Das zweite Szenario veranschaulicht das Ausführen eines <xref:System.Activities.Statements.TryCatch> parallel mit einem <xref:System.Activities.Statements.Delay>, der vor der <xref:System.Activities.Statements.TryCatch>-Verzweigung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfb41-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="dfb41-109">Die Abschlussbedingung wird auf `true` festgelegt, sobald die erste Verzweigung beendet wurde, woraufhin die andere Verzweigung abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="dfb41-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dfb41-110">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="dfb41-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dfb41-111">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die CompensationCancellation.sln-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="dfb41-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="dfb41-112">Erstellen Sie das Beispiel, indem Sie STRG+UMSCHALT+B drücken, oder wählen Sie im Menü Erstellen die Option Projektmappe erstellen aus.</span><span class="sxs-lookup"><span data-stu-id="dfb41-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="dfb41-113">Führen Sie das Beispiel aus, indem Sie F5 drücken, oder wählen Sie im Menü Debuggen die Option Debugging starten aus.</span><span class="sxs-lookup"><span data-stu-id="dfb41-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="dfb41-114">Sie können auch STRG+F5 drücken oder im Menü Debuggen die Option Starten ohne Debugging auswählen.</span><span class="sxs-lookup"><span data-stu-id="dfb41-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfb41-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="dfb41-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dfb41-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dfb41-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dfb41-117">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="dfb41-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfb41-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dfb41-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`