---
title: Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code
description: Eine Workflow Foundation-Workflow Definition ist eine Struktur von konfigurierten Aktivitäts Objekten. Verwenden Sie Code, um Workflow Definitionen, Aktivitäten und Ausdrücke zu erstellen.
ms.date: 03/30/2017
ms.assetid: cefc9cfc-2882-4eb9-8c94-7a6da957f2b2
ms.openlocfilehash: d8b4cb8b85d3ea3759d58e15df823a72146772e8
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421552"
---
# <a name="authoring-workflows-activities-and-expressions-using-imperative-code"></a>Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code
Eine Workflowdefinition ist eine Struktur konfigurierter Aktivitätsobjekte. Diese Struktur mit Aktivitäten kann auf viele verschiedene Arten definiert werden, z. B. durch manuelle Bearbeitung des XAML-Codes oder mit dem Workflow-Designer, um XAML-Daten zu erzeugen. Die Verwendung von XAML ist jedoch keine Voraussetzung. Sie können Workflowdefinitionen auch programmgesteuert erstellen. Dieses Thema bietet eine Übersicht über das Erstellen von Workflowdefinitionen, Aktivitäten und Ausdrücken mithilfe von Code. Beispiele für die Arbeit mit XAML-Workflows mithilfe von Code finden Sie unter [Serialisieren von Workflows und Aktivitäten in und aus XAML](serializing-workflows-and-activities-to-and-from-xaml.md).  
  
## <a name="creating-workflow-definitions"></a>Erstellen von Workflowdefinitionen  
 Sie können eine Workflowdefinition erstellen, indem Sie eine Instanz eines Aktivitätstyps instanziieren und die Eigenschaften des Aktivitätsobjekts konfigurieren. Für Aktivitäten, die keine untergeordneten Aktivitäten enthalten, erreichen Sie dies mit einigen Codezeilen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#47](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#47)]  
  
> [!NOTE]
> In den Beispielen dieses Themas wird <xref:System.Activities.WorkflowInvoker> zum Ausführen der Beispielworkflows verwendet. Weitere Informationen zum Aufrufen von Workflows, zum Übergeben von Argumenten und zu den verschiedenen verfügbaren Hostingoptionen finden [Sie unter Verwenden von WorkflowInvoker und WorkflowApplication](using-workflowinvoker-and-workflowapplication.md).  
  
 In diesem Beispiel wird ein Workflow erstellt, der aus einer einzelnen <xref:System.Activities.Statements.WriteLine>-Aktivität besteht. Das <xref:System.Activities.Statements.WriteLine>-Argument der <xref:System.Activities.Statements.WriteLine.Text%2A>-Aktivität wird festgelegt, und der Workflow wird aufgerufen. Wenn eine Aktivität untergeordnete Aktivitäten enthält, ist die Konstruktionsmethode ähnlich. Im folgenden Beispiel wird eine <xref:System.Activities.Statements.Sequence>-Aktivität verwendet, die zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten enthält.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#48](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#48)]  
  
