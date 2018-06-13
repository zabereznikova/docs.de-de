---
title: Emulierungsunterbrechung in einer While-Aktivität
ms.date: 03/30/2017
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
ms.openlocfilehash: 37c64c2b8dc03d58f9c2802edef644fe4888e87d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514712"
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="6465a-102">Emulierungsunterbrechung in einer While-Aktivität</span><span class="sxs-lookup"><span data-stu-id="6465a-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="6465a-103">In diesem Beispiel wird veranschaulicht, wie der Schleifenmechanismus der folgenden Aktivitäten unterbrochen werden kann: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> und <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="6465a-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="6465a-104">Dies ist hilfreich, da Windows Workflow Foundation (WF) keine Aktivität zur Unterbrechung der Ausführung dieser Schleifen umfasst enthält.</span><span class="sxs-lookup"><span data-stu-id="6465a-104">This is useful because Windows Workflow Foundation (WF) does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="6465a-105">Szenario</span><span class="sxs-lookup"><span data-stu-id="6465a-105">Scenario</span></span>  
 <span data-ttu-id="6465a-106">In dem Beispiel wird der erste zuverlässige Anbieter in einer Liste von Anbietern (Instanzen der `Vendor`-Klasse) gesucht.</span><span class="sxs-lookup"><span data-stu-id="6465a-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="6465a-107">Jeder Anbieter verfügt über eine `ID`, einen `Name` und einen numerischen Zuverlässigkeitswert, der bestimmt, wie verlässlich der Anbieter ist.</span><span class="sxs-lookup"><span data-stu-id="6465a-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="6465a-108">In dem Beispiel wird eine benutzerdefinierte Aktivität mit dem Namen `FindReliableVendor` erstellt, die zwei Eingabeparameter (eine Liste mit Anbietern und einem minimalen Zuverlässigkeitswert) empfängt und den ersten Anbieter der Liste zurückgibt, der eine Entsprechung für die angegebenen Kriterien darstellt.</span><span class="sxs-lookup"><span data-stu-id="6465a-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="6465a-109">Unterbrechen einer Schleife</span><span class="sxs-lookup"><span data-stu-id="6465a-109">Breaking a Loop</span></span>  
 <span data-ttu-id="6465a-110">Windows Workflow Foundation (WF) umfasst keine Aktivität zur Unterbrechung einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="6465a-110">Windows Workflow Foundation (WF) does not include an activity to break a loop.</span></span> <span data-ttu-id="6465a-111">In dem Codebeispiel wird die Unterbrechung einer Schleife durch Verwendung einer <xref:System.Activities.Statements.If>-Aktivität und mehreren Variablen erzielt.</span><span class="sxs-lookup"><span data-stu-id="6465a-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="6465a-112">Im Beispiel wird die <xref:System.Activities.Statements.While>-Aktivität unterbrochen, sobald die `reliableVendor`-Variable einem anderen Wert als `null` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6465a-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="6465a-113">Im folgenden Codebeispiel wird veranschaulicht, wie eine while-Schleife unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="6465a-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6465a-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="6465a-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="6465a-115">Öffnen Sie die Projektmappendatei "EmulatingBreakInWhile" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6465a-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6465a-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6465a-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6465a-117">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6465a-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6465a-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6465a-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6465a-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6465a-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6465a-120">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="6465a-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6465a-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6465a-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`