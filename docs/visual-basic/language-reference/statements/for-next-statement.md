---
title: For...Next-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 5d47d57b75005d5c13dbf8633981dfb2d57d3e90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638056"
---
# <a name="fornext-statement-visual-basic"></a>For...Next-Anweisung (Visual Basic)
Einer Gruppe von Anweisungen für eine angegebene Anzahl von Malen wiederholt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a>Teile  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`counter`|Erforderlich, der `For` Anweisung. Numerische Variable. Die Steuerelementvariable für die Schleife. Weitere Informationen finden Sie unter [Gegenargument](#BKMK_Counter) weiter unten in diesem Thema.|  
|`datatype`|Dies ist optional. Datentyp des `counter`. Weitere Informationen finden Sie unter [Gegenargument](#BKMK_Counter) weiter unten in diesem Thema.|  
|`start`|Erforderlich. Numerischer Ausdruck. Der Anfangswert von `counter`.|  
|`end`|Erforderlich. Numerischer Ausdruck. Der endgültige Wert der `counter`.|  
|`step`|Dies ist optional. Numerischer Ausdruck. Der Betrag, `counter` wird jedes Mal beim Durchlaufen der Schleife erhöht.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen zwischen `For` und `Next` , die die angegebene Anzahl von Malen ausgeführt.|  
|`Continue For`|Dies ist optional. Überträgt die Steuerung an die nächste Schleifeniteration.|  
|`Exit For`|Dies ist optional. Überträgt die Steuerung von der `For` Schleife.|  
|`Next`|Erforderlich. Beendet die Definition der `For` Schleife.|  
  
> [!NOTE]
>  Die `To` -Schlüsselwort wird in dieser Anweisung verwendet, den Bereich für den Leistungsindikator an. Sie können auch dieses Schlüsselwort in der [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) und Arraydeklarationen. Weitere Informationen zu Arraydeklarationen, finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Einfache Beispiele  
 Sie verwenden eine `For`... `Next` Struktur, wenn Sie einer Reihe von Anweisungen eine festgelegte Anzahl an, wie oft wiederholen möchten.  
  
 Im folgenden Beispiel die `index` Variable beginnt mit einem Wert von 1 und wird bei jeder Iteration der Schleife, beenden nach dem Wert des inkrementiert `index` 5 erreicht.  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 Im folgenden Beispiel die `number` Variablen beginnt bei 2 und wird von 0,25 in jeder Iteration der Schleife, beenden nach dem Wert des reduziert `number` 0 erreicht. Die `Step` Argument `-.25` verringert den Wert von 0,25 in jeder Iteration der Schleife.  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  Ein [während... While-Anweisung enden](../../../visual-basic/language-reference/statements/while-end-while-statement.md) oder [tun... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md) funktioniert gut, wenn Sie nicht im Voraus kennen wie viele Male die Anweisungen in der Schleife ausgeführt. Aber wenn Sie erwarten, führen Sie der Schleife eine bestimmte Anzahl von Malen, eine `For`... `Next` Schleife ist die bessere Wahl. Sie bestimmen die Anzahl der Iterationen, bei der Eingabe der schleifenstatus.  
  
## <a name="nesting-loops"></a>Schachteln von Schleifen  
 Sie können schachteln `For` Schleifen durch eine Schleife in einem anderen platzieren. Im folgende Beispiel wird veranschaulicht, geschachtelte `For`... `Next` Strukturen, die unterschiedliche Werte verfügen. Die äußere Schleife wird eine Zeichenfolge für jede Iteration der Schleife erstellt. Die innere Schleife verringert eine Schleifenzählervariable für jede Iteration der Schleife an.  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 Wenn Schleifen geschachtelt werden, foreach-Schleife müssen einen eindeutigen `counter` Variable.  
  
 Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Für beenden und fortsetzen für  
 Die `Exit For` Anweisung sofort beendet die `For`...`Next` Schleife und überträgt die Steuerung an die die folgende Anweisung die `Next` Anweisung.  
  
 Die `Continue For` -Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel veranschaulicht die Verwendung der `Continue For` und `Exit For` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 Sie können eine beliebige Anzahl von einfügen `Exit For` Anweisungen in einem `For`...`Next` Eine Schleife. Bei der Verwendung in geschachtelten `For`...`Next` Schleifen, `Exit For` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene Schachtelungsebenen.  
  
 `Exit For` wird häufig verwendet werden, nachdem Sie eine Bedingung ausgewertet (z. B. in einer `If`... `Then`... `Else` Struktur). Möglicherweise möchten Sie verwenden `Exit For` für die folgenden Bedingungen:  
  
- So durchlaufen Sie den Vorgang fortsetzen, ist nicht erforderlich oder unmöglich ist. Diese Bedingung möglicherweise erstellen Sie einen fehlerhaften Wert oder eine Anforderung zum Beenden.  
  
- Ein `Try`... `Catch`... `Finally` Anweisung wird eine Ausnahme abgefangen. Sie können `Exit For` am Ende der `Finally` Block.  
  
- Sie haben eine Endlosschleife, wird eine Schleife, die eine lange oder sogar unendliche Anzahl von Malen ausgeführt werden konnte. Wenn Sie eine solche Bedingung erkennen, können Sie `Exit For` die Schleife mit Escapezeichen versehen. Weitere Informationen finden Sie unter [tun... Until...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Wenn eine `For`... `Next` Schleife beginnt, Visual Basic wertet `start`, `end`, und `step`. Visual Basic wertet diese Werte nur an diese Zeit und weist dann `start` zu `counter`. Vor der Anweisung Block ausgeführt wird, vergleicht der Visual Basic `counter` zu `end`. Wenn `counter` bereits ist größer als die `end` Wert (oder kleiner, wenn `step` ist ein negativer Wert), wird die `For` Schleife und die Steuerung an die Anweisung die folgende übergeben die `Next` Anweisung. Andernfalls wird der Anweisungsblock ausgeführt.  
  
 Jedes Mal, wenn Visual Basic-stößt der `Next` -Anweisung, es erhöht `counter` von `step` und gibt an die `For` Anweisung. Erneut verglichen `counter` zu `end`, und wieder werden je nach Ergebnis die Schleife beendet oder der Block ausgeführt. Dieser Prozess wird fortgesetzt, bis `counter` übergibt `end` oder `Exit For` -Anweisung gefunden.  
  
 Beenden der Schleife nicht bis `counter` vergangen `end`. Wenn `counter` gleich `end`, die Schleife fortgesetzt wird. Der Vergleich, der bestimmt, ob der Block ausgeführt `counter`  <=  `end` Wenn `step` positiv und `counter`  >=  `end` Wenn `step` ist negativ.  
  
 Wenn Sie den Wert der ändern `counter` innerhalb einer Schleife, Ihren Code möglicherweise schwieriger zu lesen und zu debuggen. Ändern des Werts der `start`, `end`, oder `step` keine Auswirkungen auf die Iterationswerte, die bestimmt wurden, wenn die Schleife zuerst eingegeben wurde.  
  
 Wenn Sie Schleifen zu schachteln, signalisiert der Compiler einen Fehler an, wenn gefunden der `Next` Anweisung einer äußeren Schachtelungsebene vor der `Next` Anweisung einer inneren Ebene. Allerdings kann der Compiler erkennen diese überlappende Fehler aus, nur dann, wenn Sie angeben, `counter` in jeder `Next` Anweisung.  
  
### <a name="step-argument"></a>Schritt-Argument  
 Der Wert des `step` kann entweder positiv oder negativ sein. Dieser Parameter bestimmt die Verarbeitung gemäß der folgenden Tabelle:  
  
|**Step-Wert**|**Schleife wird ausgeführt, wenn**|  
|--------------------|--------------------------|  
|Positiv oder 0 (null)|`counter` <= `end`|  
|Negativ|`counter` >= `end`|  
  
 Der Standardwert von `step` ist 1.  
  
### <a name="BKMK_Counter"></a> Leistungsindikator-Argument  
 Die folgende Tabelle gibt an, ob `counter` definiert eine neue lokale Variable, die als Bereich ist für das gesamte `For…Next` Schleife. Diese Entscheidung hängt davon ab, ob `datatype` vorhanden ist und ob `counter` ist bereits definiert.  
  
|Ist `datatype` vorhanden?|Ist `counter` bereits definiert?|Ergebnis (ob `counter` definiert eine neue lokale Variable, die als Bereich ist für das gesamte `For...Next` Schleife)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|Nein|Ja|Nein, da `counter` ist bereits definiert. Wenn der Bereich der `counter` lokal für die Prozedur, eine Warnung während der Kompilierung tritt auf, ist nicht.|  
|Nein|Nein|Ja. Der Datentyp abgeleitet wird, aus der `start`, `end`, und `step` Ausdrücke. Weitere Informationen zu den Typrückschluss, finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Ja|Ja|Ja, aber nur, wenn die vorhandene `counter` Variable außerhalb der Prozedur definiert wird. Die Variable bleibt getrennt. Wenn der Bereich des vorhandenen `counter` Variable ist die Prozedur ein Fehler während der Kompilierung auftritt.|  
|Ja|Nein|Ja.|  
  
 Der Datentyp des `counter` bestimmt den Typ der Iteration, der einen der folgenden Typen sein muss:  
  
- Ein `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, oder `Double`.  
  
- Eine Enumeration, die Sie, mithilfe Deklarieren einer [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
- Eine `Object`.  
  
- Ein Typ `T` , besitzt die folgenden Operatoren, in denen `B` ist ein Typ, der verwendet werden kann eine `Boolean` Ausdruck.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Sie können optional angeben, die `counter` -Variable in der `Next` Anweisung. Diese Syntax verbessert die Lesbarkeit des Programms, besonders bei geschachtelten `For` Schleifen. Sie müssen die Variable, die angezeigt wird angeben, in der entsprechenden `For` Anweisung.  
  
 Die `start`, `end`, und `step` Auswerten von Ausdrücken können in einen Datentyp, der in den Typ der erweitert wird `counter`. Bei Verwendung ein benutzerdefinierten Typs für `counter`, möglicherweise müssen Sie definieren die `CType` Konvertierungsoperator zum Konvertieren der Typen von `start`, `end`, oder `step` in den Typ des `counter`.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel entfernt alle Elemente aus einer generischen Liste. Statt eine [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md), das Beispiel zeigt eine `For`... `Next` -Anweisung, die Elemente in absteigender Reihenfolge durchläuft. Im Beispiel wird diese Technik verwendet, da die `removeAt` Methode bewirkt, dass Elemente nach dem entfernten Element einen niedrigeren Indexwert haben.  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel durchläuft eine Enumeration, die deklariert wird ein [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel verwenden Sie die Parameter eine Klasse mit operatorüberladungen für die `+`, `-`, `>=`, und `<=` Operatoren.  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.List%601>
- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Sammlungen](../../programming-guide/concepts/collections.md)
