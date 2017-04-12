---
title: Sub-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, Sub statements
- procedures, creating
- declaring procedures, Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword, Sub statements
- Optional keyword, Sub statements
- declarations, procedures
- Sub keyword
- Handles keyword, Sub statements
- Protected Friend keyword
- ParamArray keyword, Sub statements
- Implements keyword, Sub statements
- Sub statement
- subroutines
- ByRef keyword, Sub statements
- Sub procedures, Sub statement
- recursive procedures
- Private keyword, Sub statements
- Friend keyword, Sub statements
- Exit statement, Sub statements
- procedures, Sub
- End keyword, Sub statements
- ByVal keyword, Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0eb78f92f22502d9e8595051361b45d9bf53ed64
ms.lasthandoff: 03/13/2017

---
# <a name="sub-statement-visual-basic"></a>Sub-Anweisung (Visual Basic)
Deklariert den Namen, Parameter und Code, definieren ein `Sub` Verfahren.  
  
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
  
     Optional. Finden Sie unter [Attributliste](attribute-list.md).  
  
-   `Partial`  
  
     Optional. Zeigt die Definition einer partiellen Methode. Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Private](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Overloads](../modifiers/overloads.md)  
  
    -   [Overrides](../modifiers/overrides.md)  
  
    -   [Overridable](../modifiers/overridable.md)  
  
    -   [NotOverridable](../modifiers/notoverridable.md)  
  
    -   [MustOverride](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Optional. Finden Sie unter [freigegebenen](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Optional. Finden Sie unter [Schatten](../modifiers/shadows.md).  
  
-   `Async`  
  
     Optional. Finden Sie unter [Async](../modifiers/async.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Prozedur. Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des ein `Sub` Verfahren, um die `New` Schlüsselwort. Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Optional. Liste mit Typparametern für eine generische Prozedur. Finden Sie unter [Liste](type-list.md).  
  
-   `parameterlist`  
  
     Optional. Die Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt. Finden Sie unter [Parameterliste](parameter-list.md).  
  
-   `Implements`  
  
     Optional. Gibt an, dass diese Prozedur eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert definiert. Finden Sie unter [Anweisung implementiert](implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Sub`-Prozeduren.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`interface`|Erforderlich. Name der Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist.|  
  
-   `Handles`  
  
     Optional. Gibt an, dass diese Prozedur eine oder mehrere bestimmte Ereignisse behandeln kann. Finden Sie unter [behandelt](handles-clause.md).  
  
-   `eventlist`  
  
     Erforderlich, wenn `Handles` angegeben wird. Die Liste der Ereignisse, die diese Prozedur behandelt.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:  
  
     `eventvariable.event`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`eventvariable`|Erforderlich. Objektvariable deklariert, die mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.|  
    |`event`|Erforderlich. Der Name des Ereignisses, die diese Prozedur behandelt.|  
  
-   `statements`  
  
     Optional. Der Block von Anweisungen in dieser Prozedur ausführen.  
  
-   `End Sub`  
  
     Beendet die Definition dieser Prozedur.  
  
## <a name="remarks"></a>Hinweise  
 Der gesamte ausführbare Code muss innerhalb einer Prozedur sein. Verwenden einer `Sub` Prozedur, wenn Sie einen Wert an den aufrufenden Code zurückgeben möchten. Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.  
  
## <a name="defining-a-sub-procedure"></a>Definieren eine Sub-Prozedur  
 Sie können eine `Sub` Prozedur nur auf Modulebene. Der Deklarationskontext für eine Sub-Prozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und eine Quelldatei, einen Namespace, eine Prozedur oder einen Block nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](declaration-contexts-and-default-access-levels.md).  
  
 `Sub`-Prozeduren weisen standardmäßig öffentlichen Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
 Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Sub` (in `definedname`) keine mit dem Namen dieser Prozedur übereinstimmen (in `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Rückgabe aus einer Subprozedur  
 Wenn ein `Sub` -Prozedur zum aufrufenden Code zurückkehrt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die diese aufgerufen.  
  
 Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Prozedur.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 Die `Exit Sub` und `Return` -Anweisung führen zur unmittelbare Beendigung einer `Sub` Prozedur. Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Sub` und `Return` Anweisungen.  
  
## <a name="calling-a-sub-procedure"></a>Aufrufen einer Subprozedur  
 Rufen Sie eine `Sub` -Prozedur durch den Namen der Prozedur in einer Anweisung verwenden und dann folgen diesem Namen und die Argumentliste in Klammern. Sie können die Klammern weglassen, nur, wenn Sie Argumente angeben. Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.  
  
 Ein `Sub` Prozedur und einer `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen. Allerdings eine `Function` Prozedur gibt einen Wert und eine `Sub` Prozedur nicht. Daher können keiner `Sub` Prozedur in einem Ausdruck.  
  
 Können Sie die `Call` Schlüsselwort beim Aufruf einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Verwendungen. Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).  
  
 Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz zu erhöhen. Aus diesem Grund Wenn Argumentliste Ausdrücke enthält, die andere Prozeduren aufrufen darf keine Sie davon ausgehen, dass die Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.  
  
## <a name="async-sub-procedures"></a>Async Sub-Prozeduren  
 Mithilfe der Async-Funktion können Sie die asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke teilen.  
  
 Markieren Sie eine Prozedur mit der [Async](../modifiers/async.md) -Modifizierer können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur. Wenn das Steuerelement erreicht eine `Await` Ausdruck in der `Async` Prozedur die Steuerung an den Aufrufer zurückgegeben und Fortschritt in der Prozedur wird unterbrochen, bis die Aufgabe abgeschlossen ist. Wenn der Vorgang abgeschlossen ist, können in der Prozedur die Ausführung fortsetzen.  
  
> [!NOTE]
>  Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste await-Objekt, das noch nicht abgeschlossen ist, aufgetreten ist oder das Ende der `Async` Prozedur erreicht wird, welches Ereignis zuerst eintritt.  
  
 Sie können auch Markieren einer [Function-Anweisung](function-statement.md) mit der `Async` Modifizierer. Ein `Async` Funktion kann keinen Rückgabetyp aufweisen oder <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Ein Beispiel weiter unten in diesem Thema wird ein `Async` -Funktion, die einen Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> hat  
  
 `Async``Sub` Prozeduren werden hauptsächlich für Ereignishandler, kann ein Wert zurückgegeben werden. Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async``Sub` Prozedur keine Ausnahmen auffangen, die `Sub` Prozedur ausgelöst.  
  
 Ein `Async` Prozedur kann nicht deklariert werden, keine [ByRef](../modifiers/byref.md) Parameter.  
  
 Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Sub` -Anweisung für die Definition der Name, Parameter und Code, der den Text der form einer `Sub` Prozedur.  
  
 [!code-vb[VbVbalrStatements&#58;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `DelayAsync` ist ein ein `Async``Function` , bei dem Rückgabetyp <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> `DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund der Deklaration des `DelayAsync` müssen einen Rückgabetyp von `Task(Of Integer)`. Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.  
  
 Die `startButton_Click` Verfahren ist ein Beispiel für ein `Async Sub` Verfahren. Da `DoSomethingAsync` ist ein `Async` -Funktion, die die Aufgabe für den Aufruf von `DoSomethingAsync` gewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`. Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, weil sie verfügt über eine `Await` Ausdruck.  
  
 [!code-vb[CsAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
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
