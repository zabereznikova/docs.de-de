---
title: DynamicActivity-Erstellung
ms.date: 03/30/2017
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
ms.openlocfilehash: 93435be69f90ca0b74dae6b934cb145fabb7afff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518101"
---
# <a name="dynamicactivity-creation"></a><span data-ttu-id="577ea-102">DynamicActivity-Erstellung</span><span class="sxs-lookup"><span data-stu-id="577ea-102">DynamicActivity Creation</span></span>
<span data-ttu-id="577ea-103">In diesem Beispiel werden zwei unterschiedliche Möglichkeiten zum Erstellen einer Aktivität mithilfe der <xref:System.Activities.DynamicActivity>-Aktivität zur Laufzeit veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="577ea-103">This sample demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 <span data-ttu-id="577ea-104">In diesem Beispiel wird zur Laufzeit eine Aktivität mit Text erstellt, der eine <xref:System.Activities.Statements.Sequence>-Aktivität enthält, die die <xref:System.Activities.Statements.ForEach%601>-Aktivität und die <xref:System.Activities.Statements.Assign%601>-Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="577ea-104">In this sample, an activity is created at runtime with a body that contains a <xref:System.Activities.Statements.Sequence> activity that contains <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.Assign%601> activities.</span></span> <span data-ttu-id="577ea-105">Eine Eingabeliste von Ganzzahlen wird an die Aktivität übergeben und als Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="577ea-105">An input list of integers is passed into the activity and set as a property.</span></span> <span data-ttu-id="577ea-106">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität durchläuft dann die Liste der Werte und akkumuliert diese.</span><span class="sxs-lookup"><span data-stu-id="577ea-106">The <xref:System.Activities.Statements.ForEach%601> activity then iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="577ea-107">In der <xref:System.Activities.Statements.Assign%601>-Aktivität wird der Durchschnittswert durch Teilen des Akkumulators durch die Anzahl von Elementen in der Liste und Zuweisen zum Durchschnitt berechnet.</span><span class="sxs-lookup"><span data-stu-id="577ea-107">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assign it to the average.</span></span>  
  
 <span data-ttu-id="577ea-108">In dem Beispiel wird die Verwendung einer <xref:System.Activities.DynamicActivity>-Aktivität veranschaulicht, die als Eingabeargumente in Variablen fließt und Werte als Ausgabeargumente zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="577ea-108">The sample demonstrates the usage of a <xref:System.Activities.DynamicActivity> activity that flows in variables as input arguments and returning values as output arguments.</span></span> <span data-ttu-id="577ea-109">Die Aktivität verfügt über ein Eingabeargument mit dem Namen `Numbers`, das eine Liste Ganzzahlen darstellt.</span><span class="sxs-lookup"><span data-stu-id="577ea-109">The activity has one input argument named `Numbers` that is a list of integers.</span></span> <span data-ttu-id="577ea-110">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität durchläuft die Liste der Werte und akkumuliert diese.</span><span class="sxs-lookup"><span data-stu-id="577ea-110">The <xref:System.Activities.Statements.ForEach%601> activity iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="577ea-111">In der <xref:System.Activities.Statements.Assign%601>-Aktivität wird der Durchschnittswert durch Teilen des Akkumulators durch die Anzahl von Elementen in der Liste und Zuweisen zum Durchschnitt berechnet.</span><span class="sxs-lookup"><span data-stu-id="577ea-111">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assigning it to the average.</span></span> <span data-ttu-id="577ea-112">Der Durchschnitt wird als Ausgabeargument mit dem Namen `Average` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="577ea-112">The average is returned as an output argument named `Average`.</span></span>  
  
 <span data-ttu-id="577ea-113">Wenn die dynamische Aktivität programmgesteuert erstellt wird, werden die Eingabe und die Ausgabe deklariert, wie im folgenden Codebeispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="577ea-113">When the dynamic activity is created programmatically, the input and output are declared as shown in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="577ea-114">Im folgenden Codebeispiel wird die vollständige Definition der `DynamicActivity` veranschaulicht, die den Durchschnitt der Werte in einer Liste berechnet.</span><span class="sxs-lookup"><span data-stu-id="577ea-114">The following code example shows the complete definition of the `DynamicActivity` that computes the average of the values in a list.</span></span>  
  
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
  
 <span data-ttu-id="577ea-115">Die Eingabe und Ausgabe wird (wenn in XAML erstellt) deklariert, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="577ea-115">When created in XAML, the input and output are declared as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="577ea-116">Der XAML-Code kann mithilfe von [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] visuell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="577ea-116">The XAML can be created visually using the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="577ea-117">Wenn es in einem Visual Studio-Projekt enthalten ist, achten Sie darauf, dass "Buildvorgang" auf "None" zu verhindern, dass es zu kompilierende festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="577ea-117">If it is included in a Visual Studio project, be sure to set its "Build Action" to "None" to prevent it from being compiled.</span></span> <span data-ttu-id="577ea-118">Der XAML-Code kann dann mithilfe des folgenden Aufrufs dynamisch geladen werden.</span><span class="sxs-lookup"><span data-stu-id="577ea-118">The XAML can then be loaded dynamically using the following call.</span></span>  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 <span data-ttu-id="577ea-119">Die <xref:System.Activities.DynamicActivity>-Instanz, die programmgesteuert oder durch Laden eines XAML-Workflows erstellt wurde, kann wie im folgenden Codebeispiel dargestellt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="577ea-119">The <xref:System.Activities.DynamicActivity> instance created programmatically or through loading a XAML workflow can be used as shown in the following code example.</span></span> <span data-ttu-id="577ea-120">Bitte beachten Sie, dass "act" zum Übergeben der `WorkflowInvoker.Invoke` ist "Act" <xref:System.Activities.Activity> im ersten Codebeispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="577ea-120">Please note that "act" passed to the `WorkflowInvoker.Invoke` is the "act" <xref:System.Activities.Activity> defined in the first code example.</span></span>  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="577ea-121">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="577ea-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="577ea-122">Öffnen Sie die Projektmappendatei "DynamicActivityCreation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="577ea-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DynamicActivityCreation.sln solution file.</span></span>  
  
