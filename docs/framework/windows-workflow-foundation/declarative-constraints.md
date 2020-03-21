---
title: Deklarative Einschränkungen
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 321021e3d73daecae07268f33807c992414a7b4c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182964"
---
# <a name="declarative-constraints"></a><span data-ttu-id="5bd14-102">Deklarative Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bd14-102">Declarative Constraints</span></span>
<span data-ttu-id="5bd14-103">Deklarative Einschränkungen stellen eine leistungsstarke Validierungsmethode für eine Aktivität und ihre Beziehungen zu anderen Aktivitäten bereit.</span><span class="sxs-lookup"><span data-stu-id="5bd14-103">Declarative constraints provide a powerful method of validation for an activity and its relationships with other activities.</span></span> <span data-ttu-id="5bd14-104">Einschränkungen werden während des Erstellungsprozesses für eine Aktivität konfiguriert. Der Workflowhost kann jedoch zusätzliche Einschränkungen angeben.</span><span class="sxs-lookup"><span data-stu-id="5bd14-104">Constraints are configured for an activity during the authoring process, but additional constraints can also be specified by the workflow host.</span></span> <span data-ttu-id="5bd14-105">Dieses Thema bietet eine Übersicht darüber, wie mit deklarativen Einschränkungen Aktivitätsvalidierung bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5bd14-105">This topic provides an overview of using declarative constraints to provide activity validation.</span></span>  
  
## <a name="using-declarative-constraints"></a><span data-ttu-id="5bd14-106">Verwendung deklarativer Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bd14-106">Using Declarative Constraints</span></span>  
 <span data-ttu-id="5bd14-107">Eine Einschränkung ist eine Aktivität, die Validierungslogik enthält.</span><span class="sxs-lookup"><span data-stu-id="5bd14-107">A constraint is an activity that contains validation logic.</span></span> <span data-ttu-id="5bd14-108">Die Einschränkungsaktivität kann in Code oder in XAML erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5bd14-108">This constraint activity can be authored in code or in XAML.</span></span> <span data-ttu-id="5bd14-109">Nachdem eine Einschränkungsaktivität erstellt wurde, wird sie von Aktivitätsautoren der <xref:System.Activities.Activity.Constraints%2A>-Eigenschaft hinzugefügt, die validiert werden soll, oder die Autoren verwenden die Einschränkung, um zusätzliche Validierung mithilfe der <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>-Eigenschaft einer <xref:System.Activities.Validation.ValidationSettings>-Instanz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5bd14-109">After a constraint activity is created, activity authors add this constraint to the <xref:System.Activities.Activity.Constraints%2A> property of the activity to validate, or they use the constraint to provide additional validation by using the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> property of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="5bd14-110">Die Validierungslogik kann aus einfachen Validierungen wie der Validierung der Metadaten einer Aktivität bestehen, sie kann jedoch auch eine Validierung ausführen, die die Beziehung der betreffenden Aktivität zum übergeordneten Element, den untergeordneten Elementen und den gleichgeordneten Aktivitäten berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5bd14-110">The validation logic can consist of simple validations such as validating an activity’s metadata, but it can also perform validation that takes into account the relationship of the current activity to its parent, children, and sibling activities.</span></span> <span data-ttu-id="5bd14-111">Einschränkungen werden mit der <xref:System.Activities.Validation.Constraint%601>-Aktivität erstellt. Es werden mehrere zusätzliche Validierungsaktivitäten bereitgestellt, um die Erstellung von Validierungsfehlern und -warnungen zu unterstützen und Informationen zu verwandten Aktivitäten im Workflow zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="5bd14-111">Constraints are authored by using the <xref:System.Activities.Validation.Constraint%601> activity, and several additional validation activities are provided to assist with the creation of validation errors and warnings and to provide information about related activities in the workflow.</span></span>  
  
