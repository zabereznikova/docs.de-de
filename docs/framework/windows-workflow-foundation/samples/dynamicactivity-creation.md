---
title: DynamicActivity-Erstellung
ms.date: 03/30/2017
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
ms.openlocfilehash: 93435be69f90ca0b74dae6b934cb145fabb7afff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dynamicactivity-creation"></a>DynamicActivity-Erstellung
In diesem Beispiel werden zwei unterschiedliche Möglichkeiten zum Erstellen einer Aktivität mithilfe der <xref:System.Activities.DynamicActivity>-Aktivität zur Laufzeit veranschaulicht.  
  
 In diesem Beispiel wird zur Laufzeit eine Aktivität mit Text erstellt, der eine <xref:System.Activities.Statements.Sequence>-Aktivität enthält, die die <xref:System.Activities.Statements.ForEach%601>-Aktivität und die <xref:System.Activities.Statements.Assign%601>-Aktivität enthält. Eine Eingabeliste von Ganzzahlen wird an die Aktivität übergeben und als Eigenschaft festgelegt. Die <xref:System.Activities.Statements.ForEach%601>-Aktivität durchläuft dann die Liste der Werte und akkumuliert diese. In der <xref:System.Activities.Statements.Assign%601>-Aktivität wird der Durchschnittswert durch Teilen des Akkumulators durch die Anzahl von Elementen in der Liste und Zuweisen zum Durchschnitt berechnet.  
  
 In dem Beispiel wird die Verwendung einer <xref:System.Activities.DynamicActivity>-Aktivität veranschaulicht, die als Eingabeargumente in Variablen fließt und Werte als Ausgabeargumente zurückgibt. Die Aktivität verfügt über ein Eingabeargument mit dem Namen `Numbers`, das eine Liste Ganzzahlen darstellt. Die <xref:System.Activities.Statements.ForEach%601>-Aktivität durchläuft die Liste der Werte und akkumuliert diese. In der <xref:System.Activities.Statements.Assign%601>-Aktivität wird der Durchschnittswert durch Teilen des Akkumulators durch die Anzahl von Elementen in der Liste und Zuweisen zum Durchschnitt berechnet. Der Durchschnitt wird als Ausgabeargument mit dem Namen `Average` zurückgegeben.  
  
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
  
 Die Eingabe und Ausgabe wird (wenn in XAML erstellt) deklariert, wie im folgenden Beispiel dargestellt.  
  
```xml  
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
  
 Der XAML-Code kann mithilfe von [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] visuell erstellt werden. Wenn es in einem Visual Studio-Projekt enthalten ist, achten Sie darauf, dass "Buildvorgang" auf "None" zu verhindern, dass es zu kompilierende festgelegt wird. Der XAML-Code kann dann mithilfe des folgenden Aufrufs dynamisch geladen werden.  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 Die <xref:System.Activities.DynamicActivity>-Instanz, die programmgesteuert oder durch Laden eines XAML-Workflows erstellt wurde, kann wie im folgenden Codebeispiel dargestellt verwendet werden. Bitte beachten Sie, dass "act" zum Übergeben der `WorkflowInvoker.Invoke` ist "Act" <xref:System.Activities.Activity> im ersten Codebeispiel definiert.  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei "DynamicActivityCreation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
## <a name="command-line-arguments"></a>Befehlszeilenargumente  
 In diesem Beispiel werden Befehlszeilenargumente akzeptiert. Benutzer können eine Liste von Zahlen bereitstellen, damit die Aktivität ihren Durchschnitt berechnet. Die Liste der zu verwendenden Zahlen wird als eine Liste von Zahlen übergeben, die durch ein Leerzeichen getrennt sind. Um beispielsweise den Durchschnitt von 5, 10 und 32 zu berechnen, rufen Sie das Beispiel mithilfe der folgenden Befehlszeile auf.  
  
 **DynamicActivityCreation 5 10 32**  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`