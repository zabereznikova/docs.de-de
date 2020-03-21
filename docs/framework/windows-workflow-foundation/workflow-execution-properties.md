---
title: Eigenschaften der Workflowausführung
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: 0f958e7e112bfddc2740c2605d446493f2d49010
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182661"
---
# <a name="workflow-execution-properties"></a><span data-ttu-id="9f5ee-102">Eigenschaften der Workflowausführung</span><span class="sxs-lookup"><span data-stu-id="9f5ee-102">Workflow Execution Properties</span></span>
<span data-ttu-id="9f5ee-103">Durch TLS (Thread Local Storage, threadlokaler Speicher) behält die CLR einen Ausführungskontext für jeden Thread bei.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-103">Through thread local storage (TLS), the CLR maintains an execution context for each thread.</span></span> <span data-ttu-id="9f5ee-104">Dieser Ausführungskontext bestimmt bekannte Threadeigenschaften wie die Threadidentität, die Ambient-Transaktion und den aktuellen Berechtigungssatz zusätzlich zu benutzerdefinierten Threadeigenschaften, z. B. benannte Slots.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-104">This execution context governs well-known thread properties such as the thread identity, the ambient transaction, and the current permission set in addition to user-defined thread properties like named slots.</span></span>  
  
 <span data-ttu-id="9f5ee-105">Im Gegensatz zu Programmen, die direkt mit der CLR verwendet werden, sind Workflowprogramme hierarchisch bewertete Strukturen von Aktivitäten, die in einer threadagnostischen Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-105">Unlike programs directly targeting the CLR, workflow programs are hierarchically scoped trees of activities that execute in a thread-agnostic environment.</span></span> <span data-ttu-id="9f5ee-106">Dies bedeutet, dass mit den Standard-TLS-Mechanismen nicht direkt bestimmt werden kann, welcher Kontext im Bereich eines bestimmten Arbeitselements liegt.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-106">This implies that the standard TLS mechanisms cannot directly be used to determine what context is in scope for a given work item.</span></span> <span data-ttu-id="9f5ee-107">Zwei parallele Verzweigungen der Ausführung können z. B. unterschiedliche Transaktionen verwenden, der Planer kann sie jedoch zeitgleich für denselben CLR-Thread ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-107">For example, two parallel branches of execution might use different transactions, yet the scheduler might interleave their execution on the same CLR thread.</span></span>  
  
 <span data-ttu-id="9f5ee-108">Die Eigenschaften der Workflowausführung stellen eine Möglichkeit bereit, der Umgebung einer Aktivität kontextspezifische Eigenschaften hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-108">Workflow execution properties provide a mechanism to add context specific properties to an activity’s environment.</span></span> <span data-ttu-id="9f5ee-109">Damit kann von einer Aktivität deklariert werden, welche Eigenschaften im Bereich ihrer Unterstruktur liegen, und es werden Hooks für das Einrichten und Beenden für den TLS bereitgestellt, damit eine ordnungsgemäße Zusammenarbeit mit CLR-Objekten ermöglicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-109">This allows an activity to declare which properties are in scope for its sub-tree and also provides hooks for setting up and tearing down TLS to properly interoperate with CLR objects.</span></span>  
  
## <a name="creating-and-using-workflow-execution-properties"></a><span data-ttu-id="9f5ee-110">Erstellen und Verwenden von Eigenschaften für die Workflowausführung</span><span class="sxs-lookup"><span data-stu-id="9f5ee-110">Creating and Using Workflow Execution Properties</span></span>  
 <span data-ttu-id="9f5ee-111">Eigenschaften für die Workflowausführung implementieren normalerweise die <xref:System.Activities.IExecutionProperty>-Schnittstelle, obwohl die Eigenschaften, die für Messaging verwendet werden, stattdessen <xref:System.ServiceModel.Activities.ISendMessageCallback> und <xref:System.ServiceModel.Activities.IReceiveMessageCallback> implementieren können.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-111">Workflow execution properties usually implement the <xref:System.Activities.IExecutionProperty> interface, though properties focused on messaging may implement <xref:System.ServiceModel.Activities.ISendMessageCallback> and <xref:System.ServiceModel.Activities.IReceiveMessageCallback> instead.</span></span> <span data-ttu-id="9f5ee-112">Erstellen Sie für eine neue Eigenschaft für die Workflowausführung eine Klasse, die die <xref:System.Activities.IExecutionProperty>-Schnittstelle implementiert, und implementieren Sie den <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A>-Member und den <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>-Member.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-112">To create a workflow execution property, create a class that implements the <xref:System.Activities.IExecutionProperty> interface and implement the members <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> and <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>.</span></span> <span data-ttu-id="9f5ee-113">Mithilfe dieser Member kann von der Ausführungseigenschaft für jeden Arbeitsschritt der Aktivität mit dieser Eigenschaft (einschließlich etwaiger untergeordneter Aktivitäten) der lokale Threadspeicher ordnungsgemäß eingerichtet und beendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-113">These members provide the execution property with an opportunity to properly set up and tear down the thread local storage during each pulse of work of the activity that contains the property, including any child activities.</span></span> <span data-ttu-id="9f5ee-114">In diesem Beispiel wird eine `ConsoleColorProperty` erstellt, mit der die `Console.ForegroundColor` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-114">In this example, a `ConsoleColorProperty` is created that sets the `Console.ForegroundColor`.</span></span>  
  
