---
title: Deklarative Einschränkungen
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 9098a3d79337689fef6d37e4cccf3633d8128a10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236454"
---
# <a name="declarative-constraints"></a>Deklarative Einschränkungen

Deklarative Einschränkungen stellen eine leistungsstarke Validierungsmethode für eine Aktivität und ihre Beziehungen zu anderen Aktivitäten bereit. Einschränkungen werden während des Erstellungsprozesses für eine Aktivität konfiguriert. Der Workflowhost kann jedoch zusätzliche Einschränkungen angeben. Dieses Thema bietet eine Übersicht darüber, wie mit deklarativen Einschränkungen Aktivitätsvalidierung bereitgestellt werden kann.  
  
## <a name="using-declarative-constraints"></a>Verwendung deklarativer Einschränkungen  

 Eine Einschränkung ist eine Aktivität, die Validierungslogik enthält. Die Einschränkungsaktivität kann in Code oder in XAML erstellt werden. Nachdem eine Einschränkungsaktivität erstellt wurde, wird sie von Aktivitätsautoren der <xref:System.Activities.Activity.Constraints%2A>-Eigenschaft hinzugefügt, die validiert werden soll, oder die Autoren verwenden die Einschränkung, um zusätzliche Validierung mithilfe der <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>-Eigenschaft einer <xref:System.Activities.Validation.ValidationSettings>-Instanz bereitzustellen. Die Validierungslogik kann aus einfachen Validierungen wie der Validierung der Metadaten einer Aktivität bestehen, sie kann jedoch auch eine Validierung ausführen, die die Beziehung der betreffenden Aktivität zum übergeordneten Element, den untergeordneten Elementen und den gleichgeordneten Aktivitäten berücksichtigt. Einschränkungen werden mit der <xref:System.Activities.Validation.Constraint%601>-Aktivität erstellt. Es werden mehrere zusätzliche Validierungsaktivitäten bereitgestellt, um die Erstellung von Validierungsfehlern und -warnungen zu unterstützen und Informationen zu verwandten Aktivitäten im Workflow zur Verfügung zu stellen.  
  
### <a name="assertvalidation-and-addvalidationerror"></a>AssertValidation und AddValidationError  

 Die <xref:System.Activities.Validation.AssertValidation>-Aktivität wertet den Ausdruck aus, auf den von der <xref:System.Activities.Validation.AssertValidation.Assertion%2A>-Eigenschaft verwiesen wird. Wenn der ausgewertete Ausdruck `false` ergibt, wird <xref:System.Activities.Validation.ValidationResults> ein Validierungsfehler oder eine Warnung hinzugefügt. Die <xref:System.Activities.Validation.AssertValidation.Message%2A>-Eigenschaft beschreibt den Validierungsfehler, und die <xref:System.Activities.Validation.AssertValidation.IsWarning%2A>-Eigenschaft gibt an, ob es sich dabei um einen Fehler oder eine Warnung handelt. Der Standardwert für <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> ist `false`.  
  
 Im folgenden Beispiel wird eine Einschränkung deklariert, die eine Validierungswarnung zurückgibt, wenn der <xref:System.Activities.Activity.DisplayName%2A> der validierten Aktivität zwei Zeichen oder weniger umfasst. Der generische Typparameter, der für das <xref:System.Activities.Validation.Constraint%601>-Objekt verwendet wird, gibt den Typ der Aktivität an, die von der Einschränkung validiert wird. Diese Einschränkung verwendet das <xref:System.Activities.Activity>-Objekt als generischen Typ. Mit ihr können alle Aktivitätstypen validiert werden.  
  
```csharp  
public static Constraint ActivityDisplayNameIsNotSetWarning()  
{  
    DelegateInArgument<Activity> element = new DelegateInArgument<Activity>();  
  
    return new Constraint<Activity>  
    {  
        Body = new ActivityAction<Activity, ValidationContext>  
        {  
            Argument1 = element,  
            Handler = new AssertValidation  
            {  
                IsWarning = true,  
                Assertion = new InArgument<bool>(env => (element.Get(env).DisplayName.Length > 2)),  
                Message = new InArgument<string>("It is a best practice to have a DisplayName of more than 2 characters."),  
            }  
        }  
    };  
}  
```  
  
 Um diese Einschränkung für eine Aktivität anzugeben, wird sie den <xref:System.Activities.Activity.Constraints%2A> der Aktivität hinzugefügt, wie im folgenden Beispielcode gezeigt.  
  
```csharp  
public sealed class SampleActivity : CodeActivity  
{  
    public SampleActivity()  
    {  
        base.Constraints.Add(ActivityDisplayNameIsNotSetWarning());  
    }  
  
    // Activity implementation omitted.  
}  
```  
  
 Diese Einschränkung kann der Host auch mithilfe von <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> für Aktivitäten in einem Workflow angegeben. Dieses Thema wird im nächsten Abschnitt behandelt.  
  
 Mit der <xref:System.Activities.Validation.AddValidationError>-Aktivität wird ein Validierungsfehler oder eine Validierungswarnung generiert, ohne dass ein Ausdruck ausgewertet werden muss. Ihre Eigenschaften stimmen zum großen Teil mit denen des <xref:System.Activities.Validation.AssertValidation>-Objekts überein, und die Aktivität kann zusammen mit den Flusssteuerungsaktivitäten einer Einschränkung wie der <xref:System.Activities.Statements.If>-Aktivität verwendet werden.
  
