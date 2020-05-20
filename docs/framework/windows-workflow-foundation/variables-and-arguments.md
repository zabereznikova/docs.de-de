---
title: Variablen und Argumente
description: In diesem Artikel werden die Variablen, die die Speicherung von Daten darstellen, und Argumente beschrieben, die den Datenfluss in eine bzw. aus einer Aktivität in Workflow Foundation darstellen.
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: 47b8a7bddc8c3a9a8427bcb3e93760a63e5fa976
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421305"
---
# <a name="variables-and-arguments"></a><span data-ttu-id="bcd63-103">Variablen und Argumente</span><span class="sxs-lookup"><span data-stu-id="bcd63-103">Variables and Arguments</span></span>
<span data-ttu-id="bcd63-104">In Windows Workflow Foundation (WF) stellen Variablen die Speicherung von Daten dar, und Argumente stellen den Datenfluss in eine und aus einer Aktivität dar.</span><span class="sxs-lookup"><span data-stu-id="bcd63-104">In Windows Workflow Foundation (WF), variables represent the storage of data and arguments represent the flow of data into and out of an activity.</span></span> <span data-ttu-id="bcd63-105">Eine Aktivität verfügt über einen Satz von Argumenten, die die Signatur der Aktivität ausmachen.</span><span class="sxs-lookup"><span data-stu-id="bcd63-105">An activity has a set of arguments and they make up the signature of the activity.</span></span> <span data-ttu-id="bcd63-106">Darüber hinaus kann eine Aktivität eine Liste von Variablen verwalten. Ein Entwickler kann während des Entwurfs eines Workflows Variablen zu dieser Liste hinzufügen oder daraus löschen.</span><span class="sxs-lookup"><span data-stu-id="bcd63-106">Additionally, an activity can maintain a list of variables to which a developer can add or remove variables during the design of a workflow.</span></span> <span data-ttu-id="bcd63-107">Ein Argument wird mit einem Ausdruck gebunden, der einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bcd63-107">An argument is bound using an expression that returns a value.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="bcd63-108">Variablen</span><span class="sxs-lookup"><span data-stu-id="bcd63-108">Variables</span></span>  
 <span data-ttu-id="bcd63-109">Variablen sind Speicherorte für Daten.</span><span class="sxs-lookup"><span data-stu-id="bcd63-109">Variables are storage locations for data.</span></span> <span data-ttu-id="bcd63-110">Variablen werden als Teil der Definition eines Workflows deklariert.</span><span class="sxs-lookup"><span data-stu-id="bcd63-110">Variables are declared as part of the definition of a workflow.</span></span> <span data-ttu-id="bcd63-111">Variablen nehmen zur Laufzeit Werte an, die dann als Teil des Zustands einer Workflowinstanz gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-111">Variables take on values at runtime and these values are stored as part of the state of a workflow instance.</span></span> <span data-ttu-id="bcd63-112">Eine Variablendefinition gibt den Typ der Variable und optional auch ihren Namen an.</span><span class="sxs-lookup"><span data-stu-id="bcd63-112">A variable definition specifies the type of the variable and optionally, the name.</span></span> <span data-ttu-id="bcd63-113">Im folgenden Code wird gezeigt, wie eine Variable deklariert und ihr mit einer <xref:System.Activities.Statements.Assign%601>-Aktivität ein Wert zugewiesen wird und wie der Wert mithilfe einer <xref:System.Activities.Statements.WriteLine>-Aktivität in der Konsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bcd63-113">The following code shows how to declare a variable, assign a value to it using an <xref:System.Activities.Statements.Assign%601> activity, and then display its value to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