### <a name="assertvalidation-and-addvalidationerror"></a><span data-ttu-id="5bd14-112">AssertValidation und AddValidationError</span><span class="sxs-lookup"><span data-stu-id="5bd14-112">AssertValidation and AddValidationError</span></span>  
 <span data-ttu-id="5bd14-113">Die <xref:System.Activities.Validation.AssertValidation>-Aktivität wertet den Ausdruck aus, auf den von der <xref:System.Activities.Validation.AssertValidation.Assertion%2A>-Eigenschaft verwiesen wird. Wenn der ausgewertete Ausdruck `false` ergibt, wird <xref:System.Activities.Validation.ValidationResults> ein Validierungsfehler oder eine Warnung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5bd14-113">The <xref:System.Activities.Validation.AssertValidation> activity evaluates the expression referenced by its <xref:System.Activities.Validation.AssertValidation.Assertion%2A> property, and if the expression evaluates to `false`, a validation error or warning is added to the <xref:System.Activities.Validation.ValidationResults>.</span></span> <span data-ttu-id="5bd14-114">Die <xref:System.Activities.Validation.AssertValidation.Message%2A>-Eigenschaft beschreibt den Validierungsfehler, und die <xref:System.Activities.Validation.AssertValidation.IsWarning%2A>-Eigenschaft gibt an, ob es sich dabei um einen Fehler oder eine Warnung handelt.</span><span class="sxs-lookup"><span data-stu-id="5bd14-114">The <xref:System.Activities.Validation.AssertValidation.Message%2A> property describes the validation error and the <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> property indicates whether the validation failure is an error or a warning.</span></span> <span data-ttu-id="5bd14-115">Der Standardwert für <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="5bd14-115">The default value for <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> is `false`.</span></span>  
  
 <span data-ttu-id="5bd14-116">Im folgenden Beispiel wird eine Einschränkung deklariert, die eine Validierungswarnung zurückgibt, wenn der <xref:System.Activities.Activity.DisplayName%2A> der validierten Aktivität zwei Zeichen oder weniger umfasst.</span><span class="sxs-lookup"><span data-stu-id="5bd14-116">In the following example, a constraint is declared that returns a validation warning if the <xref:System.Activities.Activity.DisplayName%2A> of the activity being validated is two characters or less in length.</span></span> <span data-ttu-id="5bd14-117">Der generische Typparameter, der für das <xref:System.Activities.Validation.Constraint%601>-Objekt verwendet wird, gibt den Typ der Aktivität an, die von der Einschränkung validiert wird.</span><span class="sxs-lookup"><span data-stu-id="5bd14-117">The generic type parameter used for <xref:System.Activities.Validation.Constraint%601> specifies the type of activity that is validated by the constraint.</span></span> <span data-ttu-id="5bd14-118">Diese Einschränkung verwendet das <xref:System.Activities.Activity>-Objekt als generischen Typ. Mit ihr können alle Aktivitätstypen validiert werden.</span><span class="sxs-lookup"><span data-stu-id="5bd14-118">This constraint uses <xref:System.Activities.Activity> as the generic type and can be used to validate all types of activities.</span></span>  
  
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
  
 <span data-ttu-id="5bd14-119">Um diese Einschränkung für eine Aktivität anzugeben, wird sie den <xref:System.Activities.Activity.Constraints%2A> der Aktivität hinzugefügt, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bd14-119">To specify this constraint for an activity, it is added to the <xref:System.Activities.Activity.Constraints%2A> of the activity, as shown in the following example code.</span></span>  
  
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
  
 <span data-ttu-id="5bd14-120">Diese Einschränkung kann der Host auch mithilfe von <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> für Aktivitäten in einem Workflow angegeben. Dieses Thema wird im nächsten Abschnitt behandelt.</span><span class="sxs-lookup"><span data-stu-id="5bd14-120">The host could also specify this constraint for activities in a workflow by using <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, which is covered in the next section.</span></span>  
  
 <span data-ttu-id="5bd14-121">Mit der <xref:System.Activities.Validation.AddValidationError>-Aktivität wird ein Validierungsfehler oder eine Validierungswarnung generiert, ohne dass ein Ausdruck ausgewertet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5bd14-121">The <xref:System.Activities.Validation.AddValidationError> activity is used to generate a validation error or warning without requiring the evaluation of an expression.</span></span> <span data-ttu-id="5bd14-122">Ihre Eigenschaften stimmen zum großen Teil mit denen des <xref:System.Activities.Validation.AssertValidation>-Objekts überein, und die Aktivität kann zusammen mit den Flusssteuerungsaktivitäten einer Einschränkung wie der <xref:System.Activities.Statements.If>-Aktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bd14-122">Its properties are similar to <xref:System.Activities.Validation.AssertValidation> and it can be used in conjunction with flow control activities of a constraint such as the <xref:System.Activities.Statements.If> activity.</span></span>
  
### <a name="workflow-relationship-activities"></a><span data-ttu-id="5bd14-123">Workflowbeziehungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="5bd14-123">Workflow Relationship Activities</span></span>

<span data-ttu-id="5bd14-124">Es gibt mehrere Validierungsaktivitäten, die Informationen zu den anderen Aktivitäten im Workflow im Verhältnis zur validierten Aktivität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5bd14-124">Several validation activities are available that provide information about the other activities in the workflow in relation to the activity being validated.</span></span> <span data-ttu-id="5bd14-125"><xref:System.Activities.Validation.GetParentChain> gibt eine Auflistung von Aktivitäten zurück, die alle Aktivitäten zwischen der aktuellen Aktivität und der Stammaktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="5bd14-125"><xref:System.Activities.Validation.GetParentChain> returns a collection of activities that contains all of the activities between the current activity and the root activity.</span></span> <span data-ttu-id="5bd14-126"><xref:System.Activities.Validation.GetChildSubtree> stellt eine Auflistung von Aktivitäten bereit, die die untergeordneten Aktivitäten in einem rekursiven Muster enthält, und <xref:System.Activities.Validation.GetWorkflowTree> ruft alle Aktivitäten im Workflow ab.</span><span class="sxs-lookup"><span data-stu-id="5bd14-126"><xref:System.Activities.Validation.GetChildSubtree> provides a collection of activities that contains the child activities in a recursive pattern, and <xref:System.Activities.Validation.GetWorkflowTree> gets all the activities in the workflow.</span></span>  
  
