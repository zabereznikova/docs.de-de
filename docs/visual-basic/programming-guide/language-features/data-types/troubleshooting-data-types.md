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
ms.openlocfilehash: c5ff9d097c0660956a9751a23511d8273766227c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655784"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Problembehandlung bei Datentypen (Visual Basic)
Auf dieser Seite sind einige allgemeine Probleme, die beim Ausführen von Vorgängen für systeminterne Datentypen auftreten können.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Gleitkomma-Ausdrücke vergleichen nicht gleichwertig  
 Beim Arbeiten mit Gleitkommazahlen ([Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) und [Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md)), denken Sie daran, dass sie als binäre Brüche gespeichert werden. Dies bedeutet, sie können keine genaue Darstellung der Menge, die nicht Binärbruch enthalten (im Format k / (2 ^ n), auf dem k "und" n "sind ganze Zahlen). Beispielsweise können 0,5 (= 1/2) und 0,3125 (= 5/16) als präzise Werte gespeichert werden, während 0,2 (= 1/5) und 0,3 (= 3/10) nur Näherungswerte sein können.  
  
 Aus diesem Grund können nicht Ungenauigkeit, Sie genaue Ergebnisse hängen bei Gleitkommazahlen-Punktwerte bearbeitet werden. Insbesondere möglicherweise zwei Werte, die theoretisch gleich sind etwas anderen Darstellungen bereit.  
  
| Zu vergleichenden Gleitkommazahlen Mengen | 
|---| 
|1.  Berechnen Sie den absoluten Wert des ihrer Differenz mithilfe der <xref:System.Math.Abs%2A> Methode der <xref:System.Math> -Klasse in der <xref:System> Namespace.<br />2.  Bestimmen Sie, dass Sie werden, die zwei Mengen aus praktischen Gründen gleich sein berücksichtigt können, wenn ihre Unterschied nicht größer ist als eine zulässige maximale Abweichung.<br />3.  Vergleichen Sie den absoluten Wert des Unterschieds auf den zulässigen Unterschied.|  
  
 Das folgende Beispiel veranschaulicht die falschen und richtigen Vergleich von zwei `Double` Werte.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 Im vorherigen Beispiel wird die <xref:System.Double.ToString%2A> Methode der <xref:System.Double> strukturieren, sodass er eine größere Genauigkeit als angeben kann die `CStr` -Schlüsselwort verwendet. Der Standardwert ist 15 Dezimalstellen, aber das Format "G17" erweitert sie 17 Ziffern.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod-Operator gibt keine exakte Ergebnis zurück.  
 Aufgrund der Ungenauigkeit der Gleitkomma-Speicher der [Mod Operator](../../../../visual-basic/language-reference/operators/mod-operator.md) kann ein unerwartetes Ergebnis zurückgeben, wenn mindestens einer der Operanden ein Gleitkomma ist.  
  
 Die [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) gleitkommadarstellung nicht verwendet. Viele Zahlen, die ungenau sind `Single` und `Double` genau in `Decimal` (z. B. 0,2 und 0,3). Obwohl arithmetische langsamer `Decimal` als in Gleitkommazahlen, es möglicherweise wiegt die geringere Leistung erzielen Sie bessere Genauigkeit.  
  
|Um den ganzzahligen Rest einer Gleitkommazahl Mengen suchen|  
|---|  
|1.  Deklarieren Sie Variablen als `Decimal`.<br />2.  Verwenden des Literaltypzeichens `D` gezwungen Literale `Decimal`, für den Fall, dass ihre Werte zu groß für werden die `Long` -Datentyp.|  
  
 Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 Im vorherigen Beispiel wird die <xref:System.Double.ToString%2A> Methode der <xref:System.Double> strukturieren, sodass er eine größere Genauigkeit als angeben kann die `CStr` -Schlüsselwort verwendet. Der Standardwert ist 15 Dezimalstellen, aber das Format "G17" erweitert sie 17 Ziffern.  
  
 Da `zeroPointTwo` ist `Double`, seinen Wert für die 0,2 ist ein unendlicher Binärbruch mit dem gespeicherten Wert 0,20000000000000001. 2.0 durch diese Menge dividiert ergibt 9,9999999999999995 mit dem Rest des 0,19999999999999991.  
  
 In den Ausdruck für `decimalRemainder`, dem literal-Typzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 verfügt über eine genaue Darstellung. Aus diesem Grund die `Mod` -Operator liefert den erwarteten Rest 0,0.  
  
 Beachten Sie, dass es nicht ausreichend, um deklarieren `decimalRemainder` als `Decimal`. Sie müssen auch erzwingen, die Literale `Decimal`, oder verwenden sie `Double` standardmäßig und `decimalRemainder` empfängt ungenauen denselben Wert wie `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Boolean-Typ konvertiert nicht numerischen Typs korrekt  
 [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte dürfen nicht mit Zahlen gleichwertig sein. Um die Kompatibilität mit früheren Versionen, Visual Basic bietet Konvertierungsschlüsselwörter ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`usw.) zum Konvertieren zwischen `Boolean` und numerischen Typen. Allerdings anderssprachige manchmal nur unzureichende diese Konvertierungen wie unterschiedlich die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Methoden.  
  
 Schreiben Sie Code, der auf den entsprechenden numerischen Werten für nutzt `True` und `False`. Wann immer möglich, beschränken Sie die Verwendung von `Boolean` Variablen, die für sie vorgesehenen logischen Werte. Wenn Sie kombinieren müssen `Boolean` und numerische Werte, stellen Sie sicher, dass Sie die Konvertierungsmethode verstehen, die Sie auswählen.  
  