### <a name="using-object-initializers"></a>Verwenden von Objektinitialisierern  
 In den Beispielen in diesem Thema wird die Syntax zur Objektinitialisierung verwendet. Die Objektinitialisierungssyntax kann eine nützliche Möglichkeit zum Erstellen von Workflowdefinitionen per Code darstellen, da diese eine hierarchische Ansicht der Aktivitäten im Workflow bietet und die Beziehung zwischen den Aktivitäten anzeigt. Die Verwendung der Objektinitialisierungssyntax ist keine Anforderung der programmgesteuerten Erstellung von Workflows. Das folgende Beispiel entspricht von der Funktion her dem vorherigen Beispiel.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#49](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#49)]  
  
 Weitere Informationen zu Objektinitialisierern finden Sie unter Gewusst [wie: Initialisieren von Objekten ohne Aufruf eines Konstruktors (c#-Programmier Handbuch)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) und Gewusst [wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).  
  
### <a name="working-with-variables-literal-values-and-expressions"></a>Verwenden von Variablen, literalen Werten und Ausdrücken  
 Achten Sie beim Erstellen einer Workflowdefinition per Code darauf, welcher Code als Teil der Erstellung einer Workflowdefinition ausgeführt wird und welcher Code als Teil der Ausführung einer Instanz dieses Workflows ausgeführt wird. Der folgende Workflow soll z. B. eine zufällige Zahl generieren und auf die Konsole schreiben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#50](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#50)]  
  
 Wenn dieser Workflowdefinitionscode ausgeführt wird, erfolgt der Aufruf von `Random.Next`, und das Ergebnis wird in der Workflowdefinition als literaler Wert gespeichert. Es können viele Instanzen dieses Workflows aufgerufen werden, und für alle wird jeweils die gleiche Zahl angezeigt. Um die Zufallszahlengenerierung während der Workflowausführung durchführen zu lassen, müssen Sie einen Ausdruck verwenden, der bei jeder Ausführung des Workflows ausgewertet wird. Im folgenden Beispiel wird ein Visual Basic-Ausdruck mit <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> verwendet.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 Der Ausdruck im vorherigen Beispiel könnte auch mithilfe von <xref:Microsoft.CSharp.Activities.CSharpValue%601> und einem C#-Ausdruck implementiert werden.  
  
```csharp  
new Assign<int>  
{  
    To = n,  
    Value = new CSharpValue<int>("new Random().Next(1, 101)")  
}  
```  
  
 C#-Ausdrücke müssen kompiliert werden, bevor der Workflow, in dem sie enthalten sind, aufgerufen wird. Wenn die c#-Ausdrücke nicht kompiliert werden, wird eine ausgelöst, <xref:System.NotSupportedException> Wenn der Workflow mit einer Meldung ähnlich der folgenden aufgerufen wird: ``Expression Activity type 'CSharpValue`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.`` in den meisten Szenarien mit Workflows, die in Visual Studio erstellt werden, werden die c#-Ausdrücke automatisch kompiliert. in einigen Szenarien, wie z. b. Code Workflows, müssen die c#-Ausdrücke jedoch manuell kompiliert werden. Ein Beispiel für die Kompilierung von c#-Ausdrücken finden Sie im Abschnitt [Verwenden von c#-Ausdrücken in Code Workflows](csharp-expressions.md#CodeWorkflows) des Themas [c#-Ausdrücke](csharp-expressions.md) .  
  
 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> stellt einen Ausdruck in Visual Basic-Syntax dar, der als R-Wert in einem Ausdruck verwendet werden kann, und <xref:Microsoft.CSharp.Activities.CSharpValue%601> stellt einen Ausdruck in C#-Syntax dar, der als R-Wert in einem Ausdruck verwendet werden kann. Diese Ausdrücke werden jedes Mal ausgewertet, wenn die enthaltende Aktivität ausgeführt wird. Das Ergebnis des Ausdrucks wird der Workflowvariablen `n` zugewiesen, und diese Ergebnisse werden von der nächsten Aktivität im Workflow verwendet. Um zur Laufzeit auf den Wert der Workflowvariablen `n` zuzugreifen, ist der <xref:System.Activities.ActivityContext> erforderlich. Darauf kann mit dem folgenden Lambdaausdruck zugegriffen werden.  
  
> [!NOTE]
> Beachten Sie, dass beide Codebeispiele C# als Programmiersprache verwenden. In einem Fall wird jedoch <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> und im anderen <xref:Microsoft.CSharp.Activities.CSharpValue%601> verwendet. <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> und <xref:Microsoft.CSharp.Activities.CSharpValue%601> können sowohl in Visual Basic- als auch in C#-Projekten verwendet werden. Standardmäßig entsprechen die im Workflow-Designer erstellten Ausdrücke der Programmiersprache des Hostingprojekts. Wenn Workflows im Code erstellt werden, wählt der Workflowautor die verwendete Sprache nach eigenem Ermessen aus.  
  
 In diesen Beispielen wird das Ergebnis des Ausdrucks der Workflowvariablen `n` zugewiesen, und diese Ergebnisse werden von der nächsten Aktivität im Workflow verwendet. Um zur Laufzeit auf den Wert der Workflowvariablen `n` zuzugreifen, ist der <xref:System.Activities.ActivityContext> erforderlich. Darauf kann mit dem folgenden Lambdaausdruck zugegriffen werden.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#52](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#52)]  
  
 Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke (c#-Programmier Handbuch)](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) oder [Lambda-Ausdrücke (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Lambda-Ausdrücke können nicht in das XAML-Format serialisiert werden. Wenn versucht wird, einen Workflow mit Lambda-Ausdrücken zu serialisieren, wird <xref:System.Activities.Expressions.LambdaSerializationException> mit der folgenden Meldung ausgelöst: "Dieser Workflow enthält im Code spezifizierte Lambda-Ausdrücke. Diese Ausdrücke sind nicht XAML-serialisierbar. Um den Workflow XAML-serialisierbar zu machen, verwenden Sie entweder VisualBasicValue/VisualBasicReference oder ExpressionServices.Convert(lambda). Dadurch werden die Lambda-Ausdrücke in Ausdrucksaktivitäten konvertiert." Um diesen Ausdruck mit XAML kompatibel zu machen, verwenden Sie <xref:System.Activities.Expressions.ExpressionServices> und <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>. Dies wird im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#53](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#53)]  
  
 Es kann auch ein <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> verwendet werden. Beachten Sie, dass kein Lambda-Ausdruck erforderlich ist, wenn Sie einen Visual Basic-Ausdruck verwenden.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#54](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#54)]  
  
 Zur Laufzeit werden die Visual Basic-Ausdrücke in LINQ-Ausdrücke kompiliert. Beide vorherigen Beispiele sind in XAML serialisierbar, aber wenn die serialisierte XAML im Workflow-Designer angezeigt und bearbeitet werden soll, verwenden Sie <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> für die Ausdrücke. Serialisierte Workflows, die `ExpressionServices.Convert` verwenden, können zwar im Designer geöffnet werden, der Wert des Ausdrucks ist jedoch leer. Weitere Informationen zum Serialisieren von Workflows in XAML finden Sie unter [Serialisieren von Workflows und Aktivitäten in und aus XAML](serializing-workflows-and-activities-to-and-from-xaml.md).  
  
#### <a name="literal-expressions-and-reference-types"></a>Literale Ausdrücke und Verweistypen  
 Literale Ausdrücke werden in Workflows durch die <xref:System.Activities.Expressions.Literal%601>-Aktivität dargestellt. Die folgenden <xref:System.Activities.Statements.WriteLine>-Aktivitäten sind funktional äquivalent.  
  
```csharp  
new WriteLine  
{  
    Text = "Hello World."  
},  
new WriteLine  
{  
    Text = new Literal<string>("Hello World.")  
}  
```  
  
 Es ist nicht zulässig, einen literalen Ausdruck mit einem beliebigen Verweistyp außer <xref:System.String> zu initialisieren. Im folgenden Beispiel wird die <xref:System.Activities.Statements.Assign>-Eigenschaft einer <xref:System.Activities.Statements.Assign.Value%2A>-Aktivität mit einem literalen Ausdruck mit `List<string>` initialisiert.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new List<string>())  
},  
```  
  
 Bei der Überprüfung des Workflows, der die Aktivität enthält, wird der folgende Validierungsfehler zurückgegeben: „Literal unterstützt nur Werttypen und den unveränderlichen Typ „System.String“. Der System.Collections.Generic.List`1 [System.String]-Typ kann nicht als Literal verwendet werden." Beim Aufrufen des Workflows wird <xref:System.Activities.InvalidWorkflowException> ausgelöst, die den Text des Validierungsfehlers enthält. Dies ist ein Validierungsfehler, da durch das Erstellen eines literalen Ausdrucks mit einem Verweistyp keine neue Instanz des Verweistyps für die einzelnen Instanzen des Workflows erstellt wird. Um diesen Fehler zu beheben, ersetzen Sie den literalen Ausdruck durch einen Ausdruck, der eine neue Instanz des Verweistyps erstellt und zurückgibt.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new VisualBasicValue<List<string>>("New List(Of String)"))  
},  
```  
  
 Weitere Informationen zu Ausdrücken finden Sie unter [Ausdrücke](expressions.md).  
  
#### <a name="invoking-methods-on-objects-using-expressions-and-the-invokemethod-activity"></a>Aufrufen von Methoden für Objekte mithilfe von Ausdrücken und der InvokeMethod-Aktivität  
 Die <xref:System.Activities.Expressions.InvokeMethod%601>-Aktivität kann verwendet werden, um statische und Instanzenmethoden von Klassen in .NET Framework aufzurufen. In einem vorherigen Beispiel dieses Themas wird eine Zufallszahl mithilfe der <xref:System.Random>-Klasse generiert.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 Die <xref:System.Activities.Expressions.InvokeMethod%601>-Aktivität kann auch verwendet werden, um die <xref:System.Random.Next%2A>-Methode der <xref:System.Random>-Klasse aufzurufen.  
  
```csharp  
new InvokeMethod<int>  
{  
    TargetObject = new InArgument<Random>(new VisualBasicValue<Random>("New Random()")),  
    MethodName = "Next",  
    Parameters =
    {  
        new InArgument<int>(1),  
        new InArgument<int>(101)  
    },  
    Result = n  
}  
```  
  
 Da <xref:System.Random.Next%2A> keine statische Methode ist, wird eine Instanz der <xref:System.Random>-Klasse für die <xref:System.Activities.Expressions.InvokeMethod%601.TargetObject%2A>-Eigenschaft angegeben. In diesem Beispiel wird eine neue Instanz mit einem Visual Basic-Ausdruck erstellt. Diese hätte jedoch auch zuvor erstellt und in einer Workflowvariablen gespeichert werden können. In diesem Beispiel wäre es einfacher, die <xref:System.Activities.Statements.Assign%601>-Aktivität anstelle der <xref:System.Activities.Expressions.InvokeMethod%601>-Aktivität zu verwenden. Wenn der Methodenaufruf, der letztendlich entweder durch die <xref:System.Activities.Statements.Assign%601>-Aktivität oder durch <xref:System.Activities.Expressions.InvokeMethod%601>-Aktivität aufgerufen wird, eine lange Ausführungszeit aufweist, bietet <xref:System.Activities.Expressions.InvokeMethod%601> einen Vorteil, da sie über eine <xref:System.Activities.Expressions.InvokeMethod%601.RunAsynchronously%2A>-Eigenschaft verfügt. Wenn diese Eigenschaft auf `true` festgelegt ist, wird die aufgerufene Methode im Hinblick auf den Workflow asynchron ausgeführt. Wenn andere Aktivitäten parallel sind, werden sie nicht blockiert, während die Methode asynchron ausgeführt wird. Auch wenn die aufzurufende Methode über keinen Rückgabewert verfügt, stellt <xref:System.Activities.Expressions.InvokeMethod%601> die geeignete Möglichkeit zum Aufrufen der Methode dar.  
  
## <a name="arguments-and-dynamic-activities"></a>Argumente und dynamische Aktivitäten  
 Eine Workflowdefinition wird im Code erstellt, indem Aktivitäten in einer Aktivitätsstruktur zusammengestellt und alle Eigenschaften und Argumente konfiguriert werden. Vorhandene Argumente können gebunden werden, aber Aktivitäten können keine neuen Argumente hinzugefügt werden. Dies gilt auch für Workflowargumente, die an die Stammaktivität übergeben werden. In imperativem Code werden Workflowargumente als Eigenschaften eines neuen CLR-Typs angegeben, und in XAML werden sie mithilfe von `x:Class` und `x:Member` deklariert. Da kein neuer CLR-Typ erstellt wird, wenn eine Workflowdefinition als Struktur von Objekten im Arbeitsspeicher erstellt wird, können Argumente nicht hinzugefügt werden. Argumente können jedoch einer <xref:System.Activities.DynamicActivity> hinzugefügt werden. In diesem Beispiel wird eine <xref:System.Activities.DynamicActivity%601> erstellt, die zwei ganzzahlige Argumente verwendet, diese zusammenfügt und das Ergebnis zurückgibt. Für jedes Argument wird ein <xref:System.Activities.DynamicActivityProperty>-Element erstellt, und das Ergebnis des Vorgangs wird dem <xref:System.Activities.Activity%601.Result%2A>-Argument von <xref:System.Activities.DynamicActivity%601> zugewiesen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#55](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#55)]  
  
 Weitere Informationen zu dynamischen Aktivitäten finden Sie [unter Erstellen einer Aktivität zur Laufzeit](creating-an-activity-at-runtime-with-dynamicactivity.md).  
  
## <a name="compiled-activities"></a>Kompilierte Aktivitäten  
 Dynamische Aktivitäten bieten eine Möglichkeit, eine Aktivität mit Argumenten auf der Basis von Code zu definieren, Aktivitäten können jedoch auch im Code erstellt und in Typen kompiliert werden. Es können einfache Aktivitäten erstellt werden, die von <xref:System.Activities.CodeActivity> abgeleitet sind, und asynchrone Aktivitäten, die von <xref:System.Activities.AsyncCodeActivity> abgeleitet sind. Diese Aktivitäten können Argumente und Rückgabewerte aufweisen, und ihre Logik kann mithilfe von imperativem Code definiert werden. Beispiele zum Erstellen dieser Arten von Aktivitäten finden Sie unter [CodeActivity-Basisklasse](workflow-activity-authoring-using-the-codeactivity-class.md) und [Erstellen von asynchronen Aktivitäten](creating-asynchronous-activities-in-wf.md).  
  
 Aktivitäten, die von <xref:System.Activities.NativeActivity> abgeleitet werden, können ihre Logik mithilfe von imperativem Code definieren, und sie können auch untergeordnete Aktivitäten enthalten, die die Logik definieren. Sie haben außerdem Vollzugriff auf Funktionen der Laufzeit, z. B. das Erstellen von Lesezeichen. Beispiele für das Erstellen einer <xref:System.Activities.NativeActivity> -basierten Aktivität finden Sie unter [NativeActivity-Basisklasse](nativeactivity-base-class.md), Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md)und das Beispiel " [Custom Composite using Native Activity](./samples/custom-composite-using-native-activity.md) ".  
  
 Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet sind, definieren ihre Logik nur durch die Verwendung untergeordneter Aktivitäten. Diese Aktivitäten werden in der Regel mit dem Workflow-Designer erstellt, können aber auch mithilfe von Code definiert werden. Im folgenden Beispiel wird eine `Square`-Aktivität definiert, die von `Activity<int>` abgeleitet wird. Die `Square`-Aktivität verfügt über ein einzelnes <xref:System.Activities.InArgument%601> namens `Value` und definiert ihre Logik, indem eine <xref:System.Activities.Statements.Sequence>-Aktivität unter Verwendung der <xref:System.Activities.Activity.Implementation%2A>-Eigenschaft angegeben wird. Die <xref:System.Activities.Statements.Sequence>-Aktivität enthält eine <xref:System.Activities.Statements.WriteLine>-Aktivität und eine <xref:System.Activities.Statements.Assign%601>-Aktivität. Zusammen implementieren diese drei Aktivitäten die Logik der `Square`-Aktivität.  
  
```csharp  
class Square : Activity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Value { get; set; }  
  
    public Square()  
    {  
        this.Implementation = () => new Sequence  
        {  
            Activities =  
            {  
                new WriteLine  
                {  
                    Text = new InArgument<string>((env) => "Squaring the value: " + this.Value.Get(env))  
                },  
                new Assign<int>  
                {  
                    To = new OutArgument<int>((env) => this.Result.Get(env)),  
                    Value = new InArgument<int>((env) => this.Value.Get(env) * this.Value.Get(env))  
                }  
            }  
        };  
    }  
}  
```  
  
 Im folgenden Beispiel wird mit `Square` eine Workflowdefinition aufgerufen, die aus einer einzelnen <xref:System.Activities.WorkflowInvoker>-Aktivität besteht.  
  
```csharp  
Dictionary<string, object> inputs = new Dictionary<string, object> {{ "Value", 5}};  
int result = WorkflowInvoker.Invoke(new Square(), inputs);  
Console.WriteLine("Result: {0}", result);  
```  
  
 Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt:  
  
 **Quadrieren des Werts: 5**  
**Ergebnis: 25**
