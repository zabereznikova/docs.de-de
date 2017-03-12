---
title: "For...Next-Anweisung (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Step"
  - "vb.Next"
  - "vb.To"
  - "vb.for"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Endlosschleifen"
  - "Next-Schlüsselwort, For...Next-Anweisungen"
  - "For-Schlüsselwort [Visual Basic], For...Next-Anweisungen"
  - "Step-Schlüsselwort, For...Next-Anweisungen"
  - "Operatorüberladung, For...Next-Anweisung"
  - "To-Schlüsselwort, For...Next-Anweisungen"
  - "Endlosschleifen"
  - "Schleifen, endlos"
  - "Anweisungen, Wiederholen"
  - "Next-Anweisung, For...Next"
  - "For...Next-Anweisungen"
  - "Schleifenstrukturen, For...Next"
  - "Schleifen, unendlich"
  - "Exit-Anweisung, For...Next-Anweisungen"
  - "For-Anweisung"
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: 64
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 64
---
# For...Next-Anweisung (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wiederholt eine Reihe von Anweisungen so oft wie angegeben.  
  
## Syntax  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## Teile  
  
|Bestandteil|Beschreibung|  
|-----------------|------------------|  
|`counter`|In der `For`\-Anweisung erforderlich.  Numerische Variable.  Die Steuerelementvariable für die Schleife.  Weitere Informationen finden Sie unter [Gegenargument](#BKMK_Counter) weiter unten in diesem Thema.|  
|`datatype`|Dies ist optional.  Vom Datentyp `counter`.  Weitere Informationen finden Sie unter [Gegenargument](#BKMK_Counter) weiter unten in diesem Thema.|  
|`start`|Erforderlich.  Ein numerischer Ausdruck.  Der Anfangswert von `counter`.|  
|`end`|Erforderlich.  Ein numerischer Ausdruck.  Der Endwert von `counter`.|  
|`step`|Dies ist optional.  Ein numerischer Ausdruck.  Der Wert, um den `counter` mit jeder durchlaufenen Schleife erhöht wird.|  
|`statements`|Dies ist optional.  Eine oder mehrere Anweisungen zwischen `For` und `Next`, die mit der angegebenen Anzahl von Wiederholungen ausgeführt werden.|  
|`Continue For`|Dies ist optional.  Übergibt die Steuerung an die nächste Schleifeniteration.|  
|`Exit For`|Dies ist optional.  Überträgt die Steuerung aus der `For`\-Schleife.|  
|`Next`|Erforderlich.  Beendet die Definition der `For`\-Schleife.|  
  
> [!NOTE]
>  Das `To`\-Schlüsselwort wird in dieser Anweisung verwendet, um den Bereich für den Indikator anzugeben.  Sie können dieses Schlüsselwort in [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) und in den Arraydeklarationen auch verwenden.  Weitere Informationen zu Arraydeklarationen finden Sie unter [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## Einfache Beispiele  
 Sie verwenden eine Struktur `For`...`Next`, wenn Sie eine Gruppe von Anweisungen ein festgelegte Häufigkeit wiederholen möchten.  
  
 Im folgenden Beispiel wird die `index`\-Variablenanfänge mit einem Wert von 1 und bei jeder Iteration der Schleife erhöht und beendet nach dem Wert von `index` gezogene 5.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_1.vb)]  
  
 Im folgenden Beispiel wird die `number`\-Variablenbeginnung mit 2 und mit 0,25 für jede Iteration der Schleife reduziert und beendet nach dem Wert von `number` gezogene 0.  Das `Step`\-Argument von `-.25` reduziert den Wert von 0,25 für jede Iteration der Schleife.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  Arbeiten [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) oder [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) gut, wenn Sie nicht vorhersagen, wie viele Male, die Anweisungen in der Schleife auszuführen.  Wenn die Schleife jedoch eine festgelegte Anzahl von Wiederholungen durchlaufen soll, eignet sich eine`For`...`Next`\-Schleife besser.  Sie bestimmen die Anzahl der Iterationen zu Beginn der Schleife.  
  
## Schachteln von Schleifen  
 Sie können `For`\-Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.  Im folgenden Beispiel werden geschachtelte `For`...`Next`\-Strukturen mit unterschiedlichen Schrittwerten veranschaulicht.  Die äußere Schleife erstellt eine Zeichenfolge für jede Iteration der Schleife.  Die innere Schleife verringert eine Zählervariable der Schleife für jede Iteration der Schleife.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_3.vb)]  
  
 Wenn geschachtelte Schleifen, jede \- Schleife eine eindeutige `counter`\-Variable benötigen.  
  
 Sie können auch unterschiedliche Arten von Steuerungsstrukturen ineinander schachteln.  Weitere Informationen finden Sie unter [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Beenden für und Fortfahren für fort  
 Die `Exit For`\-Anweisung beendet sofort die Schleife `For`...`Next` und das Übergibt die Steuerung an die Anweisung, die der `Next`\-Anweisung folgt.  
  
 Die `Continue For`\-Anweisung überträgt die Steuerung direkt an die nächste Iteration der Schleife.  Weitere Informationen finden Sie unter [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel veranschaulicht die Verwendung der `Continue For`\-Anweisung und der `Exit For`\-Anweisung.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_4.vb)]  
  
 Sie können eine beliebige Anzahl von `Exit For`\-Anweisungen in einer `For`...`Next`\-Schleife einfügen.  Bei Verwendung in geschachtelten `For`...`Next`\-Schleifen beendet `Exit For` die innerste Schleife und überträgt die Steuerung auf die nächsthöhere Schachtelungsebene.  
  
 `Exit For` wird häufig verwendet, nachdem Sie eine Bedingung auswerten, \(beispielsweise in einer Struktur `If`...`Then`...`Else` \).  Sie können `Exit For` für die folgenden Bedingungen verwenden möchten:  
  
