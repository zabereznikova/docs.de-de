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
# <a name="cancellation-handler-on-compensable-activity"></a>Abbruchhandler für kompensierbare Aktivität
In diesem Beispiel wird die Verwendung eines Abbruchhandlers für eine <xref:System.Activities.Statements.CompensableActivity> veranschaulicht.  
  
 Dieses Beispiel umfasst zwei Szenarien, die die Verwendung des Abbruchs von <xref:System.Activities.Statements.CompensableActivity> veranschaulichen. Das erste Szenario enthält eine kompensierbare Stammaktivität, die drei untergeordnete kompensierbare Aktivitäten enthält. Zwei untergeordnete Aktivitäten beenden ihre Aktivitätstextkörper erfolgreich. Wenn der Textkörper der dritten untergeordneten Aktivität ausgeführt wird, tritt eine Ausnahme auf, die durch das Abbrechen der Verarbeitung der dritten Aktivität behandelt wird. Anschließend wird der Abbruch der Stammaktivität ausgelöst. Die Logik der Stammaktivität in diesem Beispiel ist, die anderen beiden untergeordneten Aktivitäten zu kompensieren, die bereits abgeschlossen wurden.  
  
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
  
 Das zweite Szenario veranschaulicht das Ausführen eines <xref:System.Activities.Statements.TryCatch> parallel mit einem <xref:System.Activities.Statements.Delay>, der vor der <xref:System.Activities.Statements.TryCatch>-Verzweigung beendet wird. Die Abschlussbedingung wird auf `true` festgelegt, sobald die erste Verzweigung beendet wurde, woraufhin die andere Verzweigung abgebrochen wird.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die CompensationCancellation.sln-Projektmappe.  
  
2.  Erstellen Sie das Beispiel, indem Sie STRG+UMSCHALT+B drücken, oder wählen Sie im Menü Erstellen die Option Projektmappe erstellen aus.  
  
3.  Führen Sie das Beispiel aus, indem Sie F5 drücken, oder wählen Sie im Menü Debuggen die Option Debugging starten aus. Sie können auch STRG+F5 drücken oder im Menü Debuggen die Option Starten ohne Debugging auswählen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`  
  
## <a name="see-also"></a>Siehe auch
