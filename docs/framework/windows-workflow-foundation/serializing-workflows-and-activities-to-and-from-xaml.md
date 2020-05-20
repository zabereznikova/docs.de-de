---
title: Serialisieren von Workflows und Aktivitäten in und aus XAML
description: Dieser Artikel stellt eine Übersicht über das Serialisieren von Workflow Definitionen und das Arbeiten mit XAML-Workflow Definitionen in Workflow Foundation dar.
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: 168dbc9a36cfa80c15fddc7481e986d1ce383adb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421344"
---
# <a name="serialize-workflows-and-activities-to-and-from-xaml"></a>Serialisieren von Workflows und Aktivitäten in und aus XAML

Zusätzlich zur Kompilierung in Typen, die in Assemblys enthalten sind, können Workflowdefinitionen in XAML serialisiert werden. Diese serialisierten Definitionen können zur Bearbeitung oder Überprüfung erneut geladen werden, zur Kompilierung in ein Buildsystem übergeben werden oder geladen und aufgerufen werden. Dieses Thema bietet einen Überblick über das Serialisieren von Workflowdefinitionen und das Arbeiten mit XAML-Workflowdefinitionen.

## <a name="work-with-xaml-workflow-definitions"></a>Arbeiten mit XAML-Workflow Definitionen

Zum Erstellen einer Workflowdefinition zur Serialisierung wird die <xref:System.Activities.ActivityBuilder>-Klasse verwendet. Die Erstellung einer <xref:System.Activities.ActivityBuilder>-Klasse funktioniert ähnlich wie die Erstellung einer <xref:System.Activities.DynamicActivity>. Alle gewünschte Argumente werden angegeben, und die Aktivitäten, aus denen das Verhalten besteht, werden konfiguriert. Im folgenden Beispiel wird eine `Add`-Aktivität erstellt, die zwei Eingabeargumente verwendet, diese zusammenfügt und das Ergebnis zurückgibt. Da diese Aktivität ein Ergebnis zurückgibt, wird die generische <xref:System.Activities.ActivityBuilder%601>-Klasse verwendet.

[!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]

Die einzelnen <xref:System.Activities.DynamicActivityProperty>-Instanzen stellen die Eingabeargumente für den Workflow dar, und das <xref:System.Activities.ActivityBuilder.Implementation%2A>-Element enthält die Aktivitäten, aus denen die Logik des Workflows besteht. Beachten Sie, dass die Ausdrücke mit R-Wert in diesem Beispiel Visual Basic-Ausdrücke sind. Lambda-Ausdrücke sind nicht in XAML serialisierbar, es sei denn, <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> wird verwendet. Wenn die serialisierten Workflows im Workflow-Designer geöffnet oder bearbeitet werden sollen, sollten Visual Basic Ausdrücke verwendet werden. Weitere Informationen finden Sie unter [Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).

Um die von der <xref:System.Activities.ActivityBuilder>-Instanz dargestellte Workflowdefinition in XAML zu serialisieren, verwenden Sie <xref:System.Activities.XamlIntegration.ActivityXamlServices>, um <xref:System.Xaml.XamlWriter> zu erstellen, und anschließend <xref:System.Xaml.XamlServices>, um die Workflowdefinition mithilfe von <xref:System.Xaml.XamlWriter> zu serialisieren. <xref:System.Activities.XamlIntegration.ActivityXamlServices>verfügt über Methoden zum Zuordnen <xref:System.Activities.ActivityBuilder> von-Instanzen zu und aus XAML und zum Laden von XAML-Workflows und zum Zurückgeben einer <xref:System.Activities.DynamicActivity> , die aufgerufen werden kann. Im folgenden Beispiel <xref:System.Activities.ActivityBuilder> wird die-Instanz aus dem vorherigen Beispiel in eine Zeichenfolge serialisiert und in einer Datei gespeichert.

```csharp
// Serialize the workflow to XAML and store it in a string.
StringBuilder sb = new StringBuilder();
StringWriter tw = new StringWriter(sb);
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
string serializedAB = sb.ToString();

// Display the XAML to the console.
Console.WriteLine(serializedAB);

// Serialize the workflow to XAML and save it to a file.
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw2, ab);
sw.Close();
```

Im folgenden Beispiel wird der serialisierte Workflow dargestellt.

```xaml
<Activity
  x:TypeArguments="x:Int32"
  x:Class="Add"
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <x:Members>
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />
  </x:Members>
  <Sequence>
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">
      <Assign.To>
        <OutArgument x:TypeArguments="x:Int32">
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />
          </OutArgument>
      </Assign.To>
    </Assign>
  </Sequence>
</Activity>
```

Um einen serialisierten Workflow zu laden, verwenden Sie die- <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> Methode. Diese verwendet die serialisierte Workflowdefinition und gibt eine <xref:System.Activities.DynamicActivity> zurück, die die Workflowdefinition darstellt. Beachten Sie, dass die XAML-Daten erst deserialisiert werden, wenn <xref:System.Activities.Activity.CacheMetadata%2A> während des Validierungsprozesses für den Text der <xref:System.Activities.DynamicActivity> aufgerufen wird. Wenn die Validierung nicht explizit aufgerufen wird, wird Sie ausgeführt, wenn der Workflow aufgerufen wird. Wenn die XAML-Workflowdefinition ungültig ist, wird eine <xref:System.ArgumentException>-Ausnahme ausgelöst. Alle von <xref:System.Activities.Activity.CacheMetadata%2A> ausgelösten Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden. Im folgenden Beispiel wird der serialisierte Workflow aus dem vorherigen Beispiel geladen und von <xref:System.Activities.WorkflowInvoker> aufgerufen.

[!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]

Wenn dieser Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.

**25 + 15**\
**40**

> [!NOTE]
> Weitere Informationen zum Aufrufen von Workflows mit Eingabe-und Ausgabe Argumenten finden [Sie unter Verwenden von WorkflowInvoker und WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) und <xref:System.Activities.WorkflowInvoker.Invoke%2A> .

Wenn der serialisierte Workflow c#-Ausdrücke enthält, muss eine- <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> Instanz, deren- <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> Eigenschaft auf festgelegt ist, `true` als Parameter an übergeben werden <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType> <xref:System.NotSupportedException> . andernfalls wird eine mit einer Meldung ähnlich der folgenden ausgegeben: der **Ausdrucks Aktivitätstyp ' csharpvalue ' 1 ' erfordert eine Kompilierung, um ausgeführt zu werden.  Stellen Sie sicher, dass der Workflow kompiliert wurde.**

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Weitere Informationen finden Sie unter [c#-Ausdrücke](csharp-expressions.md).

Eine serialisierte Workflow Definition kann auch mit der-Methode in eine-Instanz geladen werden <xref:System.Activities.ActivityBuilder> <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> . Nachdem ein serialisierter Workflow in eine- <xref:System.Activities.ActivityBuilder> Instanz geladen wurde, kann er überprüft und geändert werden. Dies ist besonders nützlich für Autoren benutzerdefinierter Workflows, da es eine Methode zum Speichern und zum erneuten Laden von Workflowdefinitionen während des Entwurfsprozesses bereitstellt. Im folgenden Beispiel wird die serialisierte Workflowdefinition aus dem vorherigen Beispiel geladen, und ihre Eigenschaften werden überprüft.

[!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
