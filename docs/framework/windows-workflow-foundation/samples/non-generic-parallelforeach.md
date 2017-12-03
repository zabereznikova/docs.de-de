---
title: ParallelForEach (nicht generisch)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c8c02c920eda881f4a08925e3bff0567244e5c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="non-generic-parallelforeach"></a>ParallelForEach (nicht generisch)
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]geliefert wird in der Toolbox einen Satz von ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ParallelForEach%601>, womit durchlaufen <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` Sammlungen.  
  
 <xref:System.Activities.Statements.ParallelForEach%601>erfordert die <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> Eigenschaft vom Typ <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`. Dies schließt Benutzer davon, von Datenstrukturen, die implementieren durchlaufen <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` Schnittstelle (z. B. <xref:System.Collections.ArrayList>). Die nicht generische Version von <xref:System.Activities.Statements.ParallelForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.  
  
 In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität und der Designer implementiert werden. Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.  
  
## <a name="parallelforeach-activity"></a>Die ParallelForEachT-Aktivität  
 Die C#/VB-Anweisung `foreach` zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus. Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>. Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text. Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> weist eine <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> auf, damit die <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität vorzeitig abgeschlossen werden kann, wenn die Auswertung der <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> `true` zurückgibt. Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> wird nach dem Abschluss jeder Iteration ausgewertet.  
  
 In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet. Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.  
  
## <a name="class-definition"></a>Klassendefinition  
 Im folgenden Codebeispiel wird die Definition einer nicht generischen `ParallelForEach`-Aktivität veranschaulicht.  
  
```  
[ContentProperty("Body")]  
public class ParallelForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    public Activity<bool> CompletionCondition  
    [DefaultValue(null)]  
    [DependsOn("CompletionCondition")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 Text (optional)  
 Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird. Jedes einzelne Element wird durch die Argument-Eigenschaft in den Text übergeben.  
  
 Werte (optional)  
 Die Auflistung von Elementen, die durchlaufen werden. Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.  
  
 CompletionCondition (optional)  
 Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>-Eigenschaft wird ausgewertet, nachdem eine Iteration abgeschlossen wurde. Ergibt die Auswertung `true`, werden die geplanten ausstehenden Iterationen abgebrochen. Wenn diese Eigenschaft nicht festgelegt ist, werden alle Aktivitäten in der Verzweigungsauflistung bis zur Beendigung ausgeführt.  
  
## <a name="example-of-using-parallelforeach"></a>Beispiel für die Verwendung von ParallelForEach  
 Im folgenden Code wird veranschaulicht, wie die ParallelForEach-Aktivität in einer Anwendung verwendet wird.  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ParallelForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
## <a name="parallelforeach-designer"></a>ParallelForEach-Designer  
 Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität dient. Der Designer wird angezeigt, in der Toolbox unter die **Beispiele**, **nicht generische Aktivitäten** Kategorie. Der Designer ist mit dem Namen **ParallelForEachWithBodyFactory** in der Toolbox, da die Aktivität macht eine <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox, die mit einem ordnungsgemäß konfigurierten Aktivität erstellt <xref:System.Activities.ActivityAction>.  
  
```  
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:  
  
    1.  **CodeTestClient** wird gezeigt, wie die Aktivität mit Code zu verwenden.  
  
    2.  **DesignerTestClient** wird gezeigt, wie die Aktivität im Designer verwendet.  
  
2.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
