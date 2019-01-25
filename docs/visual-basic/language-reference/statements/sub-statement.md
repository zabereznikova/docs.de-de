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
ms.openlocfilehash: e7015474a0617b76ca537d2e84e8d7bfc72b6e12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737662"
---
# <a name="sub-statement-visual-basic"></a>Sub-Anweisung (Visual Basic)
Deklariert den Namen, Parameter und Code, definieren eine `Sub` Verfahren.  
  
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
  
     Dies ist optional. Finden Sie unter [Liste](attribute-list.md).  
  
-   `Partial`  
  
     Dies ist optional. Gibt die Definition einer partiellen Methode. Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Private](../modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

    - [Private Protected](../../language-reference/modifiers/private-protected.md)
  
     Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
     Dies ist optional. Finden Sie unter [Shadows](../modifiers/shadows.md).  
  
-   `Async`  
  
     Dies ist optional. Finden Sie unter [Async](../modifiers/async.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Prozedur. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise die `New` Schlüsselwort. Weitere Informationen finden Sie unter [Object Lifetime: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Dies ist optional. Liste der Parameter vom Typ für eine generische Prozedur. Finden Sie unter [Liste](type-list.md).  
  
-   `parameterlist`  
  
     Dies ist optional. Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt. Finden Sie unter [Parameterliste](parameter-list.md).  
  
-   `Implements`  
  
     Dies ist optional. Gibt an, dass diese Prozedur, eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert. Finden Sie unter [Anweisung implementiert](implements-statement.md).  
  
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
  
     Dies ist optional. Gibt an, dass dieses Verfahren auf eine oder mehrere bestimmte Ereignisse verarbeiten kann. Finden Sie unter [behandelt](handles-clause.md).  
  
-   `eventlist`  
  
     Erforderlich, wenn `Handles` angegeben wird. Liste der Ereignisse, die diese Prozedur verarbeitet.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:  
  
     `eventvariable.event`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`eventvariable`|Erforderlich. Die Objektvariable deklariert mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.|  
    |`event`|Erforderlich. Der Name des Ereignisses, die diese Prozedur verarbeitet.|  
  
-   `statements`  
  
     Dies ist optional. Der Block von Anweisungen, die in dieser Prozedur ausgeführt.  
  
-   `End Sub`  
  
     Beendet die Definition dieses Verfahrens.  
  
## <a name="remarks"></a>Hinweise  
 Der gesamte ausführbarer Code muss innerhalb einer Prozedur sein. Verwenden einer `Sub` Prozedur, wenn Sie keinen Wert an den aufrufenden Code zurückgeben möchten. Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.  
  
## <a name="defining-a-sub-procedure"></a>Definieren eine Sub-Prozedur  
 Sie können definieren, eine `Sub` Prozedur nur auf Modulebene. Der Deklarationskontext für eine Sub-Prozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und eine Quelldatei, einem Namespace, eine Prozedur oder einen Block nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).  
  
 `Sub` Prozeduren standardmäßig öffentlichen Zugriff auf. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
 Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, die enthaltende Klasse oder Struktur benötigen eine `Implements` Anweisung sofort nach der `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Sub` (in `definedname`) verfügt nicht über mit dem Namen dieses Verfahrens übereinstimmen (im `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Zurückgeben aus eine Sub-Prozedur  
 Wenn eine `Sub` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die diese aufgerufen.  
  
 Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Verfahren.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 Die `Exit Sub` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung aus einem `Sub` Verfahren. Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Sub` und `Return` Anweisungen.  
  
## <a name="calling-a-sub-procedure"></a>Aufrufen einer Subprozedur  
 Rufen Sie eine `Sub` Verfahren verwenden den Namen der Prozedur in einer Anweisung, und klicken Sie dann nach diesem Namen mit der Liste der Argumente in Klammern. Sie können die Klammern weglassen, nur, wenn Sie Argumente angeben. Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.  
  
 Ein `Sub` Prozedur und ein `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen. Allerdings eine `Function` Prozedur gibt einen Wert und einen `Sub` Prozedur nicht. Aus diesem Grund können keine `Sub` Prozedur in einem Ausdruck.  
  
 Können Sie die `Call` Schlüsselwort beim Aufrufen einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Verwendungen. Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).  
  
 Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern. Aus diesem Grund Ihrer Typargumentliste Ausdrücke enthält, die anderen Prozeduren aufgerufen werden sollte nicht Sie davon ausgehen, dass diese Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.  
  
## <a name="async-sub-procedures"></a>Async Sub-Prozeduren  
 Mithilfe der Async-Funktion zu verwenden, können Sie die asynchrone Funktionen aufrufen, ohne explizite Rückrufe oder den Code manuell über mehrere Funktionen oder Lambdaausdrücke teilen.  
  
 Wenn Sie eine Prozedur mit kennzeichnen die [Async](../modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur. Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` Prozedur die Steuerung an den Aufrufer zurückgegeben und Ausführung der Prozedur wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe abgeschlossen ist, kann in der Prozedur die Ausführung fortgesetzt.  
  
> [!NOTE]
>  Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste erwartete Objekt, das noch nicht abgeschlossen ist, erreicht wird oder das Ende der `Async` Prozedur erreicht wird, welches Ereignis zuerst eintritt.  
  
 Sie können auch Markieren einer [Function-Anweisung](function-statement.md) mit der `Async` Modifizierer. Ein `Async` Funktion kann einen Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>. Ein Beispiel weiter unten in diesem Thema wird gezeigt, eine `Async` Funktion, die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.  
  
 `Async` `Sub` Prozeduren werden in erster Linie für Ereignishandler verwendet, in dem ein Wert kann nicht zurückgegeben werden. Ein `Async` `Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async` `Sub` Prozedur keine Ausnahmen auffangen, die die `Sub` Prozedur löst.  
  
 Ein `Async` Prozedur kann nicht deklariert keine [ByRef](../modifiers/byref.md) Parameter.  
  
 Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Sub` -Anweisung für die Definition der Name, Parameter und Code, der den Text der form einer `Sub` Verfahren.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `DelayAsync` ist ein `Async` `Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>. `DelayAsync` enthält eine `Return` -Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund der Deklaration der `DelayAsync` müssen einen Rückgabetyp von `Task(Of Integer)`. Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.  
  
 Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Verfahren. Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` gewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`. Die `startButton_Click` `Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da sie verfügt über eine `Await` Ausdruck.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Implements-Anweisung](implements-statement.md)
- [Function-Anweisung](function-statement.md)
- [Parameterliste](parameter-list.md)
- [Dim-Anweisung](dim-statement.md)
- [Call-Anweisung](call-statement.md)
- [Of](of-clause.md)
- [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
