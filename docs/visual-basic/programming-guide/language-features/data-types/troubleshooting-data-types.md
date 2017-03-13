---
title: "Troubleshooting Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Char data type, converting"
  - "Decimal data type, conversions"
  - "data types [Visual Basic], troubleshooting"
  - "literals, default types"
  - "type characters, literal"
  - "Mod operator [Visual Basic], in floating-point operations"
  - "troubleshooting Visual Basic, data types"
  - "troubleshooting data types"
  - "floating-point numbers, precision"
  - "Boolean data type, converting"
  - "literal types"
  - "literal type characters"
  - "floating-point numbers, imprecision"
  - "String data type, converting"
  - "floating-point numbers, comparison"
  - "floating-point numbers"
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Troubleshooting Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Auf dieser Seite sind einige Probleme aufgeführt, die häufig auftreten, wenn Operationen mit systeminternen Datentypen ausgeführt werden.  
  
## Gleitkommaausdrücke werden nicht als gleich ausgewertet  
 Wenn Sie mit Gleitkommazahlen \([Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) und [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)\) arbeiten, beachten Sie, dass sie als Binärbrüche gespeichert werden.  Das bedeutet, dass sie keine präzise Darstellung einer Größe speichern können, die kein Binärbruch ist \(ein Binärbruch ist eine Größe von der Form k \/ \(2 ^ n\)\), wobei k und n ganze Zahlen sind\).  Beispielsweise können 0,5 \(\= 1\/2\) and 0,3125 \(\= 5\/16\) als präzise Werte gespeichert werden, während 0,2 \(\= 1\/5\) und 0,3 \(\= 3\/10\) nur annähernd genau gespeichert werden können.  
  
 Aufgrund dieser Ungenauigkeit können Sie keine genauen Ergebnissen erwarten, wenn Sie mit Gleitkommawerten arbeiten.  Insbesondere können zwei Werte, die theoretisch gleich sind, geringfügig unterschiedliche Darstellungen aufweisen.  
  
||  
|-|  
|So vergleichen Sie Gleitkommagrößen|  
|1.  Berechnen Sie den Absolutbetrag ihrer Differenz mit der <xref:System.Math.Abs%2A>\-Methode der <xref:System.Math>\-Klasse im <xref:System>\-Namespace.<br />2.  Legen Sie eine maximal zulässige Differenz fest, um die beiden Größen für praktische Zwecke als gleich zu betrachten, sofern ihre Abweichung nicht größer ist.<br />3.  Vergleichen Sie den absoluten Wert der Abweichung mit der zulässigen Abweichung.|  
  
 Im folgenden Beispiel wird sowohl ein korrekter als auch ein fehlerhafter Vergleich zweier `Double`\-Werte veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 Im vorhergehenden Beispiel wird die <xref:System.Double.ToString%2A>\-Methode der <xref:System.Double>\-Struktur verwendet. So wird eine größere Genauigkeit als mit dem `CStr`\-Schlüsselwort erreicht.  Der Standardwert ist 15 Stellen, aber mit dem Format "G17" wird er auf 17 Stellen erweitert.  
  
## Der Operator 'Mod' gibt kein präzises Ergebnis zurück  
 Aufgrund der Ungenauigkeit beim Speichern von Gleitkommazahlen kann der [Operator Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) ein unerwartetes Ergebnis zurückgeben, wenn mindestens einer der Operanden eine Gleitkommazahl ist.  
  
 Der [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) verwendet keine Gleitkommadarstellung.  Viele Zahlen, die mit `Single` und `Double` ungenau sind, sind mit `Decimal` genau \(z. B. 0,2 und 0,3\).  Obwohl die Berechnung mit `Decimal` langsamer als mit Gleitkommazahlen erfolgt, wiegt die größere Genauigkeit die geringere Leistung eventuell auf.  
  
