---
title: "Special Characters in Code (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.)"
  - "vb.("
  - "vb.colon"
  - "vb.!"
  - "vb.."
  - "vb.:"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "special characters, in code"
  - "parentheses, using in code"
  - "colons (:)"
  - "period character in code"
  - "dot operator (.)"
  - "dictionary access operator"
  - "concatenation operators, special characters in code"
  - "concatenation operators, vs. addition operator"
  - "! operator"
  - "separators, using in code"
  - "operators [Visual Basic], dictionary access"
  - ": separator character"
  - "member access operator"
  - "addition operator"
  - "operators [Visual Basic], member access"
  - ". operator"
  - "exclamation points"
  - "separators"
  - "exclamation point operator (!)"
  - "Visual Basic code, special characters"
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Special Characters in Code (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Manchmal ist es erforderlich, im Code Sonderzeichen, also nicht alphanumerische Zeichen, zu verwenden.  Zeichensetzung und Sonderzeichen im Zeichensatz von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] haben verschiedene Funktionen. Diese reichen von der Strukturierung des Programmtexts bis zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführen.  Sie legen keine auszuführende Operation fest.  
  
## Runde Klammern  
 Verwenden Sie Klammern zur Definition einer Prozedur, wie `Sub` oder `Function`.  Alle Prozedurargumentlisten müssen in Klammern stehen.  Sie verwenden auch Klammern, um Variablen oder Argumente in logischen Gruppen anzuordnen, insbesondere, um die Standardoperatorrangfolge in einem komplexen Ausdruck zu überschreiben.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 Nach der Ausführung des vorangehenden Codes lautet der Wert von `d` "8.225" und der Wert von `e` "3".  In der Berechnung von `d` wird die Standardrangfolge von `/` vor `+` verwendet. Dies entspricht `d = b + (c / a)`.  Die Klammern in der Berechnung von `e` überschreiben die Standardrangfolge.  
  
## Trennzeichen  
 Wie der Name bereits verrät, haben Trennzeichen die Aufgabe, Codeabschnitte voneinander zu trennen.  Das Trennzeichen in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ist der Doppelpunkt \(`:`\).  Verwenden Sie Trennzeichen, wenn Sie mehrere Anweisungen in dieselbe Zeile schreiben möchten.  Dies spart Platz und erhöht die Lesbarkeit des Codes.  Das folgende Beispiel besteht aus drei Anweisungen, die durch Doppelpunkte getrennt sind.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Das Doppelpunktzeichen \(`:`\) wird auch verwendet, um eine Anweisungsbezeichnung zu kennzeichnen.  Weitere Informationen finden Sie unter [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## Verkettung  
 Verwenden Sie den Operator `&` für die *Verkettung* bzw. das Verknüpfen von Zeichenfolgen.  Er ist nicht zu verwechseln mit dem Operator `+`, der numerische Werte addiert.  Die Verwendung des Operators `+` zum Verketten numerischer Werte kann fehlerhafte Ergebnisse zur Folge haben.  Das folgende Beispiel veranschaulicht dies.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 Nach der Ausführung des vorangehenden Codes ist der Wert von `resultA` 21.01 und der Wert von `resultB` "10.0111".  
  
## Operatoren für den Memberzugriff  
 Um auf den Member eines Typs zuzugreifen, wird als Operator zwischen dem Typnamen und dem Membernamen ein Punkt \(`.`\) oder ein Ausrufezeichen \(`!`\) eingefügt.  
  
### Punkt \(.\) Operator  
 Verwenden Sie den Operator `.` für eine Klasse, Struktur, Schnittstelle oder Enumeration als Operator für den Memberzugriff.  Der Member kann ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode sein.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### Ausrufezeichen \(\!\) Operator  
 Verwenden Sie den Operator `!` nur bei Klassen oder Schnittstellen als Operator für den Wörterbuchzugriff.  Die Klasse oder Schnittstelle muss eine Standardeigenschaft aufweisen, die ein einzelnes `String`\-Argument akzeptiert.  Der Bezeichner direkt nach dem Operator `!` wird zu dem Argumentwert, der der Standardeigenschaft als Zeichenkette übergeben wird.  Das folgende Beispiel veranschaulicht dies.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Alle drei Ausgabezeilen von `MsgBox` zeigen den Wert `32856` an.  In der ersten Zeile wird der herkömmliche Zugriff auf den `index` der Eigenschaft verwendet, in der zweiten Zeile wird der Umstand genutzt, dass `index` die Standardeigenschaft der Klasse `hasDefault` ist, und in der dritten Zeile wird der Dictionaryzugriff auf die Klasse verwendet.  
  
 Beachten Sie, dass der zweite Operand des Operators `!` ein gültiger Visual Basic\-Bezeichner sein muss, der nicht in doppelte Anführungszeichen \(`" "`\) eingeschlossen ist.  In anderen Worten, Sie können kein Zeichenfolgenliteral und keine Zeichenfolgenvariable verwenden.  Durch die folgende Änderung der letzten Zeile im Aufruf von `MsgBox` wird ein Fehler generiert, da `"X"` ein in Anführungszeichen eingeschlossenes Zeichenfolgenliteral ist.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Verweise auf Standardauflistungen müssen explizit sein.  Insbesondere können Sie den Operator `!` nicht für eine spät gebundene Variable verwenden.  
  
 Das `!`\-Zeichen wird auch als Zeichen für den `Single`\-Typ verwendet.  
  
## Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)