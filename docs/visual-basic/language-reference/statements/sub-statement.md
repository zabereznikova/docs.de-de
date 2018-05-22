---
title: Sub-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 08be38cdbec82914b567ab5b86eed71181efcf57
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="sub-statement-visual-basic"></a>Sub-Anweisung (Visual Basic)
Deklariert den Namen, Parameter und Code, definieren eine `Sub` Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Teile  
  
-   `attributelist`  
  
     Dies ist optional. Finden Sie unter [Attributliste](attribute-list.md).  
  
-   `Partial`  
  
     Dies ist optional. Zeigt die Definition einer partiellen Methode. Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Private](../modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

    - [Geschützt privat](../../language-reference/modifiers/private-protected.md)
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Overloads](../modifiers/overloads.md)  
  
    -   [Overrides](../modifiers/overrides.md)  
  
    -   [Overridable](../modifiers/overridable.md)  
  
    -   [NotOverridable](../modifiers/notoverridable.md)  
  
    -   [MustOverride](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Dies ist optional. Finden Sie unter [freigegebene](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Dies ist optional. Finden Sie unter [Schatten](../modifiers/shadows.md).  
  
-   `Async`  
  
     Dies ist optional. Finden Sie unter [Async](../modifiers/async.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Prozedur. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise der `New` Schlüsselwort. Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Dies ist optional. Liste mit Typparametern für eine generische Prozedur. Finden Sie unter [geben Liste](type-list.md).  
  
-   `parameterlist`  
  
     Dies ist optional. Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt. Finden Sie unter [Parameterliste](parameter-list.md).  
  
-   `Implements`  
  
     Dies ist optional. Gibt an, dass dieses Verfahren eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert. Finden Sie unter [Anweisung implementiert](implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Sub`-Prozeduren.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`interface`|Erforderlich. Name einer Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist.|  
  
-   `Handles`  
  
     Dies ist optional. Gibt an, dass dieses Verfahren eine oder mehrere bestimmte Ereignisse verarbeiten kann. Finden Sie unter [behandelt](handles-clause.md).  
  
-   `eventlist`  
  
     Erforderlich, wenn `Handles` angegeben wird. Die Liste der Ereignisse, die diese Prozedur behandelt.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:  
  
     `eventvariable.event`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`eventvariable`|Erforderlich. Mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst deklarierte Objektvariable.|  
    |`event`|Erforderlich. Der Name des Ereignisses, das dieses Verfahren behandelt.|  
  
-   `statements`  
  
     Dies ist optional. Der Block von Anweisungen in dieser Prozedur ausführen.  
  
-   `End Sub`  
  
     Beendet die Definition dieses Verfahrens fort.  
  
## <a name="remarks"></a>Hinweise  
 Alle ausführbaren Code muss innerhalb einer Prozedur sein. Verwenden einer `Sub` Prozedur, wenn Sie einen Wert an den aufrufenden Code zurückgeben möchten. Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.  
  
## <a name="defining-a-sub-procedure"></a>Definieren eine Subprozedur  
 Sie können definieren, eine `Sub` Prozedur nur auf Modulebene. Der Deklarationskontext für eine Subprozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und nicht mit einer Quelldatei, einen Namespace, eine Prozedur oder eines Blocks. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).  
  
 `Sub` Prozeduren standardmäßig öffentlichen Zugriff auf. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
 Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` -Anweisung, die unmittelbar folgt seine `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Sub` (in `definedname`) verfügt nicht über den Namen dieses Verfahrens entsprechend (in `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Rückgabe aus einer Subprozedur  
 Wenn eine `Sub` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die diese aufgerufen.  
  
 Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Prozedur.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 Die `Exit Sub` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung von einem `Sub` Prozedur. Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Sub` und `Return` Anweisungen.  
  
## <a name="calling-a-sub-procedure"></a>Aufrufen einer Subprozedur  
 Rufen Sie eine `Sub` -Prozedur durch den Namen der Prozedur in einer Anweisung verwenden und dann folgen diesem Namen und die Argumentliste in Klammern. Sie können die Klammern weglassen, nur, wenn Sie keine Argumente angeben. Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.  
  
 Ein `Sub` Prozedur und einen `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen. Allerdings eine `Function` Prozedur gibt einen Wert und eine `Sub` Prozedur nicht. Aus diesem Grund können keiner `Sub` Prozedur in einem Ausdruck.  
  
 Können Sie die `Call` Schlüsselwort beim Aufrufen einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Zwecke. Weitere Informationen finden Sie unter [-Anweisung Call](call-statement.md).  
  
 Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern. Aus diesem Grund Ihrer Typargumentliste Ausdrücke enthält, die anderen Prozeduren aufruft darf keine Sie davon ausgehen, dass diese Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.  
  
## <a name="async-sub-procedures"></a>Asynchrone Sub-Prozeduren  
 Mithilfe der Async-Funktion können Sie asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder manuell über mehrere Funktionen oder Lambda-Ausdrücke Teilen Codes zu müssen.  
  
 Wenn Sie eine Prozedur mit kennzeichnen die [Async](../modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur. Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` Prozedur, Steuerung an den Aufrufer zurückgegeben und die Ausführung der Prozedur wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe abgeschlossen ist, kann in der Prozedur die Ausführung fortgesetzt.  
  
> [!NOTE]
>  Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste erwartete Objekt, das noch nicht abgeschlossen wurde erkannt wird oder das Ende der `Async` Prozedur erreicht wird, welcher Vorgang zuerst ausgeführt.  
  
 Sie können auch markieren eine [Funktionsanweisung](function-statement.md) mit der `Async` Modifizierer. Ein `Async` Funktion kann den Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>. Ein Beispiel weiter unten in diesem Thema wird ein `Async` -Funktion, die einen Rückgabetyp <xref:System.Threading.Tasks.Task%601>.  
  
 `Async` `Sub` Prozeduren werden in erster Linie für Ereignishandler verwendet, in dem ein Wert kann nicht zurückgegeben werden. Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur keine Ausnahmen auffangen, die die `Sub` Prozedur ausgelöst.  
  
 Ein `Async` Prozedur kann nicht deklariert werden alle [ByRef](../modifiers/byref.md) Parameter.  
  
 Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Sub` Anweisung, um den Namen, Parameter und Code, der den Text der form definieren eine `Sub` Prozedur.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `DelayAsync` ist ein `Async``Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>. `DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund die Funktionsdeklaration von `DelayAsync` benötigen einen Rückgabetyp von `Task(Of Integer)`. Da der Rückgabetyp ist `Task(Of Integer)`, der Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.  
  
 Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Prozedur. Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` abgewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`. Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da es wurde ein `Await` Ausdruck.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](implements-statement.md)  
 [Function-Anweisung](function-statement.md)  
 [Parameterliste](parameter-list.md)  
 [Dim-Anweisung](dim-statement.md)  
 [Call-Anweisung](call-statement.md)  
 [Of](of-clause.md)  
 [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
