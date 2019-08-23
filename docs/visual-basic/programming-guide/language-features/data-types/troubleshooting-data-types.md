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
ms.openlocfilehash: 5b2cb0d5270b7e14c3462aeaf54942f939511fd7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933234"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Problembehandlung bei Datentypen (Visual Basic)
Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die bei der Ausführung von Vorgängen für systeminterne Datentypen auftreten können.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Gleit Komma Ausdrücke vergleichen nicht als gleich.  
 Beachten Sie beim Arbeiten mit Gleit Komma Zahlen ([einzelner Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) und [Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)-Datentyp), dass Sie als binäre Bruchteile gespeichert werden. Dies bedeutet, dass Sie keine genaue Darstellung einer Menge enthalten können, die kein binärer Bruch ist (in Form von k/(2 ^ n), wobei k und n ganze Zahlen sind). Beispielsweise können 0,5 (= 1/2) und 0,3125 (= 5/16) als genaue Werte gehalten werden, wohingegen 0,2 (= 1/5) und 0,3 (= 3/10) nur Näherungen darstellen können.  
  
 Aufgrund dieser Ungenauigkeit können Sie sich nicht auf exakte Ergebnisse verlassen, wenn Sie Gleit Komma Werte verarbeiten. Insbesondere können zwei Werte, die theoretisch gleich sind, leicht unterschiedliche Darstellungen aufweisen.  
  
| So vergleichen Sie Gleit Komma Mengen | 
|---| 
|1.  Berechnen Sie den absoluten Wert Ihres Unterschieds, indem <xref:System.Math.Abs%2A> Sie die- <xref:System.Math> Methode der- <xref:System> Klasse im-Namespace verwenden.<br />2.  Bestimmen Sie einen zulässigen maximalen Unterschied, sodass Sie die zwei Mengen für praktische Zwecke als gleich betrachtet werden können, wenn Ihr Unterschied nicht größer ist.<br />3.  Vergleichen Sie den absoluten Wert der Differenz mit dem zulässigen Unterschied.|  
  
 Im folgenden Beispiel wird ein falscher und korrekter Vergleich von `Double` zwei Werten veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]  
  
 Im vorherigen Beispiel wird die <xref:System.Double.ToString%2A> -Methode <xref:System.Double> der-Struktur verwendet, sodass Sie eine bessere Genauigkeit angeben `CStr` kann als das-Schlüsselwort verwendet. Der Standardwert ist 15 Ziffern, aber das Format "G17" erweitert ihn auf 17 Ziffern.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Der Mod-Operator gibt kein genaues Ergebnis zurück.  
 Aufgrund der Ungenauigkeit der Gleit Komma Speicherung kann der mod- [Operator](../../../../visual-basic/language-reference/operators/mod-operator.md) ein unerwartetes Ergebnis zurückgeben, wenn mindestens einer der Operanden ein Gleit Komma Wert ist.  
  
 Der [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) verwendet keine Gleit Komma Darstellung. Viele Zahlen, die in `Single` und `Double` ungenau sind, sind in `Decimal` genau (z. b. 0,2 und 0,3). Obwohl die Arithmetik in `Decimal` langsamer ist als bei Gleit Komma, kann es sinnvoll sein, die Leistung zu verringern, um eine bessere Genauigkeit zu erzielen.  
  
