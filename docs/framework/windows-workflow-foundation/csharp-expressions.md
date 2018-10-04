---
title: C#-Ausdrücke
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: 819f52c345983ca81794b8b1f33b6e2ba96b3922
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584161"
---
# <a name="c-expressions"></a>C#-Ausdrücke
Beginnend mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], c#-Ausdrücke werden in Windows Workflow Foundation (WF) unterstützt. In Visual Studio 2012, die auf erstellte neue C#-Workflowprojekte [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] verwenden C#-Ausdrücke und Visual Basic-Workflowprojekten Visual Basic-Ausdrücke verwenden. Vorhandene [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]-Workflowprojekte, die Visual Basic-Ausdrücke verwenden, können unabhängig von der Projektsprache zu [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] migieren und werden unterstützt. Dieses Thema bietet eine Übersicht über C#-Ausdrücke in [!INCLUDE[wf1](../../../includes/wf1-md.md)].

## <a name="using-c-expressions-in-workflows"></a>Verwenden von C#-Ausdrücken in Workflows

-   [Mithilfe von c#-Ausdrücke im Workflow-Designer](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#WFDesigner)

    -   [Abwärtskompatibilität Kompatibilität](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#BackwardCompat)

-   [Verwenden von C#-Ausdrücken in Codeworkflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows)

-   [Verwenden von c#-Ausdrücken in XAML-workflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#XamlWorkflows)

    -   [Kompiliertes Xaml](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CompiledXaml)

    -   [Loose Xaml](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#LooseXaml)

-   [Verwenden von C#-Ausdrücken in XAMLX-Workflowdiensten](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#WFServices)

###  <a name="WFDesigner"></a> Mithilfe von c#-Ausdrücke im Workflow-Designer
 Beginnend mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], c#-Ausdrücke werden in Windows Workflow Foundation (WF) unterstützt. In Visual Studio 2012, die auf erstellte c#-Workflowprojekte [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] c#-Ausdrücke verwenden, während Visual Basic-Workflowprojekten Visual Basic-Ausdrücke verwenden. Um den gewünschten C#-Ausdruck anzugeben, geben Sie ihn in das Feld mit der Bezeichnung **Geben Sie einen C#-Ausdruck**. Die Bezeichnung wird im Eigenschaftenfenster angezeigt, wenn die Aktivität im Designer ausgewählt wird, oder in der Aktivität im Workflow-Designer. Im folgenden Beispiel sind zwei `WriteLine`-Aktivitäten in `Sequence` innerhalb von `NoPersistScope` enthalten.

 ![Automatisch erstellte Sequenzaktivität](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")

> [!NOTE]
>  C#-Ausdrücke werden nur in Visual Studio unterstützt und werden im neu gehosteten Workflow-Designer nicht unterstützt. Weitere Informationen zu neuen WF45-Funktionen im neu gehosteten Designer unterstützt, finden Sie unter [Unterstützung für neue Workflow Foundation 4.5-Features im Workflow-Designer neu gehostet](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md).

####  <a name="BackwardCompat"></a> Abwärtskompatibilität Kompatibilität
 Visual Basic-Ausdrücke in vorhandenen [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] C#-Workflowprojekten, die zu [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] migriert wurden, werden unterstützt. Wenn die Visual Basic-Ausdrücke im Workflow-Designer angezeigt werden, durch der Text des vorhandenen Visual Basic-Ausdruck ersetzt **Wert wurde in XAML festgelegt**, es sei denn, die Visual Basic-Ausdruck gültiger C#-Syntax ist. Wenn der Visual Basic-Ausdruck gültiger C#-Syntax entspricht, wird der Ausdruck angezeigt. Um die Visual Basic-Ausdrücke auf C# zu aktualisieren, können Sie sie im Workflow-Designer bearbeiten und den entsprechenden C#-Ausdruck angeben. Es ist nicht erforderlich, die Visual Basic-Ausdrücke auf Visual C# zu aktualisieren. Nachdem die Ausdrücke jedoch im Workflow-Designer aktualisiert wurden, werden sie in C# konvertiert und möglicherweise nicht in Visual Basic wiederhergestellt.

###  <a name="CodeWorkflows"></a> Verwenden von C#-Ausdrücken in Codeworkflows
 C#-Ausdrücke werden in codebasierten [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflows unterstützt. Bevor der Workflow aufgerufen werden kann, müssen C#-Ausdrücke jedoch mit <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType> kompiliert werden. Workflowautoren können `CSharpValue` verwenden, um den R-Wert eines Ausdrucks darzustellen, und `CSharpReference`, um den L-Wert eines Ausdrucks darzustellen. Im folgenden Beispiel wird ein Workflow mit einer `Assign`-Aktivität und einer `WriteLine`-Aktivität erstellt, die in einer `Sequence`-Aktivität enthalten ist. `CSharpReference` wird für das `To`-Argument von `Assign` angegeben und stellt den L-Wert des Ausdrucks dar. Ein `CSharpValue` wird für das `Value`-Argument von `Assign` und für das `Text`-Argument von `WriteLine` angegeben und stellt den R-Wert für diese beiden Ausdrücke dar.

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

 Nachdem der Workflow erstellt wurde, werden die C#-Ausdrücke kompiliert, indem erst die `CompileExpressions`-Hilfsmethode und dann der Workflow aufgerufen wird. Im folgenden Beispiel wird die `CompileExpressions`-Methode verwendet:

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
>  Wenn die C#-Ausdrücke nicht kompiliert werden, eine <xref:System.NotSupportedException> wird ausgelöst, wenn der Workflow mit einer Meldung ähnlich der folgenden aufgerufen wird: `Expression Activity type 'CSharpValue`1" ist eine Kompilierung um auszuführen.  Stellen Sie sicher, dass der Workflow kompiliert wurde. "

 Wenn der auf benutzerdefiniertem Code basierende Workflow `DynamicActivity` verwendet, sind einige Änderungen an der `CompileExpressions`-Methode erforderlich, wie im folgenden Codebeispiel gezeigt.

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

 Es gibt einige Unterschiede in der `CompileExpressions`-Überladung, die die C#-Ausdrücke in eine dynamische Aktivität kompiliert.

-   Der Parameter zu `CompileExpressions` ist `DynamicActivity`.

-   Typname und Namespace werden mit der `DynamicActivity.Name`-Eigenschaft abgerufen.

-   Für `TextExpressionCompilerSettings.ForImplementation` ist `true` festgelegt.

-   `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` wird anstelle von `CompiledExpressionInvoker.SetCompiledExpressionRoot` aufgerufen.

 Weitere Informationen zum Arbeiten mit Ausdrücken im Code finden Sie unter [Entwickeln von Workflows, Aktivitäten und Ausdrücken mithilfe von imperativem Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).

###  <a name="XamlWorkflows"></a> Verwenden von c#-Ausdrücken in XAML-workflows
 C#-Ausdrücke werden in XAML-Workflows unterstützt. Kompilierte XAML-Workflows werden in einen Typ kompiliert und Loose XAML-Workflows werden von der Laufzeit geladen und beim Ausführen des Workflows in eine Aktivitätsstruktur kompiliert.

-   [Kompiliertes Xaml](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CompiledXaml)

-   [Loose Xaml](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#LooseXaml)

####  <a name="CompiledXaml"></a> Kompiliertes Xaml
 C#-Ausdrücke werden in kompilierten XAML-Workflows unterstützt, die als Teil eines C#-Workflowprojekts, das [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] als Zielframework verwendet, in einen Typ kompiliert werden. Kompilierte XAML ist der Standardtyp der workflowerstellung in Visual Studio und C#-Workflowprojekte erstellt, Visual Studio, die auf [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] c#-Ausdrücke verwenden.

####  <a name="LooseXaml"></a> Loose Xaml
 C#-Ausdrücke werden in Loose XAML-Workflows unterstützt. Das Workflowhostprogramm, von dem der Loose XAML-Workflow geladen und aufgerufen wird, muss [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] als Zielframework verwenden, und <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> muss auf `true` festgelegt werden (der Standardwert ist `false`). Zum Festlegen von <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> auf `true` erstellen Sie eine <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings>-Instanz, deren <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>-Eigenschaft auf `true` festgelegt ist, und übergeben sie als Parameter an <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>. Wenn `CompileExpressions` ist nicht festgelegt, um `true`, <xref:System.NotSupportedException> mit einer Meldung ähnlich der folgenden ausgelöst: `Expression Activity type 'CSharpValue`1" ist eine Kompilierung um auszuführen.  Stellen Sie sicher, dass der Workflow kompiliert wurde. "

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

 Weitere Informationen zum Arbeiten mit XAML-Workflows finden Sie unter [Serialisieren von Workflows und Aktivitäten in und aus XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).

###  <a name="WFServices"></a> Verwenden von C#-Ausdrücken in XAMLX-Workflowdiensten
 C#-Ausdrücke werden in XAMLX-Workflowdiensten unterstützt. Wenn ein Workflowdienst in IIS oder WAS gehostet ist, sind keine zusätzlichen Schritte erforderlich. Ist der XAML-Workflowdienst jedoch selbst gehostet, müssen die C#-Ausdrücke kompiliert werden. Um die C#-Ausdrücke in einem selbst gehosteten XAMLX-Workflowdienst zu kompilieren, laden Sie zuerst die XAMLX-Datei in eine `WorkflowService`, und übergeben Sie dann die `Body` von der `WorkflowService` auf die `CompileExpressions` Methode beschrieben, die im vorherigen [mit c# Ausdrücken in Codeworkflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) Abschnitt. Im folgenden Beispiel wird ein XAMLX-Workflowdienst geladen, und die C#-Ausdrücke werden kompiliert. Anschließend wird der Workflowdienst geöffnet und wartet auf Anforderungen.

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

 Wenn die C#-Ausdrücke nicht kompiliert werden, ist der `Open`-Vorgang zwar erfolgreich, der Workflow verursacht beim Aufruf jedoch einen Fehler. Die folgenden `CompileExpressions` Methode ist identisch mit der Methode aus dem vorherigen [mithilfe von C#-Ausdrücken in Codeworkflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) Abschnitt.

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
