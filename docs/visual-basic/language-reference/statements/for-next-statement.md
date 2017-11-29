---
title: For...Next-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 009c5a383cc3296f7f92888a344fa265547f1077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`counter`|Erforderlich, der `For` Anweisung. Numerische Variable. Die Steuerelementvariable für die Schleife. Weitere Informationen finden Sie unter [Leistungsindikator Argument](#BKMK_Counter) weiter unten in diesem Thema.|  
|`datatype`|Dies ist optional. Datentyp des `counter`. Weitere Informationen finden Sie unter [Leistungsindikator Argument](#BKMK_Counter) weiter unten in diesem Thema.|  
|`start`|Erforderlich. Numerischer Ausdruck. Der Anfangswert von `counter`.|  
|`end`|Erforderlich. Numerischer Ausdruck. Der endgültige Wert des `counter`.|  
|`step`|Dies ist optional. Numerischer Ausdruck. Der Betrag, `counter` wird jedes Mal beim Durchlaufen der Schleife erhöht.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen zwischen `For` und `Next` , auf denen die angegebene Anzahl von Malen ausgeführt.|  
|`Continue For`|Dies ist optional. Überträgt die Steuerung an die nächste Schleifeniteration.|  
|`Exit For`|Dies ist optional. Überträgt die Steuerung von der `For` Schleife.|  
|`Next`|Erforderlich. Beendet die Definition des der `For` Schleife.|  
  
> [!NOTE]
>  Die `To` -Schlüsselwort wird in dieser Anweisung verwendet, den Bereich für den Leistungsindikator an. Sie können auch dieses Schlüsselwort in der [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) und Arraydeklarationen. Weitere Informationen zu Arraydeklarationen, finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Einfache Beispiele  
 Sie verwenden eine `For`... `Next` Struktur, wenn Sie einer Reihe von Anweisungen eine festgelegte Anzahl von Male wiederholen möchten.  
  
 Im folgenden Beispiel die `index` Variable beginnt mit einem Wert von 1 und erhöht sich bei jeder Iteration der Schleife, beenden nach dem Wert des um `index` 5 erreicht.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 Im folgenden Beispiel die `number` Variablen beginnt bei 2 und endhost 0,25 bei jeder Iteration der Schleife, beenden, nachdem der Wert der `number` 0 erreicht. Die `Step` Argument `-.25` 0,25 bei jeder Iteration der Schleife den Wert verringert.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  Ein [während... While-Anweisung enden](../../../visual-basic/language-reference/statements/while-end-while-statement.md) oder [werden... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md) funktioniert gut, wenn Sie im Voraus wissen nicht wie oft die Anweisungen in der Schleife ausgeführt. Jedoch wenn Sie erwarten, dass der Schleife eine bestimmte Anzahl von Malen, Ausführen einer `For`... `Next` Schleife ist die bessere Wahl. Bestimmen Sie die Anzahl der Iterationen, bei der Eingabe der schleifenstatus.  
  
## <a name="nesting-loops"></a>Schachteln von Schleifen  
 Sie können schachteln `For` Schleifen, indem Sie eine Schleife in eine andere einfügen. Im folgende Beispiel wird veranschaulicht, geschachtelte `For`... `Next` Strukturen, die über unterschiedliche Werte verfügen. Die äußere Schleife erstellt eine Zeichenfolge für jede Iteration der Schleife. Die innere Schleife verringert eine Zählervariable für jede Iteration der Schleife an.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 Wenn Schleifen geschachtelt werden, muss jede Schleife einen eindeutigen haben `counter` Variable.  
  
 Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Für beenden und fortsetzen  
 Die `Exit For` Anweisung sofort unterbricht die `For`...`Next` Schleife und überträgt die Steuerung an die Anweisung mit der `Next` Anweisung.  
  
 Die `Continue For` Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel veranschaulicht die Verwendung der `Continue For` und `Exit For` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 Sie können eine beliebige Anzahl von einfügen `Exit For` Anweisungen in einem `For`...`Next` Schleife. Bei Verwendung in geschachtelten `For`...`Next` Schleifen, `Exit For` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene der Schachtelung.  
  
 `Exit For`wird häufig verwendet werden, nachdem Sie eine Bedingung ausgewertet (z. B. in einer `If`... `Then`... `Else` Struktur). Möglicherweise möchten Sie verwenden `Exit For` für die folgenden Bedingungen:  
  
-   Durchlaufen Sie den Vorgang fortsetzen, ist nicht erforderlich oder unmöglich. Diese Bedingung möglicherweise erstellen Sie einen falschen Wert oder eine Anforderung zum Beenden.  
  
-   Ein `Try`... `Catch`... `Finally` Anweisung wird eine Ausnahme abgefangen. Sie können `Exit For` am Ende der `Finally` Block.  
  
-   Sie haben eine Endlosschleife, also eine Schleife, die eine große oder sogar unendliche Anzahl von Malen ausgeführt werden konnte. Wenn Sie diese Situation erkennen, können Sie `Exit For` um die Schleife zu verlassen. Weitere Informationen finden Sie unter [werden... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Wenn eine `For`... `Next` Schleife gestartet wird, wertet Visual Basic `start`, `end`, und `step`. Visual Basic wertet diese Werte nur zu dieser Zeit ein, und weist `start` auf `counter`. Vor der Anweisung Block ausgeführt wird, stellt das Visual Basic `counter` auf `end`. Wenn `counter` bereits ist größer als die `end` Wert (oder kleiner, wenn `step` ist ein negativer Wert), wird die `For` -Schleife beendet und die Steuerung an die Anweisung mit übergeben der `Next` Anweisung. Andernfalls wird der Anweisungsblock ausgeführt.  
  
 Jedes Mal, wenn Visual Basic stößt der `Next` -Anweisung, es erhöht `counter` von `step` und gibt Sie zurück zu der `For` Anweisung. Erneut vergleicht `counter` auf `end`, und es werden abhängig vom Ergebnis die Schleife beendet oder der Block ausgeführt. Dieser Prozess wird fortgesetzt, bis `counter` übergibt `end` oder eine `Exit For` Anweisung gefunden wird.  
  
 Beenden der Schleife nicht bis `counter` vergangen `end`. Wenn `counter` gleich `end`, die Schleife fortgesetzt wird. Der Vergleich, der bestimmt, ob der Block ausgeführt wird `counter`  <=  `end` Wenn `step` positiv und `counter`  >=  `end` Wenn `step` ist ein negativer Wert.  
  
 Wenn Sie den Wert ändern `counter` innerhalb einer Schleife Code möglicherweise schwieriger zu lesen und zu debuggen. Ändern des Werts der `start`, `end`, oder `step` keinen Einfluss auf die Iterationswerte, die ermittelt wurden, wenn die Schleife zuerst eingegeben wurde.  
  
 Wenn Sie Schleifen schachteln, signalisiert der Compiler einem Fehler, wenn er erkennt die `Next` Anweisung einer äußeren Schachtelungsebene vor der `Next` Anweisung einer inneren Ebene. Jedoch der Compiler erkennen diese überlappende Fehler bei der Angabe `counter` in jedem `Next` Anweisung.  
  
### <a name="step-argument"></a>Schritt-Argument  
 Der Wert des `step` kann positiv oder negativ sein. Dieser Parameter bestimmt Verarbeitung entsprechend der folgenden Tabelle:  
  
|**Step-Wert**|**Schleife wird ausgeführt, wenn**|  
|--------------------|--------------------------|  
|Positiv oder 0 (null)|`counter` <= `end`|  
|Negativ|`counter` >= `end`|  
  
 Der Standardwert von `step` ist 1.  
  
###  <a name="BKMK_Counter"></a>Leistungsindikator-Argument  
 Die folgende Tabelle gibt an, ob `counter` definiert eine neue lokale Variable, die als Bereich ist für das gesamte `For…Next` Schleife. Diese Entscheidung hängt davon ab, ob `datatype` vorhanden ist und ob `counter` ist bereits definiert.  
  
|Ist `datatype` vorhanden?|Ist `counter` bereits definiert?|Ergebnis (ob `counter` definiert eine neue lokale Variable, die als Bereich ist für das gesamte `For...Next` Schleife)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|Nein|Ja|Nein, da `counter` ist bereits definiert. Wenn den Bereich der `counter` befindet sich nicht lokal auf die Prozedur eine Warnung während der Kompilierung auftritt.|  
|Nein|Nein|Ja. Der Datentyp abgeleitet wird, aus der `start`, `end`, und `step` Ausdrücke. Informationen über den Typrückschluss finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Ja|Ja|Ja, aber nur, wenn die vorhandene `counter` Variable außerhalb der Prozedur definiert wird. Diese Variable bleibt getrennt. Wenn der Bereich des vorhandenen `counter` Variable ist die Prozedur tritt ein Kompilierzeitfehler auf.|  
|Ja|Nein|Ja.|  
  
 Der Datentyp des `counter` bestimmt den Typ der Iteration, der einen der folgenden Typen sein muss:  
  
-   Ein `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, oder `Double`.  
  
-   Eine Enumeration, die Sie mithilfe von Deklarieren einer [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Eine `Object`.  
  
-   Ein Typ `T` , besitzt die folgenden Operatoren, in denen `B` ist ein Typ, der in verwendet werden kann ein `Boolean` Ausdruck.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Sie können optional angeben, die `counter` -Variable in der `Next` Anweisung. Diese Syntax verbessert die Lesbarkeit des Programms, insbesondere bei geschachtelten `For` Schleifen. Geben Sie die Variable, die angezeigt wird in der entsprechenden `For` Anweisung.  
  
 Die `start`, `end`, und `step` Auswerten von Ausdrücken können auf einen beliebigen Datentyp aufweisen, die in den Typ des erweitert `counter`. Wenn Sie einen benutzerdefinierten Typ für verwenden `counter`, möglicherweise müssen Sie definieren die `CType` Konvertierungsoperator konvertieren Sie die Typen von `start`, `end`, oder `step` in den Typ des `counter`.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel entfernt alle Elemente aus einer generischen Liste. Statt eine [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md), das Beispiel zeigt eine `For`... `Next` -Anweisung, die Elemente in absteigender Reihenfolge durchläuft. Im Beispiel wird diese Technik verwendet, da die `removeAt` Methode bewirkt, dass Elemente nach dem entfernten Element einen niedrigeren Indexwert haben.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel durchläuft eine Enumeration, die deklariert wird ein [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel verwenden Sie die Anweisungsparameter eine Klasse mit operatorüberladungen für die `+`, `-`, `>=`, und `<=` Operatoren.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic.List%601>  
 [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Sammlungen](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
