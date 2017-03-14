---
title: "Yield-Anweisung (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Yield"
helpviewer_keywords: 
  - "Iteratoren, Yield-Anweisung [Visual Basic]"
  - "Iteratoren [Visual Basic]"
  - "Yield-Anweisung [Visual Basic]"
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Yield-Anweisung (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sendet das folgende Element einer Auflistung einer `For Each...Next`\-Anweisung.  
  
## Syntax  
  
```  
Yield expression  
```  
  
#### Parameter  
  
|||  
|-|-|  
|Begriff|Definition|  
|`expression`|Erforderlich.  Ein Ausdruck, der dem Typ der Iteratorfunktion oder des `Get` Accessor implizit in ist, der die `Yield`\-Anweisung enthält.|  
  
## Hinweise  
 Die `Yield`\-Anweisung ist ein Element einer Auflistung auf einmal zurück.  Die `Yield`\-Anweisung wird in einer Iteratorfunktion oder in einem `Get` Accessor enthalten, die benutzerdefinierte Iterationen zu einer Auflistung ausführen.  
  
 Sie verwenden eine Iteratorfunktion, indem Sie [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oder eine LINQ\-Abfrage verwenden.  Jede Iteration der Schleife `For Each` ruft die Iteratorfunktion auf.  Wenn eine `Yield`\-Anweisung in der Iteratorfunktion erreicht ist, wird `expression` zurückgegeben, und die aktuelle Position im Code wird beibehalten.  Die Ausführung von diesem Speicherort beim nächsten Mal neu gestartet, dass die Iteratorfunktion aufgerufen wird.  
  
 Eine implizite Konvertierung muss vom Typ von `expression` in der `Yield`\-Anweisung an den Rückgabetyp des Iterators vorhanden sind.  
  
 Sie können eine `Exit Function` oder `Return`\-Anweisung verwenden, um die Iteration zu beenden.  
  
 "Yield" ist kein reserviertes Wort und ist eine besondere Bedeutung, falls dies in einer `Iterator`\-Funktion oder in einem `Get` Accessor verwendet wird.  
  
 Weitere Informationen zu Iteratorfunktionen und `Get` Accessoren, finden Sie unter [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Iterator\-Funktionen und get\-Accessoren  
 Die Deklaration einer Iteratorfunktion oder des `Get` Accessor muss die folgenden Anforderungen erfüllen:  
  
-   Sie muss einen [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)\-Modifizierer einschließen.  
  
-   Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.  
  
-   Es kann keine `ByRef`\-Parameter haben.  
  
 Eine Iteratorfunktion kann nicht in einem Ereignis, in einem Instanzenkonstruktor, in einem statischen Konstruktor oder in einem statischen Destruktor auftreten.  
  
 Eine Iteratorfunktion können anonyme Funktion sein.  Weitere Informationen finden Sie unter [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Ausnahmebehandlung  
 Eine `Yield`\-Anweisung kann innerhalb eines Blocks von `Try`[Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) sein.  Ein `Try`\-Block, der eine `Yield`\-Anweisung hat, kann `Catch` Blöcke haben und kann einen `Finally`\-Block haben.  
  
 Eine `Yield`\-Anweisung kann nicht innerhalb eines `Catch`\-Blocks oder eines \- Blocks `Finally` sein.  
  
 Wenn der `For Each` Text \(außerhalb der Iteratorfunktion\) eine Ausnahme auslöst, wird ein `Catch`\-Block in der Iteratorfunktion nicht ausgeführt, aber ein `Finally`\-Block in der Iteratorfunktion wird ausgeführt.  Ein `Catch`\-Block in einer Iteratorfunktion fängt nur Ausnahmen ab, die in der Iteratorfunktion auftreten.  
  
## Technische Implementierung  
 Der folgende Code gibt `IEnumerable (Of String)` aus einer Iteratorfunktion zurück und durchläuft dann durch die Elemente `IEnumerable (Of String)` durch.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Der Aufruf `MyIteratorFunction` führt nicht den Text der Funktion aus.  Stattdessen beim Aufruf `IEnumerable(Of String)` in die `elements`\-Variable.  
  
 Auf einer Iteration der Schleife `For Each`, wird die <xref:System.Collections.IEnumerator.MoveNext%2A>\-Methode für `elements` aufgerufen.  Dieser Aufruf wird der Text von `MyIteratorFunction` aus, bis die folgende Anweisung `Yield` erreicht ist.  Die `Yield`\-Anweisung gibt einen Ausdruck zurück, der nicht nur den Wert der `element`\-Variable für die Konsumierung durch den Schleifentext jedoch auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A>\-Eigenschaft von Elementen bestimmt, die `IEnumerable (Of String)` ist.  
  
 Klicken Sie in der nächsten Iteration `For Each`\-Schleife, setzt die Ausführung des Iteratortexts der, in denen diese durch unterzogen fort und erneut angehalten wird, wenn sie eine `Yield`\-Anweisung erreicht.  Die `For Each`\-Schleife werden abgeschlossen, wenn das Ende der Iteratorfunktion oder der `Return` oder `Exit Function`\-Anweisung erreicht wird.  
  
## Beispiel  
 Das folgende Beispiel enthält eine `Yield`\-Anweisung, die innerhalb einer [Für... Next\-Schleife](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife ist.  Jede Iteration des [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md)\-Anweisungstexts in `Main` erstellt einen Aufruf der `Power` Iteratorfunktion.  Jeder Aufruf der Iteratorfunktion wechselt zur nächsten Ausführung der `Yield`\-Anweisung über, die während der nächsten Iteration der Schleife `For…Next` auftritt.  
  
 Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601>, ein Iteratorschnittstellentyp.  Wenn die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein `Get` Accessor, der ein Iterator ist.  Die Eigenschaftendeklaration umfasst einen `Iterator`\-Modifizierer.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Anforderungen  
 [!INCLUDE[vs_dev11_long](~/includes/vs-dev11-long-md.md)]  
  
## Siehe auch  
 [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Statements](../../../visual-basic/language-reference/statements/index.md)