|So ermitteln Sie den ganzzahligen Rest von Gleit Komma Mengen|  
|---|  
|1.  Deklarieren Sie `Decimal`Variablen als.<br />2.  Verwenden Sie das Literaltypzeichen `D` , um Literale für zu `Decimal`erzwingen, falls ihre Werte für den `Long` Datentyp zu groß sind.|  
  
 Im folgenden Beispiel wird die mögliche Ungenauigkeit von Gleit Komma Operanden veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]  
  
 Im vorherigen Beispiel wird die <xref:System.Double.ToString%2A> -Methode <xref:System.Double> der-Struktur verwendet, sodass Sie eine bessere Genauigkeit angeben `CStr` kann als das-Schlüsselwort verwendet. Der Standardwert ist 15 Ziffern, aber das Format "G17" erweitert ihn auf 17 Ziffern.  
  
 Da `zeroPointTwo`den Wert hat,istderWertfür0,2einunendlichwiederholterbinärerBruchteilmiteinemgespeichertenWertvon0.20000000000000001.`Double` Die Division von 2,0 durch diese Menge ergibt 9.9999999999999995 mit einem Rest von 0.19999999999999991.  
  
 Im Ausdruck für `decimalRemainder`erzwingt das Literaltypzeichen `D` beide Operanden zu `Decimal`, und 0,2 hat eine genaue Darstellung. Daher ergibt `Mod` der Operator den erwarteten Rest 0,0.  
  
 Beachten Sie, dass es nicht ausreicht, `decimalRemainder` als `Decimal`zu deklarieren. Außerdem müssen Sie die `Decimal`Literale in erzwingen oder standardmäßig verwenden `Double` und `decimalRemainder` erhalten denselben ungenauen Wert wie `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Der boolesche Typ wird nicht exakt in den numerischen Typ konvertiert.  
 [Boolesche Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sind nicht als äquivalent zu zahlen vorgesehen. Aus Gründen der Kompatibilität mit früheren Versionen bietet Visual Basic Konvertierungs Schlüsselwörter ( `CBool`[CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md),, `CInt`usw.) `Boolean` , um zwischen und numerischen Typen zu konvertieren. In anderen Sprachen werden diese Konvertierungen jedoch manchmal anders durchgeführt, ebenso wie die .NET Framework Methoden.  
  
 Sie sollten niemals Code schreiben, der auf äquivalenten numerischen `True` Werten `False`für und basiert. Wenn möglich, sollten Sie die Verwendung von `Boolean` Variablen auf die logischen Werte beschränken, für die Sie entworfen wurden. Wenn Sie `Boolean` und numerische Werte kombinieren müssen, stellen Sie sicher, dass Sie die von Ihnen gewählte Konvertierungsmethode verstehen.  
  
### <a name="conversion-in-visual-basic"></a>Konvertierung in Visual Basic  
 Wenn Sie `CType` die Konvertierungs `CBool` Schlüsselwörter oder verwenden, um numerische `Boolean`Datentypen in `False` zu konvertieren, wird 0 `True`zu, und alle anderen Werte werden. Wenn Sie Werte `Boolean` mithilfe der Konvertierungs Schlüsselwörter in numerische Typen `False` konvertieren, wird `True` 0 und wird zu-1.  
  
### <a name="conversion-in-the-framework"></a>Konvertierung im Framework  
 Die <xref:System.Convert.ToInt32%2A> -Methode <xref:System.Convert> der-Klasse im <xref:System> -Namespace `True` wird in + 1 konvertiert.  
  
 Wenn Sie einen `Boolean` Wert in einen numerischen Datentyp konvertieren müssen, achten Sie darauf, welche Konvertierungsmethode Sie verwenden.  
  
## <a name="character-literal-generates-compiler-error"></a>Zeichen Literale generiert Compilerfehler  
 Wenn keine Typzeichen vorhanden sind, wird Visual Basic von Standard Datentypen für Literale ausgegangen. Der Standardtyp für ein Zeichenliteral–, das`" "`in Anführungszeichen `String`() eingeschlossen ist – ist.  
  
 Der `String` -Datentyp wird nicht in den [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)erweitert. Dies bedeutet Folgendes: Wenn Sie einer `Char` Variablen ein Literalzeichen zuweisen möchten, müssen Sie entweder eine einschränkende Konvertierung vornehmen oder das Literale für den `Char` Typ erzwingen.  

|So erstellen Sie ein Char-wahrsten, das einer Variablen oder Konstanten zugewiesen werden soll|
|---|  
|1.  Deklarieren Sie die Variable oder `Char`Konstante als.<br />2.  Schließen Sie den Zeichen Wert in Anführungszeichen (`" "`) ein.<br />3.  Befolgen Sie das schließende doppelte Anführungszeichen mit dem Literaltypzeichen `C` , um das Literale zu `Char`erzwingen. Dies ist erforderlich, wenn der Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) lautet `On`und in jedem Fall wünschenswert ist.|  
  
 Im folgenden Beispiel werden sowohl fehlgeschlagene als auch erfolgreiche Zuweisungen eines Literals zu einer `Char` Variablen veranschaulicht.  
  
 [!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]  
  
 Einschränkende Konvertierungen bestehen immer aus Risiken, da Sie zur Laufzeit fehlschlagen können. Beispielsweise kann eine Konvertierung von `String` in `Char` fehlschlagen, wenn `String` der Wert mehr als ein Zeichen enthält. Daher ist es besser, das `C` Typzeichen zu verwenden.  
  
## <a name="string-conversion-fails-at-run-time"></a>Zeichen folgen Konvertierung schlägt zur Laufzeit fehl  
 Der [Zeichen folgen-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) ist an sehr wenigen erweiternden Konvertierungen beteiligt. `String`wird nur auf sich selbst und `Object`, und nur `Char` und `Char()` (ein `Char` -Array) `String`erweitert. Dies liegt daran `String` , dass Variablen und Konstanten Werte enthalten können, die andere Datentypen nicht enthalten können.  
  
 Wenn der Schalter für die Typüberprüfung ([Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)- `On`Anweisung) ist, lässt der Compiler nicht alle impliziten einschränkenden Konvertierungen zu. Dies umfasst auch die `String`, die betreffen. In Ihrem Code können weiterhin Konvertierungs Schlüsselwörter verwendet werden, wie z `CStr` . b. die-und die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), die die .NET Framework zum Versuch  
  
> [!NOTE]
> Der einschränkende Konvertierungs Fehler wird für Konvertierungen von Elementen in einer `For Each…Next` Auflistung in die Schleifen Steuerungs Variable unterdrückt. Weitere Informationen und Beispiele finden Sie im Abschnitt "einschränkende Konvertierungen" unter [for each... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Einschränkende Konvertierungs Schutz  
 Der Nachteil von einschränkenden Konvertierungen besteht darin, dass Sie zur Laufzeit einen Fehler verursachen können. Wenn eine `String` Variable beispielsweise etwas anderes als "true" oder "false" enthält, kann Sie nicht in `Boolean`konvertiert werden. Wenn Sie Interpunktions Zeichen enthält, schlägt die Konvertierung in einen beliebigen numerischen Typ fehl. Wenn Sie nicht wissen, `String` dass die Variable immer Werte enthält, die der Zieltyp annehmen kann, sollten Sie keine Konvertierung versuchen.  
  
 Wenn Sie von `String` in einen anderen Datentyp konvertieren müssen, besteht das sicherste Verfahren darin, die versuchte Konvertierung in das [try... Catch... Abschließend-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Dies ermöglicht es Ihnen, einen Laufzeitfehler zu behandeln.  
  
### <a name="character-arrays"></a>Zeichen Arrays  
 Ein einzelnes `Char` und ein Array von `Char` -Elementen werden in `String`erweitert. Allerdings wird nicht zu `Char()`erweitert. `String` Wenn Sie einen `String` -Wert in `Char` ein-Array konvertieren möchten, <xref:System.String.ToCharArray%2A> können Sie die <xref:System.String?displayProperty=nameWithType> -Methode der-Klasse verwenden.  
  
### <a name="meaningless-values"></a>Bedeutungslose Werte  
 Im allgemeinen `String` sind Werte in anderen Datentypen nicht von Bedeutung, und die Konvertierung ist hochgradig künstlich und gefährlich. Wenn möglich, sollten Sie die Verwendung von `String` Variablen auf die Zeichen folgen beschränken, für die Sie entworfen wurden. Sie sollten niemals Code schreiben, der auf äquivalenten Werten in anderen Typen basiert.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