2.  <span data-ttu-id="577ea-123">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="577ea-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="577ea-124">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="577ea-124">To run the solution, press CTRL+F5.</span></span>  
  
## <a name="command-line-arguments"></a><span data-ttu-id="577ea-125">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="577ea-125">Command line arguments</span></span>  
 <span data-ttu-id="577ea-126">In diesem Beispiel werden Befehlszeilenargumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="577ea-126">This sample accepts command line arguments.</span></span> <span data-ttu-id="577ea-127">Benutzer können eine Liste von Zahlen bereitstellen, damit die Aktivität ihren Durchschnitt berechnet.</span><span class="sxs-lookup"><span data-stu-id="577ea-127">Users can provide a list of numbers for the activity to calculate their average.</span></span> <span data-ttu-id="577ea-128">Die Liste der zu verwendenden Zahlen wird als eine Liste von Zahlen übergeben, die durch ein Leerzeichen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="577ea-128">The list of numbers to be used is passed as a list of numbers separated by a space.</span></span> <span data-ttu-id="577ea-129">Um beispielsweise den Durchschnitt von 5, 10 und 32 zu berechnen, rufen Sie das Beispiel mithilfe der folgenden Befehlszeile auf.</span><span class="sxs-lookup"><span data-stu-id="577ea-129">For example, to calculate the average of 5, 10, and 32 invoke the sample using the following command line.</span></span>  
  
 <span data-ttu-id="577ea-130">**DynamicActivityCreation 5 10 32**</span><span class="sxs-lookup"><span data-stu-id="577ea-130">**DynamicActivityCreation 5 10 32**</span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="577ea-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="577ea-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="577ea-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="577ea-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="577ea-133">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="577ea-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="577ea-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="577ea-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`