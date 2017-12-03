---
title: "Emulierungsunterbrechung in einer While-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d2d1a0686b96d74bc39a654ee5c9b6f0972a12b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="emulating-breaking-in-a-while-activity"></a>Emulierungsunterbrechung in einer While-Aktivität
In diesem Beispiel wird veranschaulicht, wie der Schleifenmechanismus der folgenden Aktivitäten unterbrochen werden kann: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> und <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 Dies ist hilfreich, da [!INCLUDE[wf](../../../../includes/wf-md.md)] keine Aktivität zur Unterbrechung der Ausführung dieser Schleifen umfasst.  
  
## <a name="scenario"></a>Szenario  
 In dem Beispiel wird der erste zuverlässige Anbieter in einer Liste von Anbietern (Instanzen der `Vendor`-Klasse) gesucht. Jeder Anbieter verfügt über eine `ID`, einen `Name` und einen numerischen Zuverlässigkeitswert, der bestimmt, wie verlässlich der Anbieter ist. In dem Beispiel wird eine benutzerdefinierte Aktivität mit dem Namen `FindReliableVendor` erstellt, die zwei Eingabeparameter (eine Liste mit Anbietern und einem minimalen Zuverlässigkeitswert) empfängt und den ersten Anbieter der Liste zurückgibt, der eine Entsprechung für die angegebenen Kriterien darstellt.  
  
## <a name="breaking-a-loop"></a>Unterbrechen einer Schleife  
 [!INCLUDE[wf](../../../../includes/wf-md.md)] umfasst keine Aktivität zur Unterbrechung einer Schleife. In dem Codebeispiel wird die Unterbrechung einer Schleife durch Verwendung einer <xref:System.Activities.Statements.If>-Aktivität und mehreren Variablen erzielt. Im Beispiel wird die <xref:System.Activities.Statements.While>-Aktivität unterbrochen, sobald die `reliableVendor`-Variable einem anderen Wert als `null` zugewiesen wird.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine while-Schleife unterbrochen wird.  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "EmulatingBreakInWhile" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`