-   Das weitere Durchlaufen ist unnötig oder unmöglich.  Ein fehlerhafter Wert oder eine Abschlussanforderung könnten diese Bedingung.  
  
-   Eine Anweisung `Try`...`Catch`...`Finally` fängt eine Ausnahme ab.  Sie können am Ende des `Finally`\-Blocks `Exit For` verwenden.  
  
-   Sie haben eine Endlosschleife, die eine Schleife ist, die eine große oder sogar unbegrenzte Häufigkeit ausführen konnte.  Wenn Sie eine solche Bedingung feststellen, können Sie `Exit For` verwenden, um die Schleife zu verlassen.  Weitere Informationen finden Sie unter [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Technische Implementierung  
 Wenn eine `For`...`Next`\-Schleife beginnt, wertet Visual Basic `start`, `end` und `step` aus.  Visual Basic wertet diese Werte nur derzeit aus und weist dann `counter``start` zu.  Bevor der Anweisungsblock ausgeführt wird, vergleicht Visual Basic `counter` zu `end`.  Wenn `counter` bereits größer als ist, der `end`\-Wert \(oder das weniger, wenn `step` negativ ist\), die `For`\-Schleifenenden und die die Steuerung an die Anweisung, die der `Next`\-Anweisung folgt.  Andernfalls wird der Anweisungsblock ausgeführt.  
  
 Visual Basic erhöht bei jedem Auftreten der `Next`\-Anweisung `counter` um `step` und kehrt zur `For`\-Anweisung zurück.  `counter` wird erneut mit `end` verglichen, und wieder wird je nach Ergebnis der Block ausgeführt oder die Schleife verlassen.  Dieser Vorgang wird fortgesetzt, bis `end` von `counter` übergeben wird oder eine `Exit For`\-Anweisung auftritt.  
  
 Die Schleife wird nicht auf, bis `counter``end` übergeben hat.  Wenn `counter` gleich `end` ist, wird die Schleife fortgesetzt.  Der Vergleich, der bestimmt, ob der Block ausgeführt werden soll, lautet `counter` \<\= `end`, wenn `step` positiv ist, und `counter` \>\= `end`, wenn `step` negativ ist.  
  
 Wenn Sie den Wert von `counter` während innerhalb einer Schleife ändern, kann der Code schwieriger zu lesen und zu debuggen.  Ein Wert von `start` ändern, wirkt sich `end` oder `step` nicht die Iterationswerte, die bestimmt wurden, als die Schleife zuerst eingeführt wurde.  
  
 Wenn Sie Schleifen schachteln, signalisiert der Compiler einen Fehler, wenn er die `Next`\-Anweisung einer äußeren Schachtelungsebene vor der `Next`\-Anweisung einer inneren Ebene auftritt.  Der Compiler kann diesen Überlappungsfehler nur erkennen, wenn Sie in jeder `Next`\-Anweisung `counter` angeben.  
  
### Schrittargument  
 Der Wert von `step` kann positiv oder negativ sein.  Dieser Parameter bestimmt die Schleife, die entsprechend der folgenden Tabelle verarbeitet:  
  
|**Step\-Wert**|**Schleifenausführung, wenn**|  
|--------------------|-----------------------------------|  
|Positiv oder 0|`counter` \<\= `end`|  
|Negativ|`counter` \>\= `end`|  
  
 Der Standardwert von `step` ist 1 \(null\).  
  
###  <a name="BKMK_Counter"></a> Gegenargument  
 Die folgende Tabelle gibt an, ob `counter` eine neue lokale Variable definiert, die in der gesamten `For…Next`\-Schleife ausgewertet wird.  Diese Angabe hängt davon ab, ob `datatype` vorhanden ist und ob `counter` bereits definiert ist.  
  
|Ein vorhandenes `datatype` ?|Der wird `counter` bereits definiert?|Ergebnis \(ob `counter` eine neue lokale Variable definiert, die in der gesamten `For...Next`\-Schleife erstreckt\)|  
|----------------------------------|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|  
|Nein|Ja|Nein, da `counter` bereits definiert ist.  Wenn der Bereich von `counter` nicht zur Prozedur lokal ist, tritt eine Warnung zur Kompilierzeit auf.|  
|Nein|Nein|Ja.  Der Datentyp wird von `start`, von `end` und von `step` Ausdrücken abgeleitet.  Informationen zum Typrückschluss, finden Sie unter [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Ja|Ja|Ja, aber nur, wenn die vorhandene `counter`\-Variable außerhalb der Prozedur definiert ist.  Diese Variable bleibt separat.  Wenn der Bereich der vorhandenen `counter`\-Variable zur Prozedur lokal ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|Ja.|  
  
 Der Datentyp von `counter` bestimmt den Typ der Iteration, die einer der folgenden Typen sein muss:  
  
-   Ein `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single` oder `Double`.  
  
-   Eine Enumeration, die Sie mithilfe einer [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)deklarieren.  
  
-   Ein `Object`.  
  
-   Ein Typ `T`, der die folgenden Operatoren hat, wobei `B` ein Typ ist, der in einem `Boolean`\-Ausdruck verwendet werden kann.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Sie können die `counter`\-Variable in der Anweisung `Next` optional angeben.  Diese Syntax verbessert die Lesbarkeit des Programms, insbesondere wenn Sie `For`\-Schleifen geschachtelt haben.  Sie müssen die Variable angeben, die in der entsprechenden `For`\-Anweisung auftritt.  
  
 Die Ausdrücke `start`, `end` und `step` können jeden Datentyp ergeben, der zum Typ von `counter` erweitert werden kann.  Wenn Sie einen benutzerdefinierten Typ für `counter` verwenden, müssen Sie möglicherweise den `CType` Konvertierungsoperator definieren, um die Typen von `start`, von `end` oder von `step` in den Typ von `counter` zu konvertieren.  
  
## Beispiel  
 Das folgende Beispiel entfernt alle Elemente aus einer generischen Liste.  Anstatt [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) zeigt das Beispiel eine Anweisung `For`...`Next` an, die in absteigender Reihenfolge durchlaufen wird.  Im Beispiel wird diese Technik, da die `removeAt`\-Methode Elemente nach dem entfernten Element bewirkt, dass einen niedrigeren Indexwert verfügen.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_5.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird durch eine Enumeration von, die deklariert wird, indem [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) verwendet.  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_6.vb)]  
  
## Beispiel  
 Im folgenden Beispiel verwenden die Anweisungsparameter eine Klasse mit Operatorüberladungen für die Operatoren `+`, `-`, `>=` und `<=`.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_7.vb)]  
  
## Siehe auch  
 <xref:System.Collections.Generic.List%601>   
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)