```csharp  
class ConsoleColorProperty : IExecutionProperty  
{  
    public const string Name = "ConsoleColorProperty";  
  
    ConsoleColor original;  
    ConsoleColor color;  
  
    public ConsoleColorProperty(ConsoleColor color)  
    {  
        this.color = color;  
    }  
  
    void IExecutionProperty.SetupWorkflowThread()  
    {  
        original = Console.ForegroundColor;  
        Console.ForegroundColor = color;  
    }  
  
    void IExecutionProperty.CleanupWorkflowThread()  
    {  
        Console.ForegroundColor = original;  
    }  
}  
```  
  
 <span data-ttu-id="9f5ee-115">Aktivitätsautoren können diese Eigenschaft verwenden, indem sie sie in der Überschreibung der Ausführung registrieren.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-115">Activity authors can use this property by registering it in the activity’s execute override.</span></span> <span data-ttu-id="9f5ee-116">In diesem Beispiel wird eine `ConsoleColorScope`-Aktivität definiert, die die `ConsoleColorProperty` registriert, indem diese der <xref:System.Activities.NativeActivityContext.Properties%2A>-Auflistung des aktuellen <xref:System.Activities.NativeActivityContext> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-116">In this example, a `ConsoleColorScope` activity is defined that registers the `ConsoleColorProperty` by adding it to the <xref:System.Activities.NativeActivityContext.Properties%2A> collection of the current <xref:System.Activities.NativeActivityContext>.</span></span>  
  
```csharp  
public sealed class ConsoleColorScope : NativeActivity  
{  
    public ConsoleColorScope()  
        : base()  
    {  
    }  
  
    public ConsoleColor Color { get; set; }  
    public Activity Body { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        context.Properties.Add(ConsoleColorProperty.Name, new ConsoleColorProperty(this.Color));  
  
        if (this.Body != null)  
        {  
            context.ScheduleActivity(this.Body);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="9f5ee-117">Wenn der Text der Aktivität einen Arbeitsschritt einleitet, wird die <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A>-Methode der Eigenschaft aufgerufen, und nach Abschluss des Schritts wird der <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-117">When the activity’s body starts a pulse of work, the <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> method of the property is called, and when the pulse of work is complete, the <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> is called.</span></span> <span data-ttu-id="9f5ee-118">In diesem Beispiel wird ein Workflow erstellt, der eine <xref:System.Activities.Statements.Parallel>-Aktivität mit drei Branches verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-118">In this example, a workflow is created that uses a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="9f5ee-119">Die ersten zwei Verzweigungen verwenden die `ConsoleColorScope`-Aktivität, die dritte Verzweigung jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-119">The first two branches use the `ConsoleColorScope` activity and the third branch does not.</span></span> <span data-ttu-id="9f5ee-120">Alle drei Branches enthalten zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten und eine <xref:System.Activities.Statements.Delay>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-120">All three branches contain two <xref:System.Activities.Statements.WriteLine> activities and a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="9f5ee-121">Wenn die <xref:System.Activities.Statements.Parallel>-Aktivität ausgeführt wird, werden die in den Verzweigungen enthaltenen Aktivitäten parallel ausgeführt. Bei der Ausführung der einzelnen untergeordneten Aktivitäten wird jedoch die richtige Konsolenfarbe von der `ConsoleColorProperty` angewendet.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-121">When the <xref:System.Activities.Statements.Parallel> activity executes, the activities that are contained in the branches execute in an interleaved manner, but as each child activity executes the correct console color is applied by the `ConsoleColorProperty`.</span></span>  
  
```csharp  
Activity wf = new Parallel  
{  
    Branches =
    {  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Blue,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start blue text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End blue text."  
                    }  
                }  
            }  
        },  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Red,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start red text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End red text."  
                    }  
                }  
            }  
        },  
        new Sequence  
        {  
            Activities =
            {  
                new WriteLine  
                {  
                    Text = "Start default text."  
                },  
                new Delay  
                {  
                    Duration = TimeSpan.FromSeconds(1)  
                },  
                new WriteLine  
                {  
                    Text = "End default text."  
                }  
            }  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 <span data-ttu-id="9f5ee-122">Beim Aufruf des Workflows wird die folgende Ausgabe in das Konsolenfenster geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-122">When the workflow is invoked, the following output is written to the console window.</span></span>  
  
```console  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
> <span data-ttu-id="9f5ee-123">Obwohl keine entsprechende Anzeige in der vorangehenden Ausgabe erfolgt, wird jede Textzeile im Konsolenfenster in der angegebenen Farbe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-123">Although it is not shown in the previous output, each line of text in the console window is displayed in the indicated color.</span></span>  
  
 <span data-ttu-id="9f5ee-124">Die Eigenschaften der Workflowausführung können von benutzerdefinierten Aktivitätsautoren verwendet werden. Sie stellen außerdem einen Mechanismus zur Handleverwaltung für Aktivitäten bereit, z. B. für die <xref:System.ServiceModel.Activities.CorrelationScope>-Aktivität und <xref:System.Activities.Statements.TransactionScope>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9f5ee-124">Workflow execution properties can be used by custom activity authors, and they also provide the mechanism for handle management for activities such as the <xref:System.ServiceModel.Activities.CorrelationScope> and <xref:System.Activities.Statements.TransactionScope> activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5ee-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f5ee-125">See also</span></span>

- <xref:System.Activities.IExecutionProperty>
- <xref:System.Activities.IPropertyRegistrationCallback>
- <xref:System.Activities.RegistrationContext>
