---
title: "Nicht generisches ForEach-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Nicht generisches ForEach-Element
Zur Toolbox von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehört ein Satz von Ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ForEach%601>, die das Durchlaufen von <xref:System.Collections.IEnumerable%601>\-Auflistungen ermöglicht.  
  
 Für <xref:System.Activities.Statements.ForEach%601> muss die <xref:System.Activities.Statements.ForEach%601.Values%2A>\-Eigenschaft den Typ <xref:System.Collections.IEnumerable%601> aufweisen.  Dies schließt Benutzer davon aus, Datenstrukturen zu durchlaufen, die die <xref:System.Collections.IEnumerable%601>\-Schnittstelle implementieren \(z. B. <xref:System.Collections.ArrayList>\).  Die nicht generische Version von <xref:System.Activities.Statements.ForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.  
  
 In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ForEach%601>\-Aktivität und der Designer implementiert werden.  Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.  
  
## ForEach\-Aktivität  
 Die C\#\/VB\-Anweisung `foreach` zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus.  Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Aktivitäten für `foreach` sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>.  Die <xref:System.Activities.Statements.ForEach%601>\-Aktivität enthält eine Liste von Werten und einen Text.  Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.  
  
 In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet.  Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>\-Schnittstelle implementieren, verwendet werden.  
  
## Klassendefinition  
 Im folgenden Codebeispiel wird die Definition einer nicht generischen `ForEach`\-Aktivität veranschaulicht.  
  
```  
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
  
 Text \(optional\)  
 Das <xref:System.Activities.ActivityAction>\-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird.  Jedes einzelne Element wird durch die `Argument`\-Eigenschaft in den Text übergeben.  
  
 Werte \(optional\)  
 Die Auflistung von Elementen, die durchlaufen werden.  Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.  
  
## Beispiel der Verwendung von ForEach  
 Im folgenden Code wird veranschaulicht, wie die ForEach\-Aktivität in einer Anwendung verwendet wird.  
  
```  
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
|---------------|-------------|-----------------|-----------------|  
|Werte sind `null`|Für das erforderliche Aktivitätsargument "Values1" wurde kein Wert angegeben.|Fehler|<xref:System.InvalidOperationException>|  
  
## ForEach\-Designer  
 Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ForEach%601>\-Aktivität dient.  Der Designer wird in der Toolbox unter **Beispiele**, Kategorie **Nicht generische Aktivitäten**, angezeigt.  Der Designer wird in der Toolbox **ForEachWithBodyFactory** genannt, da die Aktivität ein <xref:System.Activities.Presentation.IActivityTemplateFactory>\-Element in der Toolbox verfügbar macht, das die Aktivität mit einem ordnungsgemäß konfigurierten <xref:System.Activities.ActivityAction>\-Element erstellt.  
  
```  
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
  
#### So führen Sie dieses Beispiel aus  
  
1.  Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:  
  
    1.  **CodeTestClient** zeigt, wie die Aktivität mit Code verwendet wird.  
  
    2.  **DesignerTestClient** zeigt, wie die Aktivität im Designer verwendet wird.  
  
2.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`