### <a name="workflow-relationship-activities"></a>Workflowbeziehungsaktivitäten

Es gibt mehrere Validierungsaktivitäten, die Informationen zu den anderen Aktivitäten im Workflow im Verhältnis zur validierten Aktivität bereitstellen. <xref:System.Activities.Validation.GetParentChain> gibt eine Auflistung von Aktivitäten zurück, die alle Aktivitäten zwischen der aktuellen Aktivität und der Stammaktivität enthält. <xref:System.Activities.Validation.GetChildSubtree> stellt eine Auflistung von Aktivitäten bereit, die die untergeordneten Aktivitäten in einem rekursiven Muster enthält, und <xref:System.Activities.Validation.GetWorkflowTree> ruft alle Aktivitäten im Workflow ab.  
  
Im folgenden Beispiel wird eine `CreateState` -Aktivität definiert. Die `CreateState`-Aktivität muss in einer `CreateCountry`-Aktivität enthalten sein, und die `GetParent`-Methode gibt eine Einschränkung zurück, die diese Anforderung durchsetzt. `GetParent` verwendet die <xref:System.Activities.Validation.GetParentChain>-Aktivität in Verbindung mit einer <xref:System.Activities.Statements.ForEach%601>-Aktivität, um die übergeordneten Aktivitäten der `CreateState`-Aktivität zu überprüfen und zu ermitteln, ob die Anforderung erfüllt wurde.  
  
```csharp  
public sealed class CreateState : CodeActivity  
{  
    public CreateState()  
    {  
        base.Constraints.Add(CheckParent());  
        this.Cities = new List<Activity>();
    }  
  
    public List<Activity> Cities { get; set; }  
  
    public string Name { get; set; }
  
    static Constraint CheckParent()  
    {  
        DelegateInArgument<CreateState> element = new DelegateInArgument<CreateState>();  
        DelegateInArgument<ValidationContext> context = new DelegateInArgument<ValidationContext>();
        Variable<bool> result = new Variable<bool>();  
        DelegateInArgument<Activity> parent = new DelegateInArgument<Activity>();  
  
        return new Constraint<CreateState>  
        {
            Body = new ActivityAction<CreateState,ValidationContext>  
            {
                Argument1 = element,  
                Argument2 = context,  
                Handler = new Sequence  
                {  
                    Variables =  
                    {  
                        result
                    },  
                    Activities =  
                    {  
                        new ForEach<Activity>  
                        {
                            Values = new GetParentChain  
                            {  
                                ValidationContext = context
                            },  
                            Body = new ActivityAction<Activity>  
                            {
                                Argument = parent,
                                Handler = new If()  
                                {
                                    Condition = new InArgument<bool>((env) => object.Equals(parent.Get(env).GetType(),typeof(CreateCountry))),
                                    Then = new Assign<bool>  
                                    {  
                                        Value = true,  
                                        To = result  
                                    }  
                                }  
                            }
                        },  
                        new AssertValidation  
                        {  
                            Assertion = new InArgument<bool>(result),  
                            Message = new InArgument<string> ("CreateState has to be inside a CreateCountry activity"),
                        }  
                    }  
                }  
            }  
        };  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // not needed for the sample  
    }  
}  
```
  
## <a name="additional-constraints"></a>Zusätzliche Einschränkungen  

 Workflowhostautoren können zusätzliche Validierungseinschränkungen für Aktivitäten in einem Workflow angeben, indem sie Einschränkungen erstellen und dem <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>-Wörterbuch einer <xref:System.Activities.Validation.ValidationSettings>-Instanz hinzufügen. Jedes Element in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> enthält den Typ der Aktivität, für den die Einschränkungen gültig sind, sowie eine Liste der zusätzlichen Einschränkungen für diesen Aktivitätstyp. Wenn die Validierung für den Workflow aufgerufen wird, wertet jede Aktivität des angegebenen Typs (einschließlich der abgeleiteten Klassen) die Einschränkungen aus. In diesem Beispiel wird die `ActivityDisplayNameIsNotSetWarning`-Einschränkung aus dem vorherigen Abschnitt auf alle Aktivitäten in einem Workflow angewendet.  
  
```csharp  
Activity wf = new Sequence  
{  
    // Workflow Details Omitted.  
};  
  
ValidationSettings settings = new ValidationSettings()  
{  
  
    AdditionalConstraints =  
    {  
        {typeof(Activity), new List<Constraint> {ActivityDisplayNameIsNotSetWarning()}},
    }  
};  
  
// Validate the workflow.  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
// Evaluate the results.  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error in " + error.Source.DisplayName + ": " + error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning in " + warning.Source.DisplayName + ": " + warning.Message);  
    }  
}  
```  
  
 Wenn die <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A>-Eigenschaft des <xref:System.Activities.Validation.ValidationSettings>-Objekts `true` ist, werden nur die angegebenen zusätzlichen Einschränkungen ausgewertet, nachdem die Validierung über den Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufgerufen wird. Dies kann hilfreich sein, wenn überprüft wird, ob Workflows über bestimmte Validierungskonfigurationen verfügen. Beachten Sie jedoch, dass beim Aufrufen des Workflows die im Workflow konfigurierte Validierungslogik ausgewertet wird und weitergegeben werden muss, damit der Workflow erfolgreich gestartet werden kann. Weitere Informationen zum Aufrufen der Validierung finden Sie unter [Aufrufen der Aktivitäts Validierung](invoking-activity-validation.md).
