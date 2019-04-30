---
title: Problembehandlung bei Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: 851be5bdf4a3adced724dc2df33657a84226270d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906957"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Problembehandlung bei Datentypen (Visual Basic)
Diese Seite listet einige der häufigsten Probleme, die auftreten können, bei der Durchführung von Vorgängen für systeminterne Datentypen.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Gleitkomma-Ausdrücke vergleichen nicht gleichwertig  
 Beim Arbeiten mit Gleitkommazahlen ([Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) und [Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md)), beachten Sie, dass sie als binäre Brüche gespeichert werden. Dies bedeutet, sie können nicht von jeder beliebigen Menge, die nicht Binärbruch ist eine genaue Darstellung enthalten (im Format k / (2 ^ n), k und n sind ganze Zahlen). Beispielsweise können 0,5 (= 1/2) und 0,3125 (= 5/16) als präzise Werte gespeichert werden, während 0,2 (= 1/5) und (3/10 =) 0.3 nur Näherungswerte sein können.  
  
 Aus diesem Grund können keine Ungenauigkeit, Sie genaue Ergebnisse verlassen bei Gleitkommazahlen-Punktwerte bearbeitet werden. Insbesondere möglicherweise zwei Werte, die theoretisch gleich sind leicht unterschiedliche Darstellungen.  
  
| Um gleitkommamengen zu vergleichen. | 
|---| 
|1.  Berechnen Sie den absoluten Wert des ihrer Differenz mithilfe der <xref:System.Math.Abs%2A> -Methode der der <xref:System.Math> -Klasse in der <xref:System> Namespace.<br />2.  Bestimmen Sie eine zulässige maximale Abweichung, Sie, die zwei Mengen aus praktischen Gründen gleich sein erwägen können, wenn die Differenz nicht größer ist.<br />3.  Vergleichen Sie den absoluten Wert des Unterschieds auf den zulässigen Unterschied.|  
  
 Im folgende Beispiel wird veranschaulicht, falschen und richtigen Vergleich von zwei `Double` Werte.  
  
 [!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]  
  
 Im vorherigen Beispiel verwendet die <xref:System.Double.ToString%2A> -Methode der der <xref:System.Double> so strukturieren, dass er größere Genauigkeit als angeben, kann die `CStr` -Schlüsselwort verwendet. Der Standardwert ist 15 Dezimalstellen, aber das Format "G17" erweitert diese um 17 Ziffern.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod-Operator gibt keine genaues Ergebnis zurück.  
 Aufgrund der Ungenauigkeit der Gleitkomma-Speicher der [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md) kann ein unerwartetes Ergebnis zurückgeben, wenn mindestens einer der Operanden eine Gleitkommazahl ist.  
  
 Die [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) gleitkommadarstellung nicht verwendet. Viele Zahlen, die in ungenau sind `Single` und `Double` genau in `Decimal` (z. B. 0.2 und 0.3). Obwohl die Berechnung langsamer `Decimal` als in Gleitkommazahlen, könnte nicht Schaden die geringere Leistung, größere Genauigkeit zu erreichen.  
  
|Um den ganzzahligen Rest-gleitkommamengen zu finden.|  
|---|  
|1.  Deklarieren Sie Variablen als `Decimal`.<br />2.  Verwenden Sie das literal-Typzeichen `D` Literale erzwingen `Decimal`, für den Fall, dass ihre Werte für zu groß sind die `Long` -Datentyp.|  
  
 Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden.  
  
 [!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]  
  
 Im vorherigen Beispiel verwendet die <xref:System.Double.ToString%2A> -Methode der der <xref:System.Double> so strukturieren, dass er größere Genauigkeit als angeben, kann die `CStr` -Schlüsselwort verwendet. Der Standardwert ist 15 Dezimalstellen, aber das Format "G17" erweitert diese um 17 Ziffern.  
  
 Da `zeroPointTwo` ist `Double`, der Wert für 0,2 ist ein unendlich Binärbruch mit dem gespeicherten Wert 0,20000000000000001. Führt zu 9,9999999999999995 mit dem Rest der 0,19999999999999991 2.0 durch diese Menge dividiert wird.  
  
 Im Ausdruck für `decimalRemainder`, dem literal-Typzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 verfügt über eine genaue Darstellung. Aus diesem Grund die `Mod` Operator liefert den erwarteten Rest von 0,0.  
  
 Beachten Sie, dass es nicht ausreichen, um zu deklarieren, `decimalRemainder` als `Decimal`. Sie müssen außerdem die Literale, erzwingen `Decimal`, oder sie verwenden `Double` standardmäßig und `decimalRemainder` empfängt ungenauen denselben Wert wie `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Boolean-Typ konvertiert nicht in numerischen Typ genau  
 [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sollen nicht Zahlen entsprechen. Kompatibilität mit früheren Versionen, Visual Basic bietet Konvertierungsschlüsselwörter ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`usw.) für die Konvertierung zwischen `Boolean` und numerischen Typen. Allerdings andere Sprachen manchmal diese Konvertierungen anders ausgeführt, wie die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Methoden.  
  
 Schreiben Sie Code, der auf den entsprechenden numerischen Werten für basiert `True` und `False`. Wann immer möglich, beschränken Sie die Verwendung von `Boolean` Variablen, um die logischen Werte, die für die sie entworfen werden. Wenn Sie kombinieren müssen `Boolean` und numerische Werte, stellen Sie sicher, dass Sie die Konvertierungsmethode verstehen, die Sie auswählen.  
  
