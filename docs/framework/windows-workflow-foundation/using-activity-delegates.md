---
title: Verwenden von Aktivitätsdelegaten
ms.date: 03/30/2017
ms.assetid: e33cf876-8979-440b-9b23-4a12d1139960
ms.openlocfilehash: cbcc8f8e498be4f79f8fed5af7cd3557d7c55981
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837570"
---
# <a name="using-activity-delegates"></a>Verwenden von Aktivitätsdelegaten
Aktivitätsdelegaten ermöglichen es Aktivitätsautoren, Rückrufe mit bestimmten Signaturen verfügbar zu machen, für die Benutzer der Aktivität aktivitätsbasierte Handler bereitstellen können. Es sind zwei Typen von Aktivitätsdelegaten verfügbar: <xref:System.Activities.ActivityAction%601> wird verwendet, um Aktivitätsdelegaten zu definieren, die keinen Rückgabewert haben, und <xref:System.Activities.ActivityFunc%601> wird verwendet, um Aktivitätsdelegaten zu definieren, die einen Rückgabewert aufweisen.

Aktivitätsdelegaten sind in Szenarien nützlich, in denen eine untergeordnete Aktivität auf die Verwendung einer bestimmten Signatur beschränkt werden muss. Eine <xref:System.Activities.Statements.While>-Aktivität kann z. B. einen beliebigen Typ von untergeordneter Aktivität ohne Einschränkungen enthalten. Der Text einer <xref:System.Activities.Statements.ForEach%601>-Aktivität ist jedoch ein <xref:System.Activities.ActivityAction%601>-Element, und die untergeordnete Aktivität, die letztlich von <xref:System.Activities.Statements.ForEach%601> ausgeführt wird, muss über ein <xref:System.Activities.InArgument%601>-Element verfügen, das den gleichen Typ wie die Member der Auflistung aufweist, die das <xref:System.Activities.Statements.ForEach%601>-Element auflistet.

## <a name="using-activityaction"></a>Verwenden von ActivityAction

