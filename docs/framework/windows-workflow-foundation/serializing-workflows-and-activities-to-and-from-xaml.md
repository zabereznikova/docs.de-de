---
title: Serialisieren von Workflows und Aktivitäten in und aus XAML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a215be76002b9e8fca8ac4a9073885b3b30a97b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a>Serialisieren von Workflows und Aktivitäten in und aus XAML
Zusätzlich zur Kompilierung in Typen, die in Assemblys enthalten sind, können Workflowdefinitionen in XAML serialisiert werden. Diese serialisierten Definitionen können zur Bearbeitung oder Überprüfung erneut geladen werden, zur Kompilierung in ein Buildsystem übergeben werden oder geladen und aufgerufen werden. Dieses Thema bietet einen Überblick über das Serialisieren von Workflowdefinitionen und das Arbeiten mit XAML-Workflowdefinitionen.  
  
## <a name="working-with-xaml-workflow-definitions"></a>Arbeiten mit XAML-Workflowdefinitionen  
 Zum Erstellen einer Workflowdefinition zur Serialisierung wird die <xref:System.Activities.ActivityBuilder>-Klasse verwendet. Die Erstellung einer <xref:System.Activities.ActivityBuilder>-Klasse funktioniert ähnlich wie die Erstellung einer <xref:System.Activities.DynamicActivity>. Alle gewünschte Argumente werden angegeben, und die Aktivitäten, aus denen das Verhalten besteht, werden konfiguriert. Im folgenden Beispiel wird eine `Add`-Aktivität erstellt, die zwei Eingabeargumente verwendet, diese zusammenfügt und das Ergebnis zurückgibt. Da diese Aktivität ein Ergebnis zurückgibt, wird die generische <xref:System.Activities.ActivityBuilder%601>-Klasse verwendet.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 Die einzelnen <xref:System.Activities.DynamicActivityProperty>-Instanzen stellen die Eingabeargumente für den Workflow dar, und das <xref:System.Activities.ActivityBuilder.Implementation%2A>-Element enthält die Aktivitäten, aus denen die Logik des Workflows besteht. Beachten Sie, dass die Ausdrücke mit R-Wert in diesem Beispiel Visual Basic-Ausdrücke sind. Lambda-Ausdrücke sind nicht in XAML serialisierbar, es sei denn, <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> wird verwendet. Wenn die serialisierten Workflows im Workflow-Designer geöffnet oder bearbeitet werden sollen, sollten Visual Basic-Ausdrücke verwendet werden. Weitere Informationen finden Sie unter [Entwickeln von Workflows, Aktivitäten und Ausdrücken mithilfe von imperativem Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
 Um die von der <xref:System.Activities.ActivityBuilder>-Instanz dargestellte Workflowdefinition in XAML zu serialisieren, verwenden Sie <xref:System.Activities.XamlIntegration.ActivityXamlServices>, um <xref:System.Xaml.XamlWriter> zu erstellen, und anschließend <xref:System.Xaml.XamlServices>, um die Workflowdefinition mithilfe von <xref:System.Xaml.XamlWriter> zu serialisieren. <xref:System.Activities.XamlIntegration.ActivityXamlServices> verfügt über Methoden, um Zuordnungen zwischen <xref:System.Activities.ActivityBuilder>-Instanzen und XAML herzustellen, und um XAML-Workflows zu laden und eine aufrufbare <xref:System.Activities.DynamicActivity> zurückzugeben. Im folgenden Beispiel wird die <xref:System.Activities.ActivityBuilder>-Instanz aus dem vorherigen Beispiel in eine Zeichenfolge serialisiert und in einer Datei gespeichert.  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
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
  
 Beim Laden eines serialisierten Workflows die <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> Methode verwendet wird. Diese verwendet die serialisierte Workflowdefinition und gibt eine <xref:System.Activities.DynamicActivity> zurück, die die Workflowdefinition darstellt. Beachten Sie, dass die XAML-Daten erst deserialisiert werden, wenn <xref:System.Activities.Activity.CacheMetadata%2A> während des Validierungsprozesses für den Text der <xref:System.Activities.DynamicActivity> aufgerufen wird. Wenn die Validierung nicht explizit aufgerufen wird, erfolgt diese beim Aufrufen des Workflows. Wenn die XAML-Workflowdefinition ungültig ist, wird eine <xref:System.ArgumentException>-Ausnahme ausgelöst. Alle von <xref:System.Activities.Activity.CacheMetadata%2A> ausgelösten Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden. Im folgenden Beispiel wird der serialisierte Workflow aus dem vorherigen Beispiel geladen und von <xref:System.Activities.WorkflowInvoker> aufgerufen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 Wenn dieser Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.  
  
 **25 + 15**  
**40**    
> [!NOTE]
>  [!INCLUDE[crabout](../../../includes/crabout-md.md)] Aufrufen von Workflows mit Eingabe- und Argumenten finden Sie unter [Verwenden von WorkflowInvoker und WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) und <xref:System.Activities.WorkflowInvoker.Invoke%2A>.  
  
 Wenn der serialisierte Workflow C#-Ausdrücke enthält ein <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> -Instanz mit der <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> -Eigenschaftensatz auf `true` muss als Parameter übergeben werden <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, andernfalls ein <xref:System.NotSupportedException> mit eine ähnliche Meldung ausgelöst wird die nach: `Expression Activity type 'CSharpValue`1" erfordert Kompilierung, um auszuführen.  Stellen Sie sicher, dass der Workflow kompiliert wurde. "  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 Weitere Informationen finden Sie unter [C#-Ausdrücke](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).  
  
 Eine serialisierte Workflowdefinition kann auch geladen werden, in eine <xref:System.Activities.ActivityBuilder> Instanz mithilfe der <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> Methode. Nachdem ein serialisierter Workflow in eine <xref:System.Activities.ActivityBuilder>-Instanz geladen wurde, kann er überprüft und geändert werden. Dies ist besonders nützlich für Autoren benutzerdefinierter Workflows, da es eine Methode zum Speichern und zum erneuten Laden von Workflowdefinitionen während des Entwurfsprozesses bereitstellt. Im folgenden Beispiel wird die serialisierte Workflowdefinition aus dem vorherigen Beispiel geladen, und ihre Eigenschaften werden überprüft.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