<span data-ttu-id="5bd14-127">Im folgenden Beispiel wird eine `CreateState` -Aktivität definiert.</span><span class="sxs-lookup"><span data-stu-id="5bd14-127">In the following example, a `CreateState` activity is defined.</span></span> <span data-ttu-id="5bd14-128">Die `CreateState`-Aktivität muss in einer `CreateCountry`-Aktivität enthalten sein, und die `GetParent`-Methode gibt eine Einschränkung zurück, die diese Anforderung durchsetzt.</span><span class="sxs-lookup"><span data-stu-id="5bd14-128">The `CreateState` activity must be contained within a `CreateCountry` activity, and the `GetParent` method returns a constraint that enforces this requirement.</span></span> <span data-ttu-id="5bd14-129">`GetParent` verwendet die <xref:System.Activities.Validation.GetParentChain>-Aktivität in Verbindung mit einer <xref:System.Activities.Statements.ForEach%601>-Aktivität, um die übergeordneten Aktivitäten der `CreateState`-Aktivität zu überprüfen und zu ermitteln, ob die Anforderung erfüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="5bd14-129">`GetParent` uses the <xref:System.Activities.Validation.GetParentChain> activity in conjunction with a <xref:System.Activities.Statements.ForEach%601> activity to inspect the parent activities of the `CreateState` activity to determine if the requirement is met.</span></span>  
  
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
  
## <a name="additional-constraints"></a><span data-ttu-id="5bd14-130">Zusätzliche Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5bd14-130">Additional Constraints</span></span>  
 <span data-ttu-id="5bd14-131">Workflowhostautoren können zusätzliche Validierungseinschränkungen für Aktivitäten in einem Workflow angeben, indem sie Einschränkungen erstellen und dem <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>-Wörterbuch einer <xref:System.Activities.Validation.ValidationSettings>-Instanz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5bd14-131">Workflow host authors can specify additional validation constraints for activities in a workflow by creating constraints and adding them to the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> dictionary of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="5bd14-132">Jedes Element in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> enthält den Typ der Aktivität, für den die Einschränkungen gültig sind, sowie eine Liste der zusätzlichen Einschränkungen für diesen Aktivitätstyp.</span><span class="sxs-lookup"><span data-stu-id="5bd14-132">Each item in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contains the type of activity for which the constraints apply and a list of the additional constraints for that type of activity.</span></span> <span data-ttu-id="5bd14-133">Wenn die Validierung für den Workflow aufgerufen wird, wertet jede Aktivität des angegebenen Typs (einschließlich der abgeleiteten Klassen) die Einschränkungen aus.</span><span class="sxs-lookup"><span data-stu-id="5bd14-133">When validation is invoked for the workflow, each activity of the specified type, including derived classes, evaluates the constraints.</span></span> <span data-ttu-id="5bd14-134">In diesem Beispiel wird die `ActivityDisplayNameIsNotSetWarning`-Einschränkung aus dem vorherigen Abschnitt auf alle Aktivitäten in einem Workflow angewendet.</span><span class="sxs-lookup"><span data-stu-id="5bd14-134">In this example, the `ActivityDisplayNameIsNotSetWarning` constraint from the previous section is applied to all activities in a workflow.</span></span>  
  
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
  
 <span data-ttu-id="5bd14-135">Wenn die <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A>-Eigenschaft des <xref:System.Activities.Validation.ValidationSettings>-Objekts `true` ist, werden nur die angegebenen zusätzlichen Einschränkungen ausgewertet, nachdem die Validierung über den Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5bd14-135">If the <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> property of <xref:System.Activities.Validation.ValidationSettings> is `true`, then only the specified additional constraints are evaluated when validation is invoked by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="5bd14-136">Dies kann hilfreich sein, wenn überprüft wird, ob Workflows über bestimmte Validierungskonfigurationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="5bd14-136">This can be useful for inspecting workflows for specific validation configurations.</span></span> <span data-ttu-id="5bd14-137">Beachten Sie jedoch, dass beim Aufrufen des Workflows die im Workflow konfigurierte Validierungslogik ausgewertet wird und weitergegeben werden muss, damit der Workflow erfolgreich gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5bd14-137">Note however that when the workflow is invoked, the validation logic configured in the workflow is evaluated and must pass for the workflow to successfully begin.</span></span> <span data-ttu-id="5bd14-138">Weitere Informationen zum Aufrufen der Validierung finden Sie unter [Aufrufen der Aktivitätsvalidierung](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="5bd14-138">For more information about invoking validation, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>