Mehrere [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Aktivitäten verwenden Aktivitätsaktionen, z. B. die <xref:System.Activities.Statements.Catch>-Aktivität und die <xref:System.Activities.Statements.ForEach%601>-Aktivität. In jedem Fall stellt die Aktivitätsaktion einen Speicherort da, an dem der Workflowautor beim Verfassen eines Workflows mithilfe einer dieser Aktivitäten eine Aktivität angibt, um das gewünschte Verhalten bereitzustellen. Im folgenden Beispiel wird eine <xref:System.Activities.Statements.ForEach%601>-Aktivität verwendet, um Text im Konsolenfenster anzuzeigen. Der Text von <xref:System.Activities.Statements.ForEach%601> wird mit einer <xref:System.Activities.ActivityAction%601> angegeben, die dem Typ von <xref:System.Activities.Statements.ForEach%601>, einer Zeichenfolge, entspricht. Die im <xref:System.Activities.Statements.WriteLine> angegebene <xref:System.Activities.ActivityDelegate.Handler%2A>-Aktivität weist ein <xref:System.Activities.Statements.WriteLine.Text%2A>-Argument auf, das an die Zeichenfolgenwerte in der Auflistung gebunden ist, die die <xref:System.Activities.Statements.ForEach%601>-Aktivität durchläuft.

[!code-csharp[CFX_ActivityExample#6](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#6)]

Das actionArgument wird verwendet, um die einzelnen Elemente in der Auflistung in die WriteLine zu verschieben. Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.

```console
HelloWorld.
```

In den Beispielen in diesem Thema wird die Syntax zur Objektinitialisierung verwendet. Die Objektinitialisierungssyntax kann eine nützliche Möglichkeit zum Erstellen von Workflowdefinitionen per Code darstellen, da diese eine hierarchische Ansicht der Aktivitäten im Workflow bietet und die Beziehung zwischen den Aktivitäten anzeigt. Die Verwendung der Objektinitialisierungssyntax ist keine Anforderung der programmgesteuerten Erstellung von Workflows. Das folgende Beispiel entspricht von der Funktion her dem vorherigen Beispiel.

[!code-csharp[CFX_ActivityExample#7](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#7)]

Weitere Informationen zu Objektinitialisierern finden Sie unter Gewusst [wie: Initialisieren von Objekten ohne Aufruf eines Konstruktors (C# Programmier Handbuch)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) und Gewusst [wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).

Im folgenden Beispiel wird eine <xref:System.Activities.Statements.TryCatch>-Aktivität in einem Workflow verwendet. Eine <xref:System.ApplicationException> wird vom Workflow ausgelöst und wird von einer <xref:System.Activities.Statements.Catch%601>-Aktivität behandelt. Der Handler für die Aktivitäts Aktion der <xref:System.Activities.Statements.Catch%601> Aktivität ist eine <xref:System.Activities.Statements.WriteLine> Aktivität, und das Ausnahme Detail wird mit dem `ex`-<xref:System.Activities.DelegateInArgument%601>übertragen.

[!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]

Verwenden Sie beim Erstellen einer benutzerdefinierten Aktivität, die ein <xref:System.Activities.ActivityAction%601>-Element definiert, ein <xref:System.Activities.Statements.InvokeAction%601>-Element, um das Aufrufen dieses <xref:System.Activities.ActivityAction%601>-Elements zu modellieren. In diesem Beispiel wird eine benutzerdefinierte `WriteLineWithNotification`-Aktivität definiert. Diese Aktivität besteht aus einem <xref:System.Activities.Statements.Sequence>-Element, das eine <xref:System.Activities.Statements.WriteLine>-Aktivität gefolgt von einem <xref:System.Activities.Statements.InvokeAction%601>-Element enthält. Dieses Element ruft ein <xref:System.Activities.ActivityAction%601>-Element auf, das ein Zeichenfolgenargument verwendet.

[!code-csharp[CFX_ActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#1)]

Wenn mit der `WriteLineWithNotification`-Aktivität ein Workflow erstellt wird, gibt der Workflowautor die gewünschte benutzerdefinierte Logik in der <xref:System.Activities.ActivityDelegate.Handler%2A>-Eigenschaft der Aktivitätsaktion an. In diesem Beispiel wird ein Workflow mit der `WriteLineWithNotification`-Aktivität erstellt, und eine <xref:System.Activities.Statements.WriteLine>-Aktivität wird als <xref:System.Activities.ActivityDelegate.Handler%2A>-Eigenschaft verwendet.

[!code-csharp[CFX_ActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#2)]

Es gibt mehrere generische Versionen von <xref:System.Activities.Statements.InvokeAction%601> und <xref:System.Activities.ActivityAction%601> zum Übergeben von einem oder mehreren Argumenten.

## <a name="using-activityfunc"></a>Verwenden von ActivityFunc

<xref:System.Activities.ActivityAction%601> ist nützlich, wenn es keinen Ergebniswert der Aktivität gibt, und <xref:System.Activities.ActivityFunc%601> wird verwendet, wenn ein Ergebniswert zurückgegeben wird. Verwenden Sie beim Erstellen einer benutzerdefinierten Aktivität, die ein <xref:System.Activities.ActivityFunc%601>-Element definiert, ein <xref:System.Activities.Expressions.InvokeFunc%601>-Element, um das Aufrufen dieses <xref:System.Activities.ActivityFunc%601>-Elements zu modellieren. Im folgenden Beispiel wird eine `WriteFillerText` -Aktivität definiert. Um den Füllzeichentext anzugeben, wird ein <xref:System.Activities.Expressions.InvokeFunc%601>-Element angegeben, das ein ganzzahliges Argument verwendet und über ein Zeichenfolgenergebnis verfügt. Nachdem der Füllzeichentext abgerufen wurde, wird er mit einer <xref:System.Activities.Statements.WriteLine>-Aktivität auf der Konsole angezeigt.

[!code-csharp[CFX_ActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#3)]

Um den Text anzugeben, müssen Sie eine Aktivität verwenden, die ein `int`-Argument verwendet und über ein Zeichenfolgenergebnis verfügt. In diesem Beispiel wird eine `TextGenerator`-Aktivität veranschaulicht, die diese Anforderungen erfüllt.

[!code-csharp[CFX_ActivityExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#4)]

Um die `TextGenerator`-Aktivität mit der `WriteFillerText`-Aktivität zu verwenden, geben Sie diese als <xref:System.Activities.ActivityDelegate.Handler%2A>-Eigenschaft an.

[!code-csharp[CFX_ActivityExample#5](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#5)]
