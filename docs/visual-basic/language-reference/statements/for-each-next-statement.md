---
title: "For Each...Next-Anweisung (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ForEach"
  - "vb.ForEachNext"
  - "vb.Each"
  - "ForEachNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Endlosschleifen"
  - "Next-Anweisung, For Each...Next"
  - "Endlosschleifen"
  - "Schleifenstrukturen, For Each...Next"
  - "Schleifen, endlos"
  - "Each-Schlüsselwort"
  - "Anweisungen, Wiederholen"
  - "For Each-Anweisung"
  - "Auflistungen, Anweisungswiederholung"
  - "Schleifen, unendlich"
  - "For Each...Next-Anweisungen"
  - "For-Schlüsselwort [Visual Basic], For Each...Next-Anweisungen"
  - "Exit-Anweisung, For Each...Next-Anweisungen"
  - "Iteration"
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 56
---
# For Each...Next-Anweisung (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wiederholt eine Reihe von Anweisungen für jedes Element in einer Auflistung.  
  
## Syntax  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`element`|In der `For Each`\-Anweisung erforderlich.  In der `Next`\-Anweisung optional.  Variable.  Wird zum Durchlaufen der Elemente der Auflistung verwendet.|  
|`datatype`|Erforderlich, wenn `element` nicht bereits deklariert wird.  Vom Datentyp `element`.|  
|`group`|Erforderlich.  Eine Variable mit einem Typ, der ein Auflistung Typ oder ein \- Objekt ist.  Verweist auf die Auflistung, in der die `statements` wiederholt werden sollen.|  
|`statements`|Dies ist optional.  Eine oder mehrer Anweisungen zwischen `For Each` und `Next`, die für jedes Element in `group` ausgeführt werden.|  
|`Continue For`|Dies ist optional.  Überträgt die Steuerung an den Anfang der `For Each`\-Schleife.|  
|`Exit For`|Dies ist optional.  Überträgt die Steuerung aus der `For Each`\-Schleife.|  
|`Next`|Erforderlich.  Beendet die Definition der `For Each`\-Schleife.|  
  
## Einfaches Beispiel  
 Verwenden Sie eine `For Each`...`Next`\-Schleife, wenn für jedes Element einer Auflistung oder eines Arrays ein Satz von Anweisungen wiederholt werden soll.  
  
> [!TIP]
>  Eine [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) eignet sich gut, wenn jede Iteration einer Schleife einer Steuerelementvariablen zugeordnet und der Anfangs\- und Endwert der Variablen bestimmt werden kann.  Wenn Sie jedoch eine Auflistung arbeiten, ist das Konzept der ersten und der endgültigen Werte nicht sinnvoll, und Sie nicht unbedingt wissen, wie viele Elemente die Auflistung verfügt.  In dieser Art des Falls, ist eine \- Schleife `For Each`...`Next` häufig die bessere Wahl.  
  
 Im folgenden Beispiel wird die \- Anweisung `For Each`...`Next` durch alle Elemente einer Listenauflistung durch.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_1.vb)]  
  
 Weitere Beispiele finden Sie unter [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md) und unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Geschachtelte \- Schleifen  
 Sie können `For Each`\-Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.  
  
 Das folgende Beispiel veranschaulicht geschachtelte `For Each`…`Next`\-Strukturen.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_2.vb)]  
  
 Wenn Sie Schleifen schachteln, muss jede \- Schleife eine eindeutige `element`\-Variablen vorhanden sind.  
  
 Sie können auch unterschiedliche Arten von Steuerungsstrukturen ineinander schachteln.  Weitere Informationen finden Sie unter [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Beenden für und Fortfahren für fort  
 Die [Beenden für](../../../visual-basic/language-reference/statements/exit-statement.md)\-Anweisungsursachenausführung, um die Schleife `For`...`Next` und des Übergangssteuerelements zur Anweisung zu beenden, die der `Next`\-Anweisung folgt.  
  
 Die `Continue For`\-Anweisung überträgt die Steuerung direkt an die nächste Iteration der Schleife.  Weitere Informationen finden Sie unter [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel veranschaulicht, wie die `Continue For`\-Anweisung und die `Exit For`\-Anweisung verwendet werden.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_3.vb)]  
  
 Sie können eine beliebige Anzahl von `Exit For`\-Anweisungen in einer `For Each`\-Schleife einfügen.  Bei Verwendung in geschachtelten `For Each`\-Schleifen beendet `Exit For` die innerste Schleife und überträgt die Steuerung auf die nächsthöhere Schachtelungsebene.  
  
 `Exit For` wird oft nach der Auswertung einer Bedingung verwendet, z. B. in einer `If`...`Then`...`Else`\-Struktur.  Sie können `Exit For` für die folgenden Bedingungen verwenden möchten:  
  