```csharp  
// Define a variable named "str" of type string.  
Variable<string> var = new Variable<string>  
{  
    Name = "str"  
};  
  
// Declare the variable within a Sequence, assign  
// a value to it, and then display it.  
Activity wf = new Sequence()  
{  
    Variables = { var },  
    Activities =  
    {  
        new Assign<string>  
        {  
            To = var,  
            Value = "Hello World."  
        },  
        new WriteLine  
        {  
            Text = var  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 <span data-ttu-id="bcd63-114">Ein Standardwertausdruck kann optional als Teil einer Variablendeklaration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-114">A default value expression can optionally be specified as part of a variable declaration.</span></span> <span data-ttu-id="bcd63-115">Variablen können auch über Modifizierer verfügen.</span><span class="sxs-lookup"><span data-stu-id="bcd63-115">Variables also can have modifiers.</span></span> <span data-ttu-id="bcd63-116">Wenn z. B. eine Variable schreibgeschützt ist, kann der <xref:System.Activities.VariableModifiers>-Schreibschutmodifizierer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-116">For example, if a variable is read-only then the read-only <xref:System.Activities.VariableModifiers> modifier can be applied.</span></span> <span data-ttu-id="bcd63-117">Im folgenden Beispiel wird eine schreibgeschützte Variable erstellt, die über einen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="bcd63-117">In the following example, a read-only variable is created that has a default value assigned.</span></span>  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a><span data-ttu-id="bcd63-118">Variablengültigkeit</span><span class="sxs-lookup"><span data-stu-id="bcd63-118">Variable Scoping</span></span>  
 <span data-ttu-id="bcd63-119">Die Lebensdauer einer Variable zur Laufzeit entspricht der Lebensdauer der Aktivität, von der die Variable deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="bcd63-119">The lifetime of a variable at runtime is equal to the lifetime of the activity that declares it.</span></span> <span data-ttu-id="bcd63-120">Wenn eine Aktivität abgeschlossen wird, werden ihre Variablen bereinigt, und es kann nicht mehr darauf verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-120">When an activity completes, its variables are cleaned up and can no longer be referenced.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="bcd63-121">Argumente</span><span class="sxs-lookup"><span data-stu-id="bcd63-121">Arguments</span></span>  
 <span data-ttu-id="bcd63-122">Aktivitätsautoren definieren die Datenflüsse in und aus einer Aktivität mithilfe von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="bcd63-122">Activity authors use arguments to define the way data flows into and out of an activity.</span></span> <span data-ttu-id="bcd63-123">Jedes Argument verfügt über eine angegebene Richtung: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out> oder <xref:System.Activities.ArgumentDirection.InOut>.</span><span class="sxs-lookup"><span data-stu-id="bcd63-123">Each argument has a specified direction: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out>, or <xref:System.Activities.ArgumentDirection.InOut>.</span></span>  
  
 <span data-ttu-id="bcd63-124">Die Workflowlaufzeit gewährleistet folgende Aktionen hinsichtlich der zeitlichen Steuerung der Datenverschiebung in und aus Aktivitäten:</span><span class="sxs-lookup"><span data-stu-id="bcd63-124">The workflow runtime makes the following guarantees about the timing of data movement into and out of activities:</span></span>  
  
1. <span data-ttu-id="bcd63-125">Wenn die Ausführung einer Aktivität beginnt, werden die Werte aller Eingabeargumente und Eingabe-/Ausgabeargumente berechnet.</span><span class="sxs-lookup"><span data-stu-id="bcd63-125">When an activity starts executing, the values of all of its input and input/output arguments are calculated.</span></span> <span data-ttu-id="bcd63-126">Beispielsweise entspricht unabhängig davon, wann <xref:System.Activities.Argument.Get%2A> aufgerufen wird, der zurückgegebene Wert dem Wert, der vor dem Aufruf von `Execute` von der Laufzeit berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="bcd63-126">For example, regardless of when <xref:System.Activities.Argument.Get%2A> is called, the value returned is the one calculated by the runtime prior to its invocation of `Execute`.</span></span>  
  
2. <span data-ttu-id="bcd63-127">Wenn <xref:System.Activities.InOutArgument%601.Set%2A> aufgerufen wird, legt die Laufzeit den Wert sofort fest.</span><span class="sxs-lookup"><span data-stu-id="bcd63-127">When <xref:System.Activities.InOutArgument%601.Set%2A> is called, the runtime sets the value immediately.</span></span>  
  
3. <span data-ttu-id="bcd63-128">Für Argumente kann optional <xref:System.Activities.Argument.EvaluationOrder%2A> angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-128">Arguments can optionally have their <xref:System.Activities.Argument.EvaluationOrder%2A> specified.</span></span> <span data-ttu-id="bcd63-129"><xref:System.Activities.Argument.EvaluationOrder%2A> ist ein nullbasierter Wert, der die Reihenfolge angibt, in der das Argument ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="bcd63-129"><xref:System.Activities.Argument.EvaluationOrder%2A> is a zero-based value that specifies the order in which the argument is evaluated.</span></span> <span data-ttu-id="bcd63-130">Standardmäßig ist die Auswertungsreihenfolge des Arguments nicht angegeben und entspricht dem <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>-Wert.</span><span class="sxs-lookup"><span data-stu-id="bcd63-130">By default, the evaluation order of the argument is unspecified and is equal to the <xref:System.Activities.Argument.UnspecifiedEvaluationOrder> value.</span></span> <span data-ttu-id="bcd63-131">Legen Sie <xref:System.Activities.Argument.EvaluationOrder%2A> auf einen Wert fest, der größer oder gleich null ist, um eine Auswertungsreihenfolge für dieses Argument anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bcd63-131">Set <xref:System.Activities.Argument.EvaluationOrder%2A> to a value greater or equal to zero to specify an evaluation order for this argument.</span></span> <span data-ttu-id="bcd63-132">Windows Workflow Foundation wertet Argumente mit einer angegebenen Auswertungs Reihenfolge in aufsteigender Reihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="bcd63-132">Windows Workflow Foundation evaluates arguments with a specified evaluation order in ascending order.</span></span> <span data-ttu-id="bcd63-133">Beachten Sie, dass Argumente mit einer nicht angegebenen Auswertungsreihenfolge vor Argumenten mit einer angegebenen Auswertungsreihenfolge ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-133">Note that arguments with an unspecified evaluation order are evaluated before those with a specified evaluation order.</span></span>  
  
 <span data-ttu-id="bcd63-134">Ein Aktivitätsautor kann einen stark typisierten Mechanismus zur Bereitstellung seiner Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-134">An activity author can use a strongly-typed mechanism for exposing its arguments.</span></span> <span data-ttu-id="bcd63-135">Dazu werden Eigenschaften von Typ <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> und <xref:System.Activities.InOutArgument%601> deklariert.</span><span class="sxs-lookup"><span data-stu-id="bcd63-135">This is accomplished by declaring properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="bcd63-136">Auf diese Weise kann ein Aktivitätsautor einen bestimmten Vertrag für die ein- und ausgehenden Daten einer Aktivität einrichten.</span><span class="sxs-lookup"><span data-stu-id="bcd63-136">This allows an activity author to establish a specific contract about the data going into and out of an activity.</span></span>  
  
### <a name="defining-the-arguments-on-an-activity"></a><span data-ttu-id="bcd63-137">Definieren der Argumente einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="bcd63-137">Defining the Arguments on an Activity</span></span>  
 <span data-ttu-id="bcd63-138">Argumente können für eine Aktivität definiert werden, indem Eigenschaften vom Typ <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> und <xref:System.Activities.InOutArgument%601> angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-138">Arguments can be defined on an activity by specifying properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="bcd63-139">Im folgenden Code wird gezeigt, wie die Argumente für eine `Prompt`-Aktivität definiert werden, die eine Zeichenfolge akzeptiert und Benutzer anzeigt und eine Zeichenfolge zurückgibt, die die Antwort des Benutzers enthält.</span><span class="sxs-lookup"><span data-stu-id="bcd63-139">The following code shows how to define the arguments for a `Prompt` activity that takes in a string to display to the user and returns a string that contains the user's response.</span></span>  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="bcd63-140">Aktivitäten, die einen einzelnen Wert zurückgeben, können von <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> oder <xref:System.Activities.CodeActivity%601> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-140">Activities that return a single value can derive from <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601>, or <xref:System.Activities.CodeActivity%601>.</span></span> <span data-ttu-id="bcd63-141">Diese Aktivitäten verfügen über ein klar definiertes <xref:System.Activities.OutArgument%601>-Objekt mit dem Namen <xref:System.Activities.Activity%601.Result%2A>, das den Rückgabewert der Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="bcd63-141">These activities have a well-defined <xref:System.Activities.OutArgument%601> named <xref:System.Activities.Activity%601.Result%2A> that contains the return value of the activity.</span></span>  
  
### <a name="using-variables-and-arguments-in-workflows"></a><span data-ttu-id="bcd63-142">Verwenden von Variablen und Argumenten in Workflows</span><span class="sxs-lookup"><span data-stu-id="bcd63-142">Using Variables and Arguments in Workflows</span></span>  
 <span data-ttu-id="bcd63-143">Im folgenden Beispiel wird gezeigt, wie Variablen und Argumente in einem Workflow verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-143">The following example shows how variables and arguments are used in a workflow.</span></span> <span data-ttu-id="bcd63-144">Der Workflow ist eine Sequenz, die drei Variablen deklariert: `var1`, `var2` und `var3`.</span><span class="sxs-lookup"><span data-stu-id="bcd63-144">The workflow is a sequence that declares three variables: `var1`, `var2`, and `var3`.</span></span> <span data-ttu-id="bcd63-145">Die erste Aktivität im Workflow ist eine `Assign`-Aktivität, die den Wert der `var1`-Variable dem Wert der `var2`-Variable zuweist.</span><span class="sxs-lookup"><span data-stu-id="bcd63-145">The first activity in the workflow is an `Assign` activity that assigns the value of variable `var1` to the variable `var2`.</span></span> <span data-ttu-id="bcd63-146">Darauf folgt eine `WriteLine`-Aktivität, die den Wert der `var2`-Variable druckt.</span><span class="sxs-lookup"><span data-stu-id="bcd63-146">This is followed by a `WriteLine` activity that prints the value of the `var2` variable.</span></span> <span data-ttu-id="bcd63-147">Als Nächstes kommt eine andere `Assign`-Aktivität, die dem Wert der `var2`-Variable den Wert der `var3`-Variable zuweist.</span><span class="sxs-lookup"><span data-stu-id="bcd63-147">Next is another `Assign` activity that assigns the value of variable `var2` to the variable `var3`.</span></span> <span data-ttu-id="bcd63-148">Schließlich folgt eine weitere `WriteLine`-Aktivität, die den Wert der `var3`-Variable druckt.</span><span class="sxs-lookup"><span data-stu-id="bcd63-148">Finally there is another `WriteLine` activity that prints the value of the `var3` variable.</span></span> <span data-ttu-id="bcd63-149">Die erste `Assign`-Aktivität verwendet `InArgument<string>` und `OutArgument<string>`-Objekte, die explizit die Bindungen für die Argumente der Aktivität darstellen.</span><span class="sxs-lookup"><span data-stu-id="bcd63-149">The first `Assign` activity uses `InArgument<string>` and `OutArgument<string>` objects that explicitly represent the bindings for the activity's arguments.</span></span> <span data-ttu-id="bcd63-150">`InArgument<string>` wird für <xref:System.Activities.Statements.Assign.Value%2A> verwendet, weil der Wert durch das <xref:System.Activities.Statements.Assign%601>-Argument in die <xref:System.Activities.Statements.Assign.Value%2A>-Aktivität übertragen wird, und `OutArgument<string>` wird für <xref:System.Activities.Statements.Assign.To%2A> verwendet, weil der Wert aus dem <xref:System.Activities.Statements.Assign.To%2A>-Argument in die Variable übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="bcd63-150">`InArgument<string>` is used for <xref:System.Activities.Statements.Assign.Value%2A> because the value is flowing into the <xref:System.Activities.Statements.Assign%601> activity through its <xref:System.Activities.Statements.Assign.Value%2A> argument, and `OutArgument<string>` is used for <xref:System.Activities.Statements.Assign.To%2A> because the value is flowing out of the <xref:System.Activities.Statements.Assign.To%2A> argument into the variable.</span></span> <span data-ttu-id="bcd63-151">Die zweite `Assign`-Aktivität erreicht dasselbe Ziel mit einer kompakteren Syntax, die ansonsten äquivalent ist und implizite Umwandlungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd63-151">The second `Assign` activity accomplishes the same thing with more compact but equivalent syntax that uses implicit casts.</span></span> <span data-ttu-id="bcd63-152">Die `WriteLine`-Aktivitäten verwenden ebenfalls die kompakte Syntax.</span><span class="sxs-lookup"><span data-stu-id="bcd63-152">The `WriteLine` activities also use the compact syntax.</span></span>  
  
```csharp  
// Declare three variables; the first one is given an initial value.  
Variable<string> var1 = new Variable<string>()  
{  
    Default = "one"  
};  
Variable<string> var2 = new Variable<string>();  
Variable<string> var3 = new Variable<string>();  
  