### <a name="conversion-in-visual-basic"></a>Konvertieren in Visual Basic  
 Bei Verwendung der `CType` oder `CBool` Konvertierungsschlüsselwörter Konvertieren von numerischen Datentypen in `Boolean`, wird 0 `False` und alle anderen Werte werden `True`. Bei der Konvertierung `Boolean` Werten in numerische Typen mit den Konvertierungsschlüsselwörtern `False` ist 0 und `True` wird – 1.  
  
### <a name="conversion-in-the-framework"></a>Konvertierung in das Framework  
 Die <xref:System.Convert.ToInt32%2A> Methode der <xref:System.Convert> -Klasse in der <xref:System> Namespace konvertiert `True` bis + 1.  
  
 Wenn Sie konvertieren, müssen eine `Boolean` -Werts in einen numerischen Datentyp aufweisen, achten Sie darauf Konvertierungsmethode, die Sie verwenden.  
  
## <a name="character-literal-generates-compiler-error"></a>Zeichenfolgenliteral wird Compilerfehler generiert.  
 In Typzeichen vorhanden ist nimmt Visual Basic standardmäßig Datentypen für Literale. Der Standardtyp für ein Zeichenliteral – in Anführungszeichen eingeschlossen (`" "`) – wird `String`.  
  
 Die `String` Datentyp wird nicht erweitert werden, um die [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md). Dies bedeutet, dass, wenn Sie ein Literal zuweisen möchten eine `Char` Variable ist, müssen Sie eine einschränkende Konvertierung vornehmen oder erzwingen Sie das Literal für die `Char` Typ.  

|Um ein Zeichen zuweisen zu einer Variablen oder Konstanten Literalen erstellen|
|---|  
|1.  Deklarieren Sie die Variable oder Konstante als `Char`.<br />2.  Den Zeichenwert in Anführungszeichen einschließen (`" "`).<br />3.  Führen Sie das schließende Anführungszeichen mit dem literal-Typzeichen `C` zu erzwingen, dass das Literal für `Char`. Dies ist erforderlich, wenn die typüberprüfung wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On`, und es ist in jedem Fall wünschenswert.|  
  
 Das folgende Beispiel zeigt sowohl erfolgreiche als auch nicht erfolgreiche Zuweisungen von Literal zu einer `Char` Variable.  
  
 [!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]  
  
 Es besteht immer ein Risiko mit einschränkende Konvertierungen, da sie zur Laufzeit fehlschlagen können. Z. B. eine Konvertierung von `String` zu `Char` kann fehlschlagen, wenn die `String` Wert mehr als ein Zeichen enthält. Es ist daher besser Programmieren mit der `C` Typzeichen.  
  
## <a name="string-conversion-fails-at-run-time"></a>Zeichenfolgenkonvertierung zur Laufzeit fehlschlägt.  
 Die [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) nur sehr wenige erweiterungskonvertierungen beteiligt. `String` wird nur auf sich selbst und `Object`, und nur `Char` und `Char()` (eine `Char` Arrays) zu erweitert `String`. Grund hierfür ist, `String` können Variablen und Konstanten Werte, die andere Datentypen enthalten, darf nicht enthalten.  
  
 Wenn die typüberprüfung wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On`, der Compiler lässt alle implizite einschränkende Konvertierungen. Dies schließt Personen im Zusammenhang mit `String`. Code kann dennoch Konvertierungsschlüsselwörter wie z. B. `CStr` und [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), welche direkt den [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] , die Konvertierung auszuführen.  
  
> [!NOTE]
>  Der einschränkende Konvertierung-Fehler unterdrückt für Konvertierungen aus den Elementen in einem `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable. Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" in [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Einschränkende Konvertierung Schutz  
 Der Nachteil der einschränkende Konvertierungen ist, dass sie zur Laufzeit fehlschlagen können. Z. B. wenn ein `String` Variable enthält alle Elemente außer "True" oder "False", um ungültiges `Boolean`. Wenn es sich um Satzzeichen enthält, schlägt fehl Konvertierung in alle numerischen Typen. Es sei denn, Sie wissen, dass Ihre `String` Variable enthält immer die Werte, der der Zieltyp akzeptieren kann, Sie sollten nicht versuchen, eine Konvertierung.  
  
 Konvertieren von muss `String` in einen anderen Datentyp, ist am sichersten, die Konvertierung in den [testen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Dadurch können Sie den Umgang mit einem Laufzeitfehler.  
  
### <a name="character-arrays"></a>Zeichenarrays  
 Ein einzelnes `Char` und ein Array von `Char` Elemente, die sowohl zu erweitert `String`. Allerdings `String` ist nicht zu erweitert `Char()`. Konvertiert eine `String` Wert eine `Char` Array ist, können Sie die <xref:System.String.ToCharArray%2A> -Methode der der <xref:System.String?displayProperty=nameWithType> Klasse.  
  
### <a name="meaningless-values"></a>Bedeutungslose Werte  
 Im allgemeinen `String` Werte sind ohne Bedeutung in andere Datentypen, und eine Konvertierung ist hochgradig theoretisch angelegt ist und gefährlich. Wann immer möglich, beschränken Sie die Verwendung von `String` Variablen auf die Zeichenfolgen, die für die sie entworfen werden. Sie sollten nie Code schreiben, die entsprechenden Werte in anderen Projekttypen verwendet.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