-   Das weitere Durchlaufen ist unnötig oder unmöglich.  Dies kann durch einen falschen Wert oder eine Beendigungsanforderung verursacht werden.  
  
-   Eine Ausnahme wird abgefangen in `Try`...`Catch`...`Finally`.  Sie können am Ende des `Finally`\-Blocks `Exit For` verwenden.  
  
-   Dort eine Endlos\-Schleife, die eine Schleife ist, die eine große oder sogar unendliche Anzahl von Wiederholungen ausgeführt werden kann.  Wenn Sie eine solche Bedingung feststellen, können Sie `Exit For` verwenden, um die Schleife zu verlassen.  Weitere Informationen finden Sie unter [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Iteratoren  
 Sie verwenden einen *Iterator,* um eine benutzerdefinierte Iteration über einer Auflistung auszuführen.  Ein Iterator kann eine Funktion oder ein `Get` Accessor sein.  Er verwendet `Yield` eine \- Anweisung, um jedes Element der Auflistung separat zurückzugeben.  
  
 Sie rufen den Iterator auf, indem Sie eine `For Each...Next`\-Anweisung verwenden.  Jede Iteration der Schleife `For Each` ruft den Iterator auf.  Wenn eine `Yield`\-Anweisung im Iterator erreicht ist, wird der Ausdruck in der `Yield`\-Anweisung zurückgegeben, und die aktuelle Position im Code wird beibehalten.  Die Ausführung von diesem Speicherort beim nächsten Mal neu gestartet, dass der Iterator aufgerufen wird.  
  
 Im folgenden Beispiel wird eine Iteratorfunktion.  Die Iteratorfunktion verfügt über eine `Yield`\-Anweisung, die innerhalb einer [Für... Next\-Schleife](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife ist.  In der `ListEvenNumbers`\-Methode erstellt jede Iteration des `For Each`\-Anweisungstexts einen Aufruf der Iteratorfunktion, die der folgenden Anweisung `Yield` übergeht.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_4.vb)]  
  
 Weitere Informationen finden Sie unter [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md), [Yield\-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md) und [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## Technische Implementierung  
 Wenn eine \- Anweisung `For Each`...`Next` ausgeführt wird, wertet Visual Basic die Auflistung nur einmal, bevor die Schleifenanfänge aus.  Wenn das Anweisungsblock `element` oder `group` ändert, beeinflussen diese Änderungen nicht die Iteration der Schleife.  
  
 Nachdem `element` alle Elemente in der Auflistung zugewiesen wurden, wird die `For Each`\-Schleife beendet und die Steuerung an die Anweisung nach der `Next`\-Anweisung übergeben.  
  
 Wenn `element` nicht außerhalb der Schleife deklariert wurde, müssen Sie sie in der `For Each`\-Anweisung deklarieren.  Sie können den Typ `element` explizit durch eine `As`\-Anweisung deklarieren, oder Sie können auf den Typrückschluss zur Zuweisung des Typs zurückgreifen.  In beiden Fällen liegt der Gültigkeitsbereich von `element` innerhalb der Schleife.  Sie können `element` jedoch nicht sowohl außerhalb als auch innerhalb der Schleife deklarieren.  
  
 Sie können `element` in der `Next`\-Anweisung optional angeben.  Dies verbessert die Lesbarkeit des Programms, besonders, wenn Sie `For Each`\-Schleifen geschachtelt haben.  Sie müssen dieselbe Variable angeben, die in der entsprechenden `For Each`\-Anweisung vorhanden ist.  
  
 Vielleicht möchten Sie den Wert von `element` in einer Schleife nicht verändern müssen.  Dadurch kann machen es schwieriger sein, Code zu lesen und zu debuggen.  Das Ändern des Werts von `group` wirkt sich nicht auf die Auflistung oder die Elemente, die bestimmt wurden, als die Schleife zuerst eingeführt wurde.  
  
 Wenn geschachtelte Schleifen sind, wenn eine `Next`\-Anweisung einer äußeren Schachtelungsebene erreicht wird, bevor `Next` einer inneren Ebene, der Compiler einen Fehler signalisiert.  Der Compiler kann diesen Überlappungsfehler nur erkennen, wenn Sie in jeder `Next`\-Anweisung `element` angeben.  
  
 Wenn der Code auf dem Durchlaufen einer Auflistung in einer bestimmten Reihenfolge abhängig ist, ist eine \- Schleife `For Each`...`Next` nicht die beste Wahl, es sei denn, Sie wissen, dass die Eigenschaften des Enumeratorobjekts, das die Auflistung verfügbar macht.  Die Reihenfolge des Durchlaufs wird nicht von Visual Basic, aber durch die \- Methode des <xref:System.Collections.IEnumerator.MoveNext%2A> Enumeratorobjekts bestimmt.  Das bedeutet, dass Sie u. U. nicht vorhersagen können, welches Element der Auflistung als erstes in `element` zurückgegeben wird oder welches als nächstes Element nach einem bestimmten anderen Element zurückgegeben wird.  Zuverlässigere Ergebnisse erzielen Sie möglicherweise mit einer anderen Schleife, z. B. `For`...`Next` oder `Do`...`Loop`..  
  
 Für `element` muss ein Datentyp verwendet werden, in den der Datentyp der Elemente von `group` konvertiert werden kann.  
  
 Der Datentyp von `group` muss ein Verweistyp sein, der eine Auflistung oder ein Array verweist, das aufzählbar ist.  In der Regel bedeutet dies, dass `group` auf ein Objekt verweisen muss, mit dem die <xref:System.Collections.IEnumerable>\-Schnittstelle des `System.Collections`\-Namespaces oder der <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle des `System.Collections.Generic`\-Namespaces implementiert wird.  `System.Collections.IEnumerable` gibt die <xref:System.Collections.IEnumerable.GetEnumerator%2A>\-Methode an, die ein Enumeratorobjekt für die Sammlung zurückgibt.  Das Enumerationsobjekt implementiert die `System.Collections.IEnumerator`\-Schnittstelle des `System.Collections`\-Namespaces und macht die <xref:System.Collections.IEnumerator.Current%2A>\-Eigenschaft sowie die <xref:System.Collections.IEnumerator.Reset%2A>\-Methode und die <xref:System.Collections.IEnumerator.MoveNext%2A>\-Methode verfügbar.  Visual Basic verwendet diese, um die Auflistung zu traversieren.  
  
### Eingrenzende Konvertierungen  
 Wenn `Option Strict` auf `On` festgelegt ist, verursachen einschränkende Konvertierungen gewöhnlich Compilerfehler.  In einer `For Each`\-Anweisung werden jedoch Konvertierungen aus den Elementen in `group` in `element` ausgewertet und zur Laufzeit ausgeführt, und Compilerfehler, die durch einschränkende Konvertierungen verursacht werden, werden unterdrückt.  
  
 Im folgenden Beispiel kompiliert die Zuweisung von `m` als den Anfangswert für `n` nicht, wenn `Option Strict` aktiviert ist, da die Konvertierung von `Long` zu `Integer` einschränkende Konvertierung.  In der `For Each`\-Anweisung wird jedoch kein Compilerfehler gemeldet, obwohl die Zuordnung zu `number` dieselbe Konvertierung von `Long` in `Integer` erfordert.  In der `For Each`\-Anweisung, die eine große Anzahl enthält, tritt ein Laufzeitfehler auf, wenn <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> auf die große Anzahl angewendet wird.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_5.vb)]  
  
### IEnumerator\-Aufrufe  
 Zu Beginn der Ausführung einer `For Each`...`Next`\-Schleife überprüft Visual Basic, ob die `group` auf ein gültiges Auflistungsobjekt verweist.  Wenn dies nicht der Fall ist, wird eine Ausnahme ausgelöst.  Andernfalls werden die <xref:System.Collections.IEnumerator.MoveNext%2A>\-Methode und die <xref:System.Collections.IEnumerator.Current%2A>\-Eigenschaft des Operatorobjekts aufgerufen, um das erste Element zurückzugeben.  Wenn `MoveNext` angibt, dass kein nächstes Elemente vorhanden ist, die Auflistung also leer ist, wird die `For Each`\-Schleife beendet, und die Steuerung wird an die Anweisung nach der `Next`\-Anweisung übergeben.  Andernfalls legt Visual Basic `element` auf das erste Element fest und führt den Anweisungsblock aus.  
  
 Visual Basic setzt bei jedem Auftreten der `Next`\-Anweisung die Ausführung mit der `For Each`\-Anweisung fort.  Erneut werden `MoveNext` und `Current` aufgerufen, um das nächste Element zurückzugeben, und erneut wird je nach Ergebnis entweder der Block ausgeführt oder die Schleife beendet.  Dieser Prozess wird fortgesetzt, bis `MoveNext` angibt, dass kein nächstes Element vorhanden ist oder bis eine `Exit For`\-Anweisung auftritt.  
  
 **Ändern der Auflistung.** Das Enumeratorobjekt, das von <xref:System.Collections.IEnumerable.GetEnumerator%2A> normalerweise zurückgegeben wird, können Sie nicht die Auflistung ändern, indem es hinzugefügt wird, löscht, ersetzt, oder neu angeordnet werden alle Elemente.  Wenn Sie die Auflistung ändern, nachdem Sie eine `For Each`...`Next`\-Schleife gestartet haben, wird das Enumerationsobjekt ungültig, und der nächste Versuch des Zugriffs auf ein Element führt zu einer <xref:System.InvalidOperationException>\-Ausnahme.  
  
 ist jedoch Blockieren der Änderung nicht von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], sondern durch die Implementierung der \- Schnittstelle <xref:System.Collections.IEnumerable> bestimmt.  `IEnumerable` kann auf eine Weise implementiert werden, die Änderungen während der Iteration zulässt.  Für die Durchführung einer solchen dynamischen Änderung sollten Sie mit den Merkmalen der `IEnumerable`\-Implementierung für die verwendete Auflistung vertraut sein.  
  
 **Ändern von Auflistungselementen.** Die <xref:System.Collections.IEnumerator.Current%2A>\-Eigenschaft des Enumerationsobjekts ist [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) und gibt eine lokale Kopie jedes Auflistungselements zurück.  Das bedeutet, dass Sie die eigentlichen Elemente in einer `For Each`...`Next`\-Schleife nicht ändern können.  Jede Änderung erstellen Sie wirkt sich nur auf die lokale Kopie von `Current` und nicht zurück in die zugrunde liegende Auflistung wiedergegeben.  Wenn ein Element jedoch ein Verweistyp ist, können Sie die Member der Instanz ändern, auf die es zeigt.  Im folgenden Beispiel ändert den `BackColor`\-Member jedes `thisControl`\-Elements.  Sie können `thisControl` selbst jedoch nicht ändern.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Im vorherigen Beispiel kann der `BackColor`\-Member jedes `thisControl`\-Elements geändert werden, obwohl `thisControl` selbst nicht geändert werden kann.  
  
 **Traversieren von Arrays.** Da die <xref:System.Array>\-Klasse die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert, machen alle Arrays die <xref:System.Array.GetEnumerator%2A>\-Methode verfügbar.  Das bedeutet, dass Sie ein Array mit einer `For Each`...`Next`\-Schleife traversieren können.  Jedoch können Sie nur die Array\-Elemente lesen.  Sie können nicht geändert werden.  
  
## Beispiel  
 Im folgenden Beispiel werden alle Ordner im Verzeichnis C:\\ mithilfe der <xref:System.IO.DirectoryInfo>\-Klasse aufgelistet.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_6.vb)]  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht ein Verfahren zum Sortieren einer Auflistung.  Die Beispielssortierungsinstanzen von `Car`\-Klasse, die in <xref:System.Collections.Generic.List%601> gespeichert werden.  Die `Car`\-Klasse implementiert die \- Schnittstelle <xref:System.IComparable%601>, die erfordert, dass die <xref:System.IComparable%601.CompareTo%2A>\-Methode implementiert ist.  
  
 Jeder Aufruf der \- Methode <xref:System.IComparable%601.CompareTo%2A> vergleicht einzelnen, der zum Sortieren verwendet wird.  Vom Benutzer erstellter Code in der `CompareTo`\-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück.  Der zurückgegebene Wert ist kleiner als null, wenn das aktuelle Objekt kleiner als das andere \- Objekt ist, größer als null, wenn das aktuelle Objekt größer als das andere \- Objekt ist, und wenn sie gleich sind.  Dies ermöglicht es Ihnen, in dem Code definieren die Kriterien für größer als, weniger als und gleich.  
  
 In der `ListCars`\-Methode die `cars.Sort()`\-Anweisungssortierungen die Liste.  Dieser Aufruf der \- Methode <xref:System.Collections.Generic.List%601.Sort%2A><xref:System.Collections.Generic.List%601> wird die `CompareTo`\-Methode, für die `Car`\-Objekte in `List` automatisch aufgerufen werden.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_7.vb)]  
  
## Siehe auch  
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)