---
title: "DynamicActivity-Erstellung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# DynamicActivity-Erstellung
In diesem Beispiel werden zwei unterschiedliche Möglichkeiten zum Erstellen einer Aktivität mithilfe der <xref:System.Activities.DynamicActivity>\-Aktivität zur Laufzeit veranschaulicht.  
  
 In diesem Beispiel wird zur Laufzeit eine Aktivität mit Text erstellt, der eine <xref:System.Activities.Statements.Sequence>\-Aktivität enthält, die die <xref:System.Activities.Statements.ForEach%601>\-Aktivität und die <xref:System.Activities.Statements.Assign%601>\-Aktivität enthält.Eine Eingabeliste von Ganzzahlen wird an die Aktivität übergeben und als Eigenschaft festgelegt.Die <xref:System.Activities.Statements.ForEach%601>\-Aktivität durchläuft dann die Liste der Werte und akkumuliert diese.In der <xref:System.Activities.Statements.Assign%601>\-Aktivität wird der Durchschnittswert durch Teilen des Akkumulators durch die Anzahl von Elementen in der Liste und Zuweisen zum Durchschnitt berechnet.  
  
 In dem Beispiel wird die Verwendung einer <xref:System.Activities.DynamicActivity>\-Aktivität veranschaulicht, die als Eingabeargumente in Variablen fließt und Werte als Ausgabeargumente zurückgibt.Die Aktivität verfügt über ein Eingabeargument mit dem Namen `Numbers`, das eine Liste Ganzzahlen darstellt.Die <xref:System.Activities.Statements.ForEach%601>\-Aktivität durchläuft die Liste der Werte und akkumuliert diese.In der <xref:System.Activities.Statements.Assign%601>\-Aktivität wird der Durchschnittswert durch Teilen des Akkumulators durch die Anzahl von Elementen in der Liste und Zuweisen zum Durchschnitt berechnet.Der Durchschnitt wird als Ausgabeargument mit dem Namen `Average` zurückgegeben.  
  
 Wenn die dynamische Aktivität programmgesteuert erstellt wird, werden die Eingabe und die Ausgabe deklariert, wie im folgenden Codebeispiel dargestellt.  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
  
```  
  
 Im folgenden Codebeispiel wird die vollständige Definition der `DynamicActivity` veranschaulicht, die den Durchschnitt der Werte in einer Liste berechnet.  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 Die Eingabe und Ausgabe wird \(wenn in XAML erstellt\) deklariert, wie im folgenden Beispiel dargestellt.  
  
```  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 Der XAML\-Code kann mithilfe von [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] visuell erstellt werden.Wenn er in einem Visual Studio\-Projekt enthalten ist, legen Sie die den Buildvorgang auf "None" fest, um zu verhindern, dass der Code kompiliert wird.Der XAML\-Code kann dann mithilfe des folgenden Aufrufs dynamisch geladen werden.  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
  
```  
  
 Die <xref:System.Activities.DynamicActivity>\-Instanz, die programmgesteuert oder durch Laden eines XAML\-Workflows erstellt wurde, kann wie im folgenden Codebeispiel dargestellt verwendet werden.Beachten Sie, dass die an den `WorkflowInvoker.Invoke` übergebene "Act" die im ersten Codebeispiel definierte "Act" <xref:System.Activities.Activity> ist.  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
  
```  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "DynamicActivityCreation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
## Befehlszeilenargumente  
 In diesem Beispiel werden Befehlszeilenargumente akzeptiert.Benutzer können eine Liste von Zahlen bereitstellen, damit die Aktivität ihren Durchschnitt berechnet.Die Liste der zu verwendenden Zahlen wird als eine Liste von Zahlen übergeben, die durch ein Leerzeichen getrennt sind.Um beispielsweise den Durchschnitt von 5, 10 und 32 zu berechnen, rufen Sie das Beispiel mithilfe der folgenden Befehlszeile auf.  
  
 **DynamicActivityCreation 5 10 32**   
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`  
  
## Siehe auch