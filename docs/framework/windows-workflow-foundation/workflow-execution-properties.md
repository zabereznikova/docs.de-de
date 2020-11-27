---
title: Eigenschaften der Workflowausführung
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: be9ae5924786ea1e23cc649034d927789c64e405
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293792"
---
# <a name="workflow-execution-properties"></a>Eigenschaften der Workflowausführung

Durch TLS (Thread Local Storage, threadlokaler Speicher) behält die CLR einen Ausführungskontext für jeden Thread bei. Dieser Ausführungskontext bestimmt bekannte Threadeigenschaften wie die Threadidentität, die Ambient-Transaktion und den aktuellen Berechtigungssatz zusätzlich zu benutzerdefinierten Threadeigenschaften, z. B. benannte Slots.  
  
 Im Gegensatz zu Programmen, die direkt mit der CLR verwendet werden, sind Workflowprogramme hierarchisch bewertete Strukturen von Aktivitäten, die in einer threadagnostischen Umgebung ausgeführt werden. Dies bedeutet, dass mit den Standard-TLS-Mechanismen nicht direkt bestimmt werden kann, welcher Kontext im Bereich eines bestimmten Arbeitselements liegt. Zwei parallele Verzweigungen der Ausführung können z. B. unterschiedliche Transaktionen verwenden, der Planer kann sie jedoch zeitgleich für denselben CLR-Thread ausführen.  
  
 Die Eigenschaften der Workflowausführung stellen eine Möglichkeit bereit, der Umgebung einer Aktivität kontextspezifische Eigenschaften hinzuzufügen. Damit kann von einer Aktivität deklariert werden, welche Eigenschaften im Bereich ihrer Unterstruktur liegen, und es werden Hooks für das Einrichten und Beenden für den TLS bereitgestellt, damit eine ordnungsgemäße Zusammenarbeit mit CLR-Objekten ermöglicht werden kann.  
  
## <a name="creating-and-using-workflow-execution-properties"></a>Erstellen und Verwenden von Eigenschaften für die Workflowausführung  

 Eigenschaften für die Workflowausführung implementieren normalerweise die <xref:System.Activities.IExecutionProperty>-Schnittstelle, obwohl die Eigenschaften, die für Messaging verwendet werden, stattdessen <xref:System.ServiceModel.Activities.ISendMessageCallback> und <xref:System.ServiceModel.Activities.IReceiveMessageCallback> implementieren können. Erstellen Sie für eine neue Eigenschaft für die Workflowausführung eine Klasse, die die <xref:System.Activities.IExecutionProperty>-Schnittstelle implementiert, und implementieren Sie den <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A>-Member und den <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>-Member. Mithilfe dieser Member kann von der Ausführungseigenschaft für jeden Arbeitsschritt der Aktivität mit dieser Eigenschaft (einschließlich etwaiger untergeordneter Aktivitäten) der lokale Threadspeicher ordnungsgemäß eingerichtet und beendet werden. In diesem Beispiel wird eine `ConsoleColorProperty` erstellt, mit der die `Console.ForegroundColor` festgelegt wird.  
  
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
  
 Aktivitätsautoren können diese Eigenschaft verwenden, indem sie sie in der Überschreibung der Ausführung registrieren. In diesem Beispiel wird eine `ConsoleColorScope`-Aktivität definiert, die die `ConsoleColorProperty` registriert, indem diese der <xref:System.Activities.NativeActivityContext.Properties%2A>-Auflistung des aktuellen <xref:System.Activities.NativeActivityContext> hinzugefügt wird.  
  
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
  
 Wenn der Text der Aktivität einen Arbeitsschritt einleitet, wird die <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A>-Methode der Eigenschaft aufgerufen, und nach Abschluss des Schritts wird der <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> aufgerufen. In diesem Beispiel wird ein Workflow erstellt, der eine <xref:System.Activities.Statements.Parallel>-Aktivität mit drei Branches verwendet. Die ersten zwei Verzweigungen verwenden die `ConsoleColorScope`-Aktivität, die dritte Verzweigung jedoch nicht. Alle drei Branches enthalten zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten und eine <xref:System.Activities.Statements.Delay>-Aktivität. Wenn die <xref:System.Activities.Statements.Parallel>-Aktivität ausgeführt wird, werden die in den Verzweigungen enthaltenen Aktivitäten parallel ausgeführt. Bei der Ausführung der einzelnen untergeordneten Aktivitäten wird jedoch die richtige Konsolenfarbe von der `ConsoleColorProperty` angewendet.  
  
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
  
 Beim Aufruf des Workflows wird die folgende Ausgabe in das Konsolenfenster geschrieben.  
  
```console  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
> Obwohl keine entsprechende Anzeige in der vorangehenden Ausgabe erfolgt, wird jede Textzeile im Konsolenfenster in der angegebenen Farbe angezeigt.  
  
 Die Eigenschaften der Workflowausführung können von benutzerdefinierten Aktivitätsautoren verwendet werden. Sie stellen außerdem einen Mechanismus zur Handleverwaltung für Aktivitäten bereit, z. B. für die <xref:System.ServiceModel.Activities.CorrelationScope>-Aktivität und <xref:System.Activities.Statements.TransactionScope>-Aktivität.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Activities.IExecutionProperty>
- <xref:System.Activities.IPropertyRegistrationCallback>
- <xref:System.Activities.RegistrationContext>