||  
|-|  
|So ermitteln Sie den ganzzahligen Rest von Gleitkommagrößen|  
|1.  Deklarieren Sie Variablen als `Decimal`.<br />2.  Verwenden Sie das Literaltypzeichen `D`, um `Decimal` für Literale zu erzwingen, für den Fall, dass sie für den `Long`\-Datentyp zu groß sind.|  
  
 Im folgenden Beispiel wird die potenzielle Ungenauigkeit von Gleitkommaoperanden veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 Im vorhergehenden Beispiel wird die <xref:System.Double.ToString%2A>\-Methode der <xref:System.Double>\-Struktur verwendet. So wird eine größere Genauigkeit als mit dem `CStr`\-Schlüsselwort erreicht.  Der Standardwert ist 15 Stellen, aber mit dem Format "G17" wird er auf 17 Stellen erweitert.  
  
 Weil `zeroPointTwo` `Double` ist, ist sein Wert für 0,2 ein unendlicher Binärbruch mit dem gespeicherten Wert 0,20000000000000001.  Die Division von 2,0 durch diese Größe ergibt 9,9999999999999995 mit dem Rest 0,19999999999999991.  
  
 Im zweiten Ausdruck für `decimalRemainder` erzwingt das Literaltypzeichen `D`, dass beide Operanden den `Decimal`\-Datentyp aufweisen, und 0,2 wird präzise dargestellt.  Darum liefert der Operator `Mod` den erwarteten Rest 0,0.  
  
 Beachten Sie, dass es nicht ausreicht, `decimalRemainder` als `Decimal` zu deklarieren.  Sie müssen außerdem für die Literale `Decimal` erzwingen. Andernfalls ist ihr Standarddatentyp `Double`, und `decimalRemainder` erhält denselben ungenauen Wert wie `doubleRemainder`.  
  
