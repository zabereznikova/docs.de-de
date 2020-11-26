---
title: C#-Ausdrücke
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: b0e5d7f2fbb1f7b84c6d8f0110bd111165f0ea52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239613"
---
# <a name="c-expressions"></a>C#-Ausdrücke

Ab .NET Framework 4,5 werden c#-Ausdrücke in Windows Workflow Foundation (WF) unterstützt. Neue c#-Workflow Projekte, die in Visual Studio 2012 erstellt wurden und auf .NET Framework 4,5 abzielen, verwenden c#-Ausdrücke, und Visual Basic Workflow Projekte verwenden Visual Basic-Ausdrücke. Vorhandene .NET Framework 4-Workflow Projekte, die Visual Basic-Ausdrücke verwenden, können [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] unabhängig von der Projektsprache zu migriert werden und werden unterstützt. Dieses Thema bietet eine Übersicht über C#-Ausdrücke in [!INCLUDE[wf1](../../../includes/wf1-md.md)].

## <a name="using-c-expressions-in-workflows"></a>Verwenden von C#-Ausdrücken in Workflows

- [Verwenden von C#-Ausdrücken im Workflow-Designer](csharp-expressions.md#WFDesigner)

  - [Abwärtskompatibilität](csharp-expressions.md#BackwardCompat)

- [Verwenden von C#-Ausdrücken in Codeworkflows](csharp-expressions.md#CodeWorkflows)

- [Verwenden von C#-Ausdrücken in XAML-Workflows](csharp-expressions.md#XamlWorkflows)

  - [Kompilierte XAML](csharp-expressions.md#CompiledXaml)

  - [Lose XAML](csharp-expressions.md#LooseXaml)

- [Verwenden von C#-Ausdrücken in XAMLX-Workflowdiensten](csharp-expressions.md#WFServices)

### <a name="using-c-expressions-in-the-workflow-designer"></a><a name="WFDesigner"></a> Verwenden von c#-Ausdrücken in der Workflow-Designer

Ab .NET Framework 4,5 werden c#-Ausdrücke in Windows Workflow Foundation (WF) unterstützt. C#-Workflow Projekte, die in Visual Studio 2012 erstellt wurden und auf .NET Framework 4,5 abzielen, verwenden c#-Ausdrücke, während Visual Basic Workflow Projekte Visual Basic Ausdrücke verwenden. Um den gewünschten c#-Ausdruck anzugeben, geben Sie ihn in das Feld mit der Bezeichnung **c#-Ausdruck eingeben ein**. Die Bezeichnung wird im Eigenschaftenfenster angezeigt, wenn die Aktivität im Designer ausgewählt wird, oder in der Aktivität im Workflow-Designer. Im folgenden Beispiel sind zwei `WriteLine`-Aktivitäten in `Sequence` innerhalb von `NoPersistScope` enthalten.

![Screenshot, der eine automatisch erstellte Sequenz Aktivität anzeigt.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> C#-Ausdrücke werden nur in Visual Studio unterstützt und werden im neu gehosteten Workflow-Designer nicht unterstützt. Weitere Informationen zu neuen WF45-Funktionen, die im neu gehosteten Designer unterstützt werden, finden Sie [unter Unterstützung für neue Workflow Foundation 4,5-Features in der neu gehosteten Workflow-Designer](wf-features-in-the-rehosted-workflow-designer.md).

#### <a name="backwards-compatibility"></a><a name="BackwardCompat"></a> Abwärtskompatibilität

Visual Basic Ausdrücke in vorhandenen .NET Framework vier c#-Workflow Projekten, die zu migriert wurden, [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] werden unterstützt. Wenn die Visual Basic Ausdrücke im Workflow-Designer angezeigt werden, wird der Text des vorhandenen Visual Basic Ausdrucks durch Wert ersetzt, der **in XAML festgelegt wurde**, es sei denn, der Visual Basic Ausdruck ist eine gültige c#-Syntax. Wenn der Visual Basic-Ausdruck gültiger C#-Syntax entspricht, wird der Ausdruck angezeigt. Um die Visual Basic-Ausdrücke auf C# zu aktualisieren, können Sie sie im Workflow-Designer bearbeiten und den entsprechenden C#-Ausdruck angeben. Es ist nicht erforderlich, die Visual Basic-Ausdrücke auf Visual C# zu aktualisieren. Nachdem die Ausdrücke jedoch im Workflow-Designer aktualisiert wurden, werden sie in C# konvertiert und möglicherweise nicht in Visual Basic wiederhergestellt.

### <a name="using-c-expressions-in-code-workflows"></a><a name="CodeWorkflows"></a> Verwenden von c#-Ausdrücken in Code Workflows

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
> Wenn die c#-Ausdrücke nicht kompiliert werden, wird eine ausgelöst, <xref:System.NotSupportedException> Wenn der Workflow mit einer Meldung ähnlich der folgenden aufgerufen wird: `Expression Activity type 'CSharpValue` 1 ' erfordert Kompilierung, um ausgeführt werden zu können.  Stellen Sie sicher, dass der Workflow kompiliert wurde. "

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

- Der Parameter zu `CompileExpressions` ist `DynamicActivity`.

- Typname und Namespace werden mit der `DynamicActivity.Name`-Eigenschaft abgerufen.

- Für `TextExpressionCompilerSettings.ForImplementation` ist `true` festgelegt.

- `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` wird anstelle von `CompiledExpressionInvoker.SetCompiledExpressionRoot` aufgerufen.

Weitere Informationen zum Arbeiten mit Ausdrücken im Code finden Sie unter [Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).

### <a name="using-c-expressions-in-xaml-workflows"></a><a name="XamlWorkflows"></a> Verwenden von c#-Ausdrücken in XAML-Workflows

C#-Ausdrücke werden in XAML-Workflows unterstützt. Kompilierte XAML-Workflows werden in einen Typ kompiliert und Loose XAML-Workflows werden von der Laufzeit geladen und beim Ausführen des Workflows in eine Aktivitätsstruktur kompiliert.

- [Kompilierte XAML](csharp-expressions.md#CompiledXaml)

- [Lose XAML](csharp-expressions.md#LooseXaml)

#### <a name="compiled-xaml"></a><a name="CompiledXaml"></a> Kompilierte XAML

C#-Ausdrücke werden in kompilierten XAML-Workflows unterstützt, die als Teil eines C#-Workflowprojekts, das [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] als Zielframework verwendet, in einen Typ kompiliert werden. Der kompilierte XAML-Code ist der Standardtyp der Workflow Erstellung in Visual Studio und c#-Workflow Projekten, die in Visual Studio erstellt wurden und als Ziel [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] c#-Ausdrücke verwenden.

#### <a name="loose-xaml"></a><a name="LooseXaml"></a> Lose XAML

C#-Ausdrücke werden in Loose XAML-Workflows unterstützt. Das Workflowhostprogramm, von dem der Loose XAML-Workflow geladen und aufgerufen wird, muss [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] als Zielframework verwenden, und <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> muss auf `true` festgelegt werden (der Standardwert ist `false`). Zum Festlegen von <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> auf `true` erstellen Sie eine <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings>-Instanz, deren <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>-Eigenschaft auf `true` festgelegt ist, und übergeben sie als Parameter an <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>. Wenn `CompileExpressions` nicht auf festgelegt ist `true` , <xref:System.NotSupportedException> wird eine mit einer Meldung ähnlich der folgenden ausgelöst: `Expression Activity type 'CSharpValue` 1 ' erfordert Kompilierung, um ausgeführt zu werden.  Stellen Sie sicher, dass der Workflow kompiliert wurde. "

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Weitere Informationen zum Arbeiten mit XAML-Workflows finden [Sie unter Serialisieren von Workflows und Aktivitäten in und aus XAML](serializing-workflows-and-activities-to-and-from-xaml.md).

### <a name="using-c-expressions-in-xamlx-workflow-services"></a><a name="WFServices"></a> Verwenden von c#-Ausdrücken in xamlx-Workflow Diensten

C#-Ausdrücke werden in XAMLX-Workflowdiensten unterstützt. Wenn ein Workflowdienst in IIS oder WAS gehostet ist, sind keine zusätzlichen Schritte erforderlich. Ist der XAML-Workflowdienst jedoch selbst gehostet, müssen die C#-Ausdrücke kompiliert werden. Zum Kompilieren der c#-Ausdrücke in einem selbstgeh osteten xamlx-Workflow Dienst laden Sie zuerst die xamlx-Datei in eine `WorkflowService` und übergeben dann die `Body` der- `WorkflowService` Methode an die `CompileExpressions` im vorherigen Abschnitt [Verwenden von c#-Ausdrücken in Code Workflows](csharp-expressions.md#CodeWorkflows) beschriebenen Methode. Im folgenden Beispiel wird ein XAMLX-Workflowdienst geladen, und die C#-Ausdrücke werden kompiliert. Anschließend wird der Workflowdienst geöffnet und wartet auf Anforderungen.

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

Wenn die C#-Ausdrücke nicht kompiliert werden, ist der `Open`-Vorgang zwar erfolgreich, der Workflow verursacht beim Aufruf jedoch einen Fehler. Die folgende `CompileExpressions` Methode ist identisch mit der-Methode aus der vorherigen [mithilfe von c#-Ausdrücken im Code Workflows](csharp-expressions.md#CodeWorkflows) -Abschnitt.

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
