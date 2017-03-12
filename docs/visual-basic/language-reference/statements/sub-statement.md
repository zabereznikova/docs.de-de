---
title: "Sub-Anweisung (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Sub"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Public-Schlüsselwort, Sub-Anweisungen"
  - "Erstellen von Prozeduren"
  - "Deklarieren von Vorgehensweisen, Sub-Anweisung"
  - "Argumente [Visual Basic], Sub-Prozeduren"
  - "AS-Schlüsselwort Sub-Anweisungen"
  - "Optional-Schlüsselwort, Sub-Anweisungen"
  - "Deklarationen der Prozeduren"
  - "Sub-Schlüsselwort"
  - "Handles-Schlüsselwort Sub-Anweisungen"
  - "Protected Friend-Schlüsselwort"
  - "ParamArray-Schlüsselwort Sub-Anweisungen"
  - "Implements-Schlüsselwort Sub-Anweisungen"
  - "Sub-Anweisung"
  - "Unterroutinen"
  - "ByRef-Schlüsselwort Sub-Anweisungen"
  - "Sub-Prozeduren Sub-Anweisung"
  - "Rekursive Prozeduren"
  - "Private-Schlüsselwort, Sub-Anweisungen"
  - "Friend-Schlüsselwort Sub-Anweisungen"
  - "Exit-Anweisung, Sub-Anweisungen"
  - "Sub-Verfahren"
  - "End-Schlüsselwort, Sub-Anweisungen"
  - "ByVal-Schlüsselwort Sub-Anweisungen"
  - "Visual Basic-Code Sub-Prozeduren"
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 52
---
# Sub-Anweisung (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

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
  
     Optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Partial`  
  
     Optional. Zeigt die Definition einer partiellen Methode. Finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Geschützte](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Siehe [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Überladungen](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Außerkraftsetzungen](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Überschreibbare](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Optional. Finden Sie unter [freigegebenen](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Optional. Finden Sie unter [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Prozedur. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des ein `Sub` Verfahren, um die `New` Schlüsselwort. Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Optional. Liste mit Typparametern für eine generische Prozedur. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/type-list.md).  
  
-   `parameterlist`  
  
     Optional. Die Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `Implements`  
  
     Optional. Gibt an, dass diese Prozedur eine oder mehrere implementiert `Sub` Prozeduren, die jeweils in einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Prozedur implementiert definiert. Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Sub`-Prozeduren.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |||  
    |-|-|  
    |Segment|Beschreibung|  
    |`interface`|Erforderlich. Name der Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist.|  
  