// Define the workflow  
Activity wf = new Sequence  
{  
    Variables = { var1, var2, var3 },  
    Activities =
    {  
        new Assign<string>()  
        {  
            Value = new InArgument<string>(var1),  
            To = new OutArgument<string>(var2)  
        },  
        new WriteLine() { Text = var2 },  
        new Assign<string>()  
        {  
            Value = var2,  
            To = var3  
        },  
        new WriteLine() { Text = var3 }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a><span data-ttu-id="bcd63-153">Verwenden von Variablen und Argumenten in codebasierten Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="bcd63-153">Using Variables and Arguments in Code-Based Activities</span></span>  
 <span data-ttu-id="bcd63-154">In den vorherigen Beispielen wird gezeigt, wie Argumente und Variablen in Workflows und deklarativen Aktivitäten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bcd63-154">The previous examples show how to use arguments and variables in workflows and declarative activities.</span></span> <span data-ttu-id="bcd63-155">Argumente und Variablen werden auch in codebasierten Aktivitäten verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd63-155">Arguments and variables are also used in code-based activities.</span></span> <span data-ttu-id="bcd63-156">Vom Konzept her ist die Verwendung sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="bcd63-156">Conceptually the usage is very similar.</span></span> <span data-ttu-id="bcd63-157">Variablen stellen Datenspeicher innerhalb der Aktivität dar, und Argumente bezeichnen den Datenstrom in oder aus der Aktivität. Sie werden vom Workflowautor an andere Variablen oder Argumente im Workflow gebunden, die Ursprung und Ziel des Datenstroms darstellen.</span><span class="sxs-lookup"><span data-stu-id="bcd63-157">Variables represent data storage within the activity, and arguments represent the flow of data into or out of the activity, and are bound by the workflow author to other variables or arguments in the workflow that represent where the data flows to or from.</span></span> <span data-ttu-id="bcd63-158">Um den Wert einer Variable oder eines Arguments in einer Aktivität abzurufen oder festzulegen, muss ein Aktivitätskontext verwendet werden, der die aktuelle Ausführungsumgebung der Aktivität darstellt.</span><span class="sxs-lookup"><span data-stu-id="bcd63-158">To get or set the value of a variable or argument in an activity, an activity context must be used that represents the current execution environment of the activity.</span></span> <span data-ttu-id="bcd63-159">Er wird von der Workflowlaufzeit in die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode der Aktivität übergeben.</span><span class="sxs-lookup"><span data-stu-id="bcd63-159">This is passed into the <xref:System.Activities.CodeActivity%601.Execute%2A> method of the activity by the workflow runtime.</span></span> <span data-ttu-id="bcd63-160">In diesem Beispiel wird eine benutzerdefinierte `Add`-Aktivität definiert, die über zwei <xref:System.Activities.ArgumentDirection.In>-Argumente verfügt.</span><span class="sxs-lookup"><span data-stu-id="bcd63-160">In this example, a custom `Add` activity is defined that has two <xref:System.Activities.ArgumentDirection.In> arguments.</span></span> <span data-ttu-id="bcd63-161">Mit der <xref:System.Activities.Argument.Get%2A>-Methode wird auf den Wert der Argumente zugegriffen. Es wird der Kontext verwendet, der von der Workflowlaufzeit übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bcd63-161">To access the value of the arguments, the <xref:System.Activities.Argument.Get%2A> method is used and the context that was passed in by the workflow runtime is used.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="bcd63-162">Weitere Informationen zum Arbeiten mit Argumenten, Variablen und Ausdrücken im Code finden [Sie unter Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code](authoring-workflows-activities-and-expressions-using-imperative-code.md) und [erforderlichen Argumenten und Überladungs Gruppen](required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bcd63-162">For more information about working with arguments, variables, and expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md) and [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>
