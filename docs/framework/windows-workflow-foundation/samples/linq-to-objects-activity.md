---
title: "LINQ to Objects-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff77211000cfdda9c35e5a0dcbc69fc0eaf5c3be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-objects-activity"></a><span data-ttu-id="c34d9-102">LINQ to Objects-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c34d9-102">LINQ to Objects Activity</span></span>
<span data-ttu-id="c34d9-103">Dieses Beispiel veranschaulicht, wie eine Aktivität so erstellt wird, dass LINQ to Objects verwendet wird, um Elemente in einer Auflistung abzufragen.</span><span class="sxs-lookup"><span data-stu-id="c34d9-103">This sample demonstrates how to create an activity to use LINQ to Objects to query elements in a collection.</span></span>  
  
## <a name="activity-details-for-findincollection"></a><span data-ttu-id="c34d9-104">Aktivitätsdetails für FindInCollection</span><span class="sxs-lookup"><span data-stu-id="c34d9-104">Activity Details for FindInCollection</span></span>  
 <span data-ttu-id="c34d9-105">Diese Aktivität ermöglicht Benutzern die Abfrage von Elementen aus Auflistungen im Arbeitsspeicher mit LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="c34d9-105">This activity allows users to query elements from collections in memory using LINQ to Objects.</span></span> <span data-ttu-id="c34d9-106">Zum Filtern der Ergebnisse müssen Sie ein LINQ-Prädikat in Form eines Lambda-Ausdrucks bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c34d9-106">You must provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="c34d9-107">Diese Aktivität kann in Verbindung mit <xref:System.Activities.Statements.AddToCollection%601>-Aktivitäten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c34d9-107">This activity can be used in conjunction with <xref:System.Activities.Statements.AddToCollection%601> activities.</span></span>  
  
 <span data-ttu-id="c34d9-108">In der folgenden Tabelle werden die Eigenschaft und die Rückgabewerte für die Aktivität aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c34d9-108">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="c34d9-109">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c34d9-109">Property or Return Value</span></span>|<span data-ttu-id="c34d9-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c34d9-110">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="c34d9-111">`Collection`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c34d9-111">`Collection` property</span></span>|<span data-ttu-id="c34d9-112">Eine erforderliche Eigenschaft, die die Quellauflistung angibt.</span><span class="sxs-lookup"><span data-stu-id="c34d9-112">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="c34d9-113">`Predicate`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c34d9-113">`Predicate` property</span></span>|<span data-ttu-id="c34d9-114">Eine erforderliche Eigenschaft, die den Filter für die Auflistung in Form eines Lambda-Ausdrucks angibt.</span><span class="sxs-lookup"><span data-stu-id="c34d9-114">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="c34d9-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c34d9-115">Return Value</span></span>|<span data-ttu-id="c34d9-116">Die gefilterte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c34d9-116">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="c34d9-117">Codebeispiel, in dem die benutzerdefinierte Aktivität verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c34d9-117">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="c34d9-118">Im folgenden Codebeispiel wird die benutzerdefinierte `FindInCollection`-Aktivität verwendet, um alle Zeilen in einer Auflistung von Mitarbeitern zu suchen, deren `Role`-Eigenschaft auf `Manager` und deren `Location`-Eigenschaft auf `Redmond` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c34d9-118">The following code example uses the `FindInCollection` custom activity to find all rows in a collection of employees that have a `Role` property set to `Manager` and the `Location` property set to `Redmond`.</span></span>  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 <span data-ttu-id="c34d9-119">Im folgenden Code wird gezeigt, wie ein Workflowprogramm erstellt wird, das die benutzerdefinierte FindInCollection-Aktivität, die <xref:System.Activities.Statements.AddToCollection%601>-Aktivität und die <xref:System.Activities.Statements.ForEach%601>-Aktivität verwendet, um eine Auflistung mit Mitarbeitern aufzufüllen, alle Mitarbeiter zu suchen, die Entwickler in Redmond sind, und dann die Ergebnisliste zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="c34d9-119">The following code shows how to create a workflow program that uses the custom FindInCollection activity, <xref:System.Activities.Statements.AddToCollection%601>, and <xref:System.Activities.Statements.ForEach%601> activities to populate a collection with employees, find all the employees that have developer roles and are located in Redmond, and then iterate through the resulting list.</span></span>  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c34d9-120">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="c34d9-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="c34d9-121">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "LinqToObjects.sln".</span><span class="sxs-lookup"><span data-stu-id="c34d9-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToObjects.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c34d9-122">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c34d9-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c34d9-123">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c34d9-123">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c34d9-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c34d9-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c34d9-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c34d9-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c34d9-126">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="c34d9-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c34d9-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c34d9-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a><span data-ttu-id="c34d9-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c34d9-128">See Also</span></span>  
 [<span data-ttu-id="c34d9-129">Lambda-Ausdrücke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c34d9-129">Lambda Expressions (C# Programming Guide)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [<span data-ttu-id="c34d9-130">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="c34d9-130">LINQ to Objects</span></span>](http://go.microsoft.com/fwlink/?LinkID=150380)