-   `Handles`  
  
     Optional. Gibt an, dass diese Prozedur eine oder mehrere bestimmte Ereignisse behandeln kann. Finden Sie unter [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
-   `eventlist`  
  
     Erforderlich, wenn `Handles` angegeben wird. Die Liste der Ereignisse, die diese Prozedur behandelt.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:  
  
     `eventvariable.event`  
  
    |||  
    |-|-|  
    |Segment|Beschreibung|  
    |`eventvariable`|Erforderlich. Objektvariable deklariert, die mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.|  
    |`event`|Erforderlich. Der Name des Ereignisses, die diese Prozedur behandelt.|  
  
-   `statements`  
  
     Optional. Der Block von Anweisungen in dieser Prozedur ausführen.  
  
-   `End Sub`  
  
     Beendet die Definition dieser Prozedur.  
  
## <a name="remarks"></a>Hinweise  
 Der gesamte ausführbare Code muss innerhalb einer Prozedur sein. Verwenden einer `Sub` Prozedur, wenn Sie einen Wert an den aufrufenden Code zurückgeben möchten. Verwenden einer `Function` Prozedur, wenn einen Wert zurückgegeben werden soll.  
  
## <a name="defining-a-sub-procedure"></a>Definieren eine Sub-Prozedur  
 Sie können eine `Sub` Prozedur nur auf Modulebene. Der Deklarationskontext für eine Sub-Prozedur, daher muss eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und eine Quelldatei, einen Namespace, eine Prozedur oder einen Block nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 `Sub` -Prozeduren weisen standardmäßig öffentlichen Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
 Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Sub` (in `definedname`) keine mit dem Namen dieser Prozedur übereinstimmen (in `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Rückgabe aus einer Subprozedur  
 Wenn ein `Sub` -Prozedur zum aufrufenden Code zurückkehrt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die diese aufgerufen.  
  
 Das folgende Beispiel zeigt eine Rückgabe aus einer `Sub` Prozedur.  
  
```vb#  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 Die `Exit Sub` und `Return` -Anweisung führen zur unmittelbare Beendigung einer `Sub` Prozedur. Eine beliebige Anzahl von `Exit Sub` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Sub` und `Return` Anweisungen.  
  
## <a name="calling-a-sub-procedure"></a>Aufrufen einer Subprozedur  
 Rufen Sie eine `Sub` -Prozedur durch den Namen der Prozedur in einer Anweisung verwenden und dann folgen diesem Namen und die Argumentliste in Klammern. Sie können die Klammern weglassen, nur, wenn Sie Argumente angeben. Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.  
  
 Ein `Sub` Verfahren und eine `Function` Prozedur über Parameter und eine Reihe von Anweisungen ausführen. Allerdings eine `Function` Prozedur gibt einen Wert und eine `Sub` Prozedur nicht. Daher können keiner `Sub` Prozedur in einem Ausdruck.  
  
 Können Sie die `Call` Schlüsselwort beim Aufruf einer `Sub` Prozedur, aber dieses Schlüsselwort wird nicht empfohlen, für die meisten Verwendungen. Weitere Informationen finden Sie unter [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md).  
  
 Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz zu erhöhen. Aus diesem Grund Wenn Argumentliste Ausdrücke enthält, die andere Prozeduren aufrufen darf keine Sie davon ausgehen, dass die Ausdrücke in einer bestimmten Reihenfolge aufgerufen werden.  
  
## <a name="async-sub-procedures"></a>Async Sub-Prozeduren  
 Mithilfe der Async-Funktion können Sie die asynchrone Funktionen aufrufen, ohne explizite Rückrufe verwenden oder den Code manuell über mehrere Funktionen oder Lambda-Ausdrücke teilen.  
  
 Markieren Sie eine Prozedur mit der [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Prozedur. Wenn das Steuerelement erreicht eine `Await` Ausdruck in der `Async` Prozedur die Steuerung an den Aufrufer zurückgegeben und Fortschritt in der Prozedur wird unterbrochen, bis die Aufgabe abgeschlossen ist. Wenn der Vorgang abgeschlossen ist, können in der Prozedur die Ausführung fortsetzen.  
  
> [!NOTE]
>  Ein `Async` Prozedur zurückgibt, an den Aufrufer, wenn entweder das erste await-Objekt, das noch nicht abgeschlossen ist, aufgetreten ist oder das Ende der `Async` Prozedur erreicht wird, welches Ereignis zuerst eintritt.  
  
 Sie können auch Markieren einer [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md) mit der `Async` Modifizierer. Eine `Async` Funktion kann einen Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>. Ein Beispiel weiter unten in diesem Thema wird eine `Async` -Funktion, die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.  
  
 `Async` `Sub` Prozeduren werden hauptsächlich für Ereignishandler, kann ein Wert zurückgegeben werden. Ein `Async``Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer einer `Async``Sub` Prozedur keine Ausnahmen auffangen, die `Sub` Prozedur ausgelöst.  
  
 Ein `Async` Prozedur kann nicht deklariert werden, keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.  
  
 Weitere Informationen zu `Async` Verfahren finden Sie [asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md), [Ablaufsteuerung in asynchronen Programmen](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md), und [Async Return Types](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Sub` Anweisung definieren den Namen, Parameter und Code, der den Text der form einer `Sub` Prozedur.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel `DelayAsync` ist ein einer `Async``Function` die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>. `DelayAsync` enthält eine `Return`-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund der Deklaration des `DelayAsync` muss einen Rückgabetyp haben `Task(Of Integer)`. Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl, wie in der folgenden Anweisung dargestellt: `Dim result As Integer = Await delayTask`.  
  
 Die `startButton_Click` Verfahren ist ein Beispiel für ein `Async Sub` Verfahren. Da `DoSomethingAsync` ist eine `Async` -Funktion, die die Aufgabe für den Aufruf von `DoSomethingAsync` gewartet werden muss, wie in der folgenden Anweisung dargestellt: `Await DoSomethingAsync()`. Die `startButton_Click``Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, weil sie verfügt über eine `Await` Ausdruck.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/visualbasic/asyncfunctionvb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Der](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)