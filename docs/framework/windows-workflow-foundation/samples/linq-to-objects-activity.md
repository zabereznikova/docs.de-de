---
title: LINQ to Objects-Aktivität
ms.date: 03/30/2017
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
ms.openlocfilehash: fca4a94a951c9713a61914de6ef33e0cbb74f75e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552767"
---
# <a name="linq-to-objects-activity"></a>LINQ to Objects-Aktivität
Dieses Beispiel veranschaulicht, wie eine Aktivität so erstellt wird, dass LINQ to Objects verwendet wird, um Elemente in einer Auflistung abzufragen.  
  
## <a name="activity-details-for-findincollection"></a>Aktivitätsdetails für FindInCollection  
 Diese Aktivität ermöglicht Benutzern die Abfrage von Elementen aus Auflistungen im Arbeitsspeicher mit LINQ to Objects. Zum Filtern der Ergebnisse müssen Sie ein LINQ-Prädikat in Form eines Lambda-Ausdrucks bereitstellen. Diese Aktivität kann in Verbindung mit <xref:System.Activities.Statements.AddToCollection%601>-Aktivitäten verwendet werden.  
  
 In der folgenden Tabelle werden die Eigenschaft und die Rückgabewerte für die Aktivität aufgelistet.  
  
|Eigenschaft oder Rückgabewert|Beschreibung|  
|------------------------------|-----------------|  
|`Collection`-Eigenschaft|Eine erforderliche Eigenschaft, die die Quellauflistung angibt.|  
|`Predicate`-Eigenschaft|Eine erforderliche Eigenschaft, die den Filter für die Auflistung in Form eines Lambda-Ausdrucks angibt.|  
|Rückgabewert|Die gefilterte Auflistung.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Codebeispiel, in dem die benutzerdefinierte Aktivität verwendet wird  
 Im folgenden Codebeispiel wird die benutzerdefinierte `FindInCollection`-Aktivität verwendet, um alle Zeilen in einer Auflistung von Mitarbeitern zu suchen, deren `Role`-Eigenschaft auf `Manager` und deren `Location`-Eigenschaft auf `Redmond` festgelegt ist.  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 Im folgenden Code wird gezeigt, wie ein Workflowprogramm erstellt wird, das die benutzerdefinierte FindInCollection-Aktivität, die <xref:System.Activities.Statements.AddToCollection%601>-Aktivität und die <xref:System.Activities.Statements.ForEach%601>-Aktivität verwendet, um eine Auflistung mit Mitarbeitern aufzufüllen, alle Mitarbeiter zu suchen, die Entwickler in Redmond sind, und dann die Ergebnisliste zu durchlaufen.  
  
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
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "LinqToObjects.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke (C#-Programmierhandbuch)](https://go.microsoft.com/fwlink/?LinkId=150381)  
 [LINQ to Objects](https://go.microsoft.com/fwlink/?LinkID=150380)