### <a name="conversion-in-visual-basic"></a>Konvertieren in Visual Basic  
 Bei Verwendung der `CType` oder `CBool` Konvertierungsschlüsselwörter Konvertieren von numerischen Datentypen in `Boolean`, wird 0 `False` und alle anderen Werte werden `True`. Bei der Konvertierung `Boolean` Werte in numerische Typen mithilfe der Konvertierungsschlüsselwörter `False` wird 0 und `True` wird – 1.  
  
### <a name="conversion-in-the-framework"></a>Konvertierung in das Framework  
 Die <xref:System.Convert.ToInt32%2A> Methode der <xref:System.Convert> -Klasse in der <xref:System> Namespace konvertiert `True` auf + 1.  
  
 Nach dem konvertieren müssen eine `Boolean` -Wert in einen numerischen Datentyp aufweisen, seien Sie vorsichtig Konvertierungsmethode, die Sie verwenden.  
  
## <a name="character-literal-generates-compiler-error"></a>Zeichenliterale generiert Compilerfehler  
 In Ermangelung Typzeichen Standarddatentypen Visual Basic für Literale. Der Standardtyp für ein Zeichenliteral – in Anführungszeichen eingeschlossen (`" "`) – wird `String`.  
  
 Die `String` Datentyp wird nicht erweitert werden, um die [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md). Dies bedeutet, dass, wenn Sie ein Literal zuweisen möchten eine `Char` -Variable verwenden, müssen Sie eine einschränkende Konvertierung vornehmen oder erzwingen Sie das Literal für die `Char` Typ.  

|Char zuweisen zu einer Variablen oder Konstanten Literalen erstellen|
|---|  
|1.  Deklarieren Sie die Variable oder Konstante als `Char`.<br />2.  Den Zeichenwert in Anführungszeichen setzen (`" "`).<br />3.  Führen Sie das schließende Anführungszeichen mit dem literal-Typzeichen `C` zu erzwingen, das Literal für `Char`. Dies ist erforderlich, wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On`, und es ist in jedem Fall wünschenswert.|  
  
 Das folgende Beispiel zeigt sowohl erfolgreiche als auch nicht erfolgreiche Zuweisungen von ein Literal ein `Char` Variable.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Es ist immer ein Risiko einschränkende Konvertierungen mit da zur Laufzeit ausgeführt werden kann. Angenommen, eine Konvertierung von `String` auf `Char` kann fehlschlagen, wenn die `String` Wert mehr als ein Zeichen enthält. Ist daher eine bessere Leistung mit Programmierung der `C` Zeichen eingeben.  
  
## <a name="string-conversion-fails-at-run-time"></a>Zeichenfolgenkonvertierung schlägt fehl, zur Laufzeit  
 Die [Zeichenfolgendatentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) nur sehr wenige erweiterungskonvertierungen beteiligt. `String` nur auf sich selbst erweitert und `Object`, und nur `Char` und `Char()` (eine `Char` Array) erweitert werden, um `String`. Grund hierfür ist, `String` Variablen und Konstanten können Werte enthalten, die andere Datentypen enthalten können.  
  
 Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On`, der Compiler lässt alle implizite einschränkende Konvertierungen. Dies schließt die im Zusammenhang mit `String`. Den Code Konvertierungsschlüsselwörter wie z. B. verwenden `CStr` und [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), welche Direct die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] , die Konvertierung auszuführen.  
  
> [!NOTE]
>  Die einschränkende Konvertierung Fehler unterdrückt für Konvertierungen von den Elementen in einem `For Each…Next` -Auflistung, um die Loop-Steuerelementvariable. Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Einschränkende Konvertierung Schutz  
 Der Nachteil der einschränkende Konvertierungen ist, dass zur Laufzeit ausgeführt werden kann. Z. B. wenn ein `String` Variable enthält alles andere als "True" oder "Falsch", es in konvertiert werden kann `Boolean`. Wenn es Satzzeichen enthält, schlägt fehl, Konvertierung in einen numerischen Typ. Es sei denn, Sie wissen, dass Ihre `String` Variable enthält immer die Werte, der der Zieltyp akzeptieren kann, Sie sollten nicht versuchen, eine Konvertierung.  
  
 Konvertieren von muss `String` in einen anderen Datentyp ist am sichersten, schließen Sie die Konvertierung in den [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Dadurch können Sie einen Laufzeitfehler zu verarbeiten.  
  
### <a name="character-arrays"></a>Zeichenarrays  
 Ein einzelnes `Char` und ein Array von `Char` Elemente sowohl erweitert, um werden `String`. Allerdings `String` wird nicht erweitert werden, um `Char()`. Konvertieren einer `String` -Wert an ein `Char` Array ist, können Sie die <xref:System.String.ToCharArray%2A> Methode der <xref:System.String?displayProperty=nameWithType> Klasse.  
  
### <a name="meaningless-values"></a>Bedeutungslose Werte  
 Im allgemeinen `String` Werte sind ohne Bedeutung in andere Datentypen und Konvertierung ist nur künstliche und sehr gefährlich. Wann immer möglich, beschränken Sie die Verwendung von `String` Variablen, die für sie vorgesehenen Zeichensequenzen. Sie sollten nie Code schreiben, der entsprechende Werte in anderen Projekttypen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