## Boolescher Typ wird nicht präzise in den numerischen Typ konvertiert  
 [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)\-Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sollen nicht mit Zahlen gleichwertig sein.  Aus Gründen der Kompatibilität mit älteren Versionen stellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Konvertierungsschlüsselwörter \([CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt` usw.\) zum Konvertieren zwischen `Boolean`\-Typen und numerischen Typen bereit.  In anderen Sprachen werden diese Konvertierungen jedoch zuweilen anders ausgeführt als mit den [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Methoden.  
  
 Sie sollten nie Code schreiben, der von entsprechenden numerischen Werten für `True` und `False` abhängt.  Beschränken Sie den Einsatz von `Boolean`\-Variablen auf die logischen Werte, für die sie entworfen wurden.  Wenn es erforderlich ist, `Boolean`\-Werte und numerische Werte zu mischen, müssen Sie wissen, wie die gewählte Konvertierungsmethode arbeitet.  
  
### Konvertierung in Visual Basic  
 Wenn Sie mithilfe der Konvertierungsschlüsselwörter `CType` oder `CBool` numerische Datentypen in `Boolean` konvertieren, wird aus 0 `False` und aus alle anderen Werten `True`.  Wenn Sie `Boolean`\-Werte mit den Konvertierungsschlüsselwörtern in numerische Typen konvertieren, wird `False` zu 0 und `True` zu \-1.  
  
### Konvertierung in .NET Framework  
 Die <xref:System.Convert.ToInt32%2A>\-Methode der <xref:System.Convert>\-Klasse im <xref:System>\-Namespace konvertiert `True` in \+1.  
  
 Achten Sie auf die verwendete Konvertierungsmethode, wenn Sie einen `Boolean`\-Wert in einen numerischen Datentyp konvertieren.  
  
## Zeichenliteral generiert Compilerfehler  
 Sind keine Typzeichen angeben, verwendet [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] für Literale Standarddatentypen.  Der Standardtyp für ein Zeichenliteral – in Anführungszeichen \(`" "`\) – ist `String`.  
  
 Der `String`\-Datentyp wird nicht zum [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md) erweitert.  Wenn Sie einer `Char`\-Variablen ein Literal zuweisen möchten, müssen Sie daher entweder eine Einschränkungskonvertierung ausführen oder den `Char`\-Typ für das Literal erzwingen.  
  
||  
|-|  
|So erstellen Sie ein Zeichenliteral, um es einer Variablen oder Konstanten zuzuweisen|  
|1.  Deklarieren Sie die Variable oder die Konstante als `Char`.<br />2.  Schließen Sie den Zeichenwert in Anführungszeichen \(`" "`\) ein.<br />3.  Fügen Sie nach dem schließenden doppelten Anführungszeichen das Literaltypzeichen `C` ein, um `Char` für das Literal zu erzwingen.  Dies ist erforderlich, falls für die Typüberprüfung \([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) `On` festgelegt ist, und empfiehlt sich auf jeden Fall.|  
  
 Im folgenden Beispiel werden sowohl fehlgeschlagene als auch erfolgreiche Zuweisungen eines Literals zu einer `Char`\-Variablen veranschaulicht.  
  
 [!CODE [VbVbalrStatements#49](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#49)]  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Die Verwendung von Einschränkungskonvertierungen ist immer mit Risiken verbunden, weil sie zur Laufzeit fehlschlagen können.  Beispielsweise kann eine Konvertierung von `String` in `Char` fehlschlagen, wenn der `String`\-Wert mehrere Zeichen enthält.  In gut geschriebenen Programmen wird daher das `C`\-Typzeichen verwendet.  
  
## Zeichenfolgenkonvertierung schlägt zur Laufzeit fehl  
 Der [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) ist an sehr wenigen Erweiterungskonvertierungen beteiligt.  `String` wird nur in sich selbst und zu `Object` erweitert, und nur `Char` und `Char()` \(ein `Char`\-Array\) werden zu `String` erweitert.  Der Grund hierfür ist, dass `String`\-Variablen und \-Konstanten Werte enthalten können, die andere Datentypen nicht behandeln können.  
  
 Wenn die Typüberprüfung \([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) den Wert `On` hat, lässt der Compiler keine impliziten einschränkenden Konvertierungen zu.  Das gilt auch für solche, die `String` betreffen.  Im Code können dennoch Konvertierungsschlüsselwörter wie `CStr` und [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) verwendet werden, die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] anweisen, die Konvertierung auszuführen.  
  
> [!NOTE]
>  Der Fehler für einschränkende Konvertierung wird unterdrückt für Konvertierungen von den Elementen in einer `For Each…Next`\-Auflistung zur Schleifensteuerungsvariable.  Weitere Informationen und Beispiele finden Sie im Abschnitt "Eingrenzende Konvertierungen" unter [For Each...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### Schutz von Einschränkungskonvertierungen  
 Einschränkungskonvertierungen weisen den Nachteil auf, dass sie zur Laufzeit fehlschlagen können.  Wenn z. B. eine `String`\-Variable einen anderen Wert als "True" oder "False" enthält, kann sie nicht in `Boolean` konvertiert werden.  Wenn sie Satzzeichen enthält, schlägt die Konvertierung in jeden numerischen Typ fehl.  Sofern Sie nicht sicher sind, dass eine `String`\-Variable immer Werte enthält, die mit dem Zieltyp kompatibel sind, sollten Sie keine Konvertierung durchführen.  
  
 Wenn Sie `String` in einen anderen Datentyp konvertieren müssen, ist es am sichersten, die Konvertierung in eine [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) einzuschließen.  Dies ermöglicht die Behandlung eines Laufzeitfehlers.  
  
### Zeichenarrays  
 Sowohl ein einzelnes Zeichen vom Typ `Char` als auch ein Array von `Char`\-Elementen wird zu `String` erweitert.  `String` wird jedoch nicht zu `Char()` erweitert.  Um einen `String`\-Wert zu einem `Char`\-Array zu erweitern, können Sie die <xref:System.String.ToCharArray%2A>\-Methode der <xref:System.String?displayProperty=fullName>\-Klasse verwenden.  
  
### Bedeutungslose Werte  
 Im Allgemeinen sind `String`\-Werte in anderen Datentypen ohne Bedeutung, und die Konvertierung ist von nur theoretischem Nutzen und sehr gefährlich.  Beschränken Sie die Verwendung von `String`\-Variablen nach Möglichkeit auf die Zeichenfolgen, für die sie entworfen wurden.  Schreiben Sie niemals Code, der von entsprechenden Werten in anderen Datentypen abhängt.  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)