---
title: "Für jede... Next-Anweisung (Visual Basic) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
dev_langs:
- VB
helpviewer_keywords:
- infinite loops
- Next statement, For Each...Next
- endless loops
- loop structures, For Each...Next
- loops, endless
- Each keyword
- instructions, repeating
- For Each statement
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement, For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0173877fa4a57da76fd774d70ce63d2beda23ad
ms.lasthandoff: 03/13/2017

---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next-Anweisung (Visual Basic)
Wird eine Gruppe von Anweisungen für jedes Element in einer Auflistung wiederholt.  
  
## <a name="syntax"></a>Syntax  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Gemäß der `For Each` Anweisung. Optional in der `Next` Anweisung. Variable. Zum Durchlaufen der Elemente der Auflistung verwendet.|  
|`datatype`|Erforderlich, wenn `element` nicht ist bereits deklariert. Typ des `element`.|  
|`group`|Erforderlich. Eine Variable mit einem Typ, der eine Auflistung oder ein Objekt ist. Verweist auf die Auflistung, die die `statements` wiederholt werden sollen.|  
|`statements`|Optional. Eine oder mehrere Anweisungen zwischen `For Each` und `Next` , führen Sie für jedes Element im `group`.|  
|`Continue For`|Optional. Überträgt die Steuerung an den Anfang der `For Each` Schleife.|  
|`Exit For`|Optional. Überträgt die Steuerung von der `For Each` Schleife.|  
|`Next`|Erforderlich. Beendet die Definition der `For Each` Schleife.|  
  
## <a name="simple-example"></a>Einfaches Beispiel  
 Use a `For Each`... `Next` auf, wenn Sie eine Gruppe von Anweisungen für jedes Element einer Auflistung oder ein Array wiederholen möchten.  
  
> [!TIP]
>  A [For... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) funktioniert gut, wenn jede Iteration einer Schleife einer Steuerelementvariablen zuordnen und diese Variable Anfangs- und Endwert bestimmt werden kann. Beim Umgang mit einer Auflistung, jedoch ist das Konzept der Anfangs-und Endwert nicht aussagekräftig, und kennen Sie nicht unbedingt die Anzahl der Elemente die Auflistung hat. In diesem Fall eine `For Each`... `Next` Schleife ist häufig die bessere Wahl.  
  
 Im folgenden Beispiel die `For Each`...`Next` -Anweisung durchläuft alle Elemente einer Liste-Auflistung.  
  
 [!code-vb[VbVbalrStatements&#121;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Weitere Beispiele finden Sie unter [Sammlungen](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) und [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Nested Loops  
 Sie können schachteln `For Each` Schleifen eine Schleife in eine andere einfügen.  
  
 Im folgende Beispiel werden geschachtelte `For Each`...`Next` Strukturen.  
  
 [!code-vb[VbVbalrStatements&#122;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 Wenn Sie Schleifen zu schachteln, jede Schleife benötigen eine eindeutige `element` Variable.  
  
 Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Für beenden und fortsetzen für  
 Die [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung führt zum Beenden der `For`...`Next` Schleife und überträgt die Steuerung an die Anweisung nach der `Next` Anweisung.  
  
 Die `Continue For` -Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel zeigt, wie Sie die `Continue For` und `Exit For` Anweisungen.  
  
 [!code-vb[VbVbalrStatements&#123;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 Sie können eine beliebige Anzahl von ablegen `Exit For` -Anweisungen in einem `For Each` Schleife. Bei Verwendung in geschachtelten `For Each` Schleifen `Exit For` führt zum Beenden der innersten Schleife und überträgt die Steuerung auf die nächsthöhere Schachtelungsebene.  
  
 `Exit For`wird häufig verwendet, nachdem eine Auswertung einer Bedingung, z. B. in einer `If`... `Then`... `Else` Struktur. Möglicherweise möchten Sie verwenden `Exit For` für folgende Zwecke:  
  
-   Weitere durchlaufen ist unnötig oder unmöglich. Dies kann durch einen fehlerhaften Wert oder eine Anforderung zum Beenden liegen.  
  
-   Wird eine Ausnahme einer `Try`... `Catch`... `Finally`. Sie können `Exit For` am Ende der `Finally` Block.  
  
-   Es gibt eine Endlosschleife, also eine Schleife, die eine große oder sogar unendliche Anzahl von Malen ausgeführt werden. Wenn Sie eine solche Bedingung feststellen, können Sie `Exit For` um die Schleife zu verlassen. Weitere Informationen finden Sie unter [tun... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Iteratoren  
 Sie verwenden ein *Iterator* auf eine benutzerdefinierte Iteration durch eine Auflistung auszuführen. Ein Iterator kann eine Funktion oder ein `Get` Accessor. Er verwendet eine `Yield` -Anweisung jedes Element der Auflistung zu einem Zeitpunkt zurückgegeben.  
  
 Sie rufen den Iterator mithilfe einer `For Each...Next` Anweisung. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn ein `Yield` -Anweisung erreicht wird, in der Iterator, der Ausdruck in der `Yield` Anweisung zurückgegeben wird und die aktuelle Position im Code beibehalten wird. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Im folgenden Beispiel wird eine Iteratorfunktion. Der Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers` -Methode, jede Iteration der `For Each` Anweisungstext erstellt einen Aufruf an die Iteratorfunktion, der auf die nächste übergeht `Yield` Anweisung.  
  
 [!code-vb[127 VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7), [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md), und [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Wenn ein `For Each`...`Next` Anweisung ausgeführt wird, Visual Basic wertet die Auflistung nur einmal, bevor die Schleife gestartet wird. Wenn der Anweisungsblock ändert `element` oder `group`, diese Änderungen wirken sich nicht auf die Iteration der Schleife.  
  
 Wenn alle Elemente in der Auflistung zugewiesen wurden `element`, `For Each` -Schleife beendet und die folgende Anweisung wird die Steuerung der `Next` Anweisung.  
  
 Wenn `element` noch nicht deklariert wurde außerhalb dieser Schleife deklarieren Sie müssen sie in der `For Each` Anweisung. Sie können den Typ deklarieren `element` explizit mithilfe einer `As` -Anweisung, oder Sie können auf den Typrückschluss zur Zuweisung des Typs verlassen. In beiden Fällen den Bereich der `element` ist der Text der Schleife. Sie können jedoch nicht deklarieren `element` sowohl außerhalb und innerhalb der Schleife.  
  
 Sie können optional angeben `element` in der `Next` Anweisung. Dies verbessert die Lesbarkeit des Programms, insbesondere bei geschachtelten `For Each` Schleifen. Sie müssen dieselbe Variable angeben, wie der in der entsprechenden `For Each` Anweisung.  
  
 Möglicherweise möchten Sie zu vermeiden, ändern den Wert des `element` in einer Schleife. Auf diese Weise kann erschweren lesen und Debuggen des Codes. Ändern den Wert des `group` hat keinen Einfluss auf die Auflistung oder ihre Elemente aus, die bestimmt wurden, wenn die Schleife.  
  
 Wenn Sie sind Schachteln von Schleifen, wenn ein `Next` einer äußeren Schachtelungsebene-Anweisung vor der `Next` einer inneren Ebene, signalisiert der Compiler einen Fehler. Allerdings der Compiler erkennt dies überlappende Fehler nur, wenn `element` in jedem `Next` Anweisung.  
  
 Wenn der Code in einer Auflistung in einer bestimmten Reihenfolge durchlaufen einer `For Each`... `Next` Schleife ist nicht die beste Wahl, es sei denn, Sie kennen die Merkmale des Enumerationsobjekts der Auflistung verfügbar macht. Die Reihenfolge des Durchlaufs wird nicht durch Visual Basic, festgelegt, sondern von der <xref:System.Collections.IEnumerator.MoveNext%2A>Methode des Enumeratorobjekts.</xref:System.Collections.IEnumerator.MoveNext%2A> Aus diesem Grund Sie möglicherweise nicht um vorherzusagen, welches Element der Auflistung zurückgegeben werden als erster ist `element`, oder die als Nächstes nach einem bestimmten Element zurückgegeben werden. Erzielen Sie möglicherweise zuverlässiger Ergebnisse, die mit einer anderen Schleife, z. B. `For`... `Next` or `Do`... `Loop`.  
  
 Der Datentyp des `element` müssen zulassen, dass der Datentyp der Elemente des `group` können konvertiert werden kann.  
  
 Der Datentyp des `group` muss ein Referenztyp, der verweist auf eine Auflistung oder ein Array, das aufzählbar ist. Meist bedeutet dies, dass `group` bezieht sich auf ein Objekt, das implementiert die <xref:System.Collections.IEnumerable>Schnittstelle die `System.Collections` Namespace oder die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle die `System.Collections.Generic` Namespace.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> `System.Collections.IEnumerable`definiert die <xref:System.Collections.IEnumerable.GetEnumerator%2A>Methode, die ein Enumeratorobjekt für die Sammlung zurückgibt.</xref:System.Collections.IEnumerable.GetEnumerator%2A> Das Enumerationsobjekt implementiert die `System.Collections.IEnumerator` Schnittstelle die `System.Collections` Namespace und macht die <xref:System.Collections.IEnumerator.Current%2A>Eigenschaft und die <xref:System.Collections.IEnumerator.Reset%2A>und <xref:System.Collections.IEnumerator.MoveNext%2A>Methoden.</xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.Current%2A> Visual Basic verwendet diese, um die Auflistung zu durchlaufen.  
  
### <a name="narrowing-conversions"></a>Einschränkende Konvertierungen  
 Wenn `Option Strict` Wert `On`, einschränkende Konvertierungen normalerweise Compilerfehler verursachen. In einer `For Each` -Anweisung jedoch Konvertierungen von den Elementen in `group` auf `element` ausgewertet werden und zur Laufzeit ausgeführt und Compilerfehler durch einschränkende Konvertierungen werden unterdrückt.  
  
 Im folgenden Beispiel die Zuweisung von `m` als Anfangswert für `n` nicht kompiliert, wenn `Option Strict` ist auf, da die Konvertierung von einer `Long` , ein `Integer` ist eine einschränkende Konvertierung. In der `For Each` -Anweisung ist jedoch kein Compilerfehler gemeldet, obwohl die Zuweisung zu `number` erfordert dieselbe Konvertierung von `Long` auf `Integer`. In der `For Each` Anweisung, die eine große Anzahl enthält, die ein Laufzeitfehler tritt auf, wenn <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>auf die große Anzahl angewendet wird.</xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>  
  
 [!code-vb[VbVbalrStatements&#89;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>IEnumerator-Aufrufe  
 Bei der Ausführung einer `For Each`... `Next` -Schleife beginnt, überprüft Visual Basic, die `group` bezieht sich auf ein gültiges Auflistungsobjekt. Wenn dies nicht der Fall ist, wird eine Ausnahme ausgelöst. Andernfalls ruft sie die <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode und der <xref:System.Collections.IEnumerator.Current%2A>Eigenschaft des Enumeratorobjekts auf das erste Element zurückzugeben.</xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> Wenn `MoveNext` gibt an, dass keine nächste Element, d. h., wenn die Auflistung leer ist, ist die `For Each` -Schleife beendet und die Steuerung an die Anweisung nach übergeben der `Next` Anweisung. Andernfalls legt Visual Basic `element` mit dem ersten Element und führt den Anweisungsblock.  
  
 Jedes Mal, wenn Visual Basic stößt der `Next` -Anweisung gibt es die `For Each` Anweisung. Erneut aufgerufen `MoveNext` und `Current` das nächste Element, und erneut entweder der Block ausgeführt oder beendet die Schleife je nach Ergebnis. Dieser Prozess wird fortgesetzt, bis `MoveNext` gibt an, dass kein nächsten Element vorhanden ist oder eine `Exit For` -Anweisung auftritt.  
  
 **Ändern der Auflistung.** Das Enumeratorobjekt, das von zurückgegebene <xref:System.Collections.IEnumerable.GetEnumerator%2A>normalerweise nicht, dass Sie die Auflistung durch Hinzufügen, löschen, ersetzen oder Neuordnen von Elementen ändern.</xref:System.Collections.IEnumerable.GetEnumerator%2A> Wenn Sie die Auflistung ändern, nachdem Sie initiiert eine `For Each`... `Next` -Schleife, das Enumerationsobjekt ungültig und bewirkt, dass der nächste Zugriffsversuch auf ein Element ein <xref:System.InvalidOperationException>Ausnahme.</xref:System.InvalidOperationException>  
  
 Jedoch diese Blockierung der Änderung ist nicht ermittelt [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], sondern durch die Implementierung der <xref:System.Collections.IEnumerable>Schnittstelle.</xref:System.Collections.IEnumerable> Es ist möglich, implementieren `IEnumerable` auf eine Weise, die Änderung während der Iteration ermöglicht. Wenn Sie erwägen, Durchführung einer solchen dynamischen Änderung, stellen Sie sicher, dass Sie wissen, dass die Merkmale des der `IEnumerable` Implementierung für die Sammlung, die Sie verwenden.  
  
 **Ändern die Elemente der Auflistung.** Die <xref:System.Collections.IEnumerator.Current%2A>-Eigenschaft des Enumeratorobjekts ist [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), und es gibt eine lokale Kopie jedes Auflistungselements.</xref:System.Collections.IEnumerator.Current%2A> Dies bedeutet, dass Sie die Elemente selbst können nicht in einem `For Each`... `Next` loop. Jede Änderung, die Sie vornehmen, wirkt sich nur auf die lokale Kopie von `Current` und ist nicht in der zugrunde liegenden Auflistung übernommen. Allerdings können ein Element ein Verweistyp ist, Sie die Member der Instanz ändern, auf die es verweist. Das folgende Beispiel ändert die `BackColor` Mitglied aller `thisControl` Element. Nicht möglich ist, Sie jedoch ändern `thisControl` selbst.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Das vorherige Beispiel ändern kann die `BackColor` Mitglied aller `thisControl` -Element, jedoch nicht geändert werden kann `thisControl` selbst.  
  
 **Durchlaufen von Arrays.** Da die <xref:System.Array>-Klasse implementiert die <xref:System.Collections.IEnumerable>-Schnittstelle verfügbar machen, alle Arrays der <xref:System.Array.GetEnumerator%2A>-Methode.</xref:System.Array.GetEnumerator%2A> </xref:System.Collections.IEnumerable> </xref:System.Array> Das bedeutet, dass Sie ein Array mit einem `For Each`... `Next` loop. Sie können jedoch die Elemente des Arrays schreibgeschützt. Sie können nicht geändert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Ordner im Verzeichnis C:\ mithilfe der <xref:System.IO.DirectoryInfo>Klasse.</xref:System.IO.DirectoryInfo>  
  
 [!code-vb[VbVbalrStatements&#124;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. Im Beispiel werden Instanzen von sortiert eine `Car` -Klasse, die in eine <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> gespeichert sind Die `Car` -Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die erfordert, dass die <xref:System.IComparable%601.CompareTo%2A>-Methode implementiert werden.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601>  
  
 Jeder Aufruf von der <xref:System.IComparable%601.CompareTo%2A>-Methode führt einen einzelnen Vergleich, der für die Sortierung verwendet wird.</xref:System.IComparable%601.CompareTo%2A> Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.  
  
 In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>Methode der <xref:System.Collections.Generic.List%601>bewirkt, dass die `CompareTo` automatisch für die aufzurufende Methode der `Car` Objekte in der `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A>  
  
 [!code-vb[VbVbalrStatements&#125;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sammlungen](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)   
 [Für... Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While... While-Anweisung beenden](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Führen Sie... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
