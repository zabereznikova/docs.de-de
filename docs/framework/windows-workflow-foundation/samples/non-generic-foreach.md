---
title: Nicht generisches ForEach-Element
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 93a6b1d815ef6478974ceadf8ad935be2a3bdea5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338658"
---
# <a name="non-generic-foreach"></a>Nicht generisches ForEach-Element
Zur Toolbox von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehört ein Satz von Ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ForEach%601>, die das Durchlaufen von <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen ermöglicht.  
  
 Für <xref:System.Activities.Statements.ForEach%601> muss die <xref:System.Activities.Statements.ForEach%601.Values%2A>-Eigenschaft den Typ <xref:System.Collections.Generic.IEnumerable%601> aufweisen. Dies schließt Benutzer davon aus, Datenstrukturen zu durchlaufen, die die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementieren (z. B. <xref:System.Collections.ArrayList>). Die nicht generische Version von <xref:System.Activities.Statements.ForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.  
  
 In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ForEach%601>-Aktivität und der Designer implementiert werden. Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.  
  
## <a name="foreach-activity"></a>ForEach-Aktivität  
 Die C#/Visual Basic `foreach`-Anweisung zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus. Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten für `foreach` sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>. Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text. Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.  
  
 In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet. Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.  
  
## <a name="class-definition"></a>Klassendefinition  
 Im folgenden Codebeispiel wird die Definition einer nicht generischen `ForEach`-Aktivität veranschaulicht.  
  
```csharp  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 Text (optional)  
 Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird. Jedes einzelne Element wird durch die `Argument`-Eigenschaft in den Text übergeben.  
  
 Werte (optional)  
 Die Auflistung von Elementen, die durchlaufen werden. Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.  
  
## <a name="example-of-using-foreach"></a>Beispiel der Verwendung von ForEach  
 Im folgenden Code wird veranschaulicht, wie die ForEach-Aktivität in einer Anwendung verwendet wird.  
  
```csharp  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
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
  
|Bedingung|Meldung|Schweregrad|Ausnahmetyp|  
|---------------|-------------|--------------|--------------------|  
|Werte sind `null`|Für das erforderliche Aktivitätsargument "Values1" wurde kein Wert angegeben.|Fehler|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a>ForEach-Designer  
 Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ForEach%601>-Aktivität dient. Der Designer wird in der Toolbox in der Kategorie **Beispiele**, **nicht generische Aktivitäten** angezeigt. Der Designer wird in der Toolbox **ForEachWithBodyFactory** genannt, da die-Aktivität ein <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox verfügbar macht, das die Aktivität mit einem ordnungsgemäß konfigurierten <xref:System.Activities.ActivityAction>erstellt.  
  
```csharp  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
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
  
#### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus  
  
1. Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:  
  
    1. **Codetestclient** zeigt, wie die-Aktivität mithilfe von Code verwendet wird.  
  
    2. **Designertestclient** zeigt, wie die-Aktivität innerhalb des Designers verwendet wird.  
  
2. Erstellen Sie das Projekt, und führen Sie es aus.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
