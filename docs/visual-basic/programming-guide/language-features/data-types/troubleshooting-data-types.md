---
title: Problembehandlung bei Datentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Char data type, converting
- Decimal data type, conversions
- data types [Visual Basic], troubleshooting
- literals, default types
- type characters, literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types
- floating-point numbers, precision
- Boolean data type, converting
- literal types
- literal type characters
- floating-point numbers, imprecision
- String data type, converting
- floating-point numbers, comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cfb8fc77d3e0d85ef795a94fc95ab61a8f68ff39
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-data-types-visual-basic"></a>Problembehandlung bei Datentypen (Visual Basic)
Diese Seite listet einige der häufigsten Probleme, die auftreten können, wenn Operationen mit systeminternen Datentypen ausgeführt.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Gleitkomma-Ausdrücke vergleichen nicht gleichwertig  
 Beim Arbeiten mit Gleitkommazahlen ([Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) und [Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md)), beachten Sie, dass sie als binäre Brüche gespeichert werden. Dies bedeutet, sie können keine genaue Darstellung der eine Menge, die nicht Binärbruch enthalten (im Format k / (2 ^ n), k und n sind ganze Zahlen). Beispielsweise können 0,5 (= 1/2) and 0,3125 (= 5/16) als präzise Werte gespeichert werden, während 0,2 (= 1/5) und 0,3 (= 3/10) nur Näherungswerte sein können.  
  
 Aus diesem Grund können nicht Ungenauigkeit, Sie genaue Ergebnisse abhängig, wenn Sie mit Gleitkommawerten arbeiten. Insbesondere möglicherweise zwei Werte, die theoretisch gleich sind etwas unterschiedlich dargestellt.  
  
| Zu vergleichenden Gleitkommazahlen Mengen | 
|---| 
|1.  Berechnen Sie den Absolutbetrag ihrer Differenz mithilfe der <xref:System.Math.Abs%2A>Methode der <xref:System.Math>-Klasse in die <xref:System>Namespace.</xref:System> </xref:System.Math> </xref:System.Math.Abs%2A><br />2.  Bestimmen Sie eine zulässige maximale Abweichung, die Sie berücksichtigen können die beiden Größen für praktische Zwecke gleich sein, sofern ihre Abweichung nicht größer ist.<br />3.  Vergleichen Sie den absoluten Wert des Unterschieds mit der zulässigen Abweichung.|  
  
 Das folgende Beispiel zeigt die falschen und richtigen Vergleich von zwei `Double` Werte.  
  
 [!code-vb[VbVbalrDataTypes&#10;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 Im vorhergehenden Beispiel wird die <xref:System.Double.ToString%2A>Methode der <xref:System.Double>so strukturieren, dass er eine größere Genauigkeit als angeben kann die `CStr` -Schlüsselwort verwendet.</xref:System.Double> </xref:System.Double.ToString%2A> Der Standardwert ist 15 Stellen, aber das Format "G17" erweitert ihn auf 17 Ziffern.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod-Operator gibt kein präzises Ergebnis zurück.  
 Aufgrund der Ungenauigkeit von Gleitkommazahlen die [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md) kann ein unerwartetes Ergebnis zurückgeben, wenn mindestens einer der Operanden eine Gleitkommazahl ist.  
  
 Die [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) gleitkommadarstellung wird nicht verwendet. Viele Zahlen, die ungenau sind `Single` und `Double` sind genau in `Decimal` (z. B. 0,2 und 0,3). Obwohl die Berechnung ist langsamer in `Decimal` als in Gleitkommazahlen es möglicherweise wiegt die geringere Leistung, größere Genauigkeit.  
  
|Um den ganzzahligen Rest Gleitkomma Mengen suchen|  
|---|  
|1.  Deklarieren Sie Variablen als `Decimal`.<br />2.  Verwenden Sie das Literalzeichen `D` erzwingen Literale `Decimal`für den Fall, dass ihre Werte für zu groß sind die `Long` -Datentyp.|  
  
 Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden.  
  
 [!code-vb[VbVbalrDataTypes&#11;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 Im vorhergehenden Beispiel wird die <xref:System.Double.ToString%2A>Methode der <xref:System.Double>so strukturieren, dass er eine größere Genauigkeit als angeben kann die `CStr` -Schlüsselwort verwendet.</xref:System.Double> </xref:System.Double.ToString%2A> Der Standardwert ist 15 Stellen, aber das Format "G17" erweitert ihn auf 17 Ziffern.  
  
 Da `zeroPointTwo` ist `Double`, sein Wert für 0,2 ein unendlicher Binärbruch mit dem gespeicherten Wert 0,20000000000000001 dargestellt wird. 2.0 durch diese Menge dividiert ergibt 9,9999999999999995 mit dem Rest des 0,19999999999999991.  
  
 Im Ausdruck für `decimalRemainder`, das Literalzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 wird präzise dargestellt. Aus diesem Grund die `Mod` -Operator liefert den erwarteten Rest 0,0.  
  
 Beachten Sie, dass es nicht ausreicht, deklarieren `decimalRemainder` als `Decimal`. Sie müssen außerdem die Literale erzwingen `Decimal`, oder sie verwenden `Double` standardmäßig und `decimalRemainder` empfängt ungenauen denselben Wert wie `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Boolean-Typ konvertiert nicht numerischen Typ korrekt  
 [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sollen nicht mit Zahlen gleichwertig sein. Für die Kompatibilität mit früheren Versionen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bietet Konvertierungsschlüsselwörter ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`usw.) zum Konvertieren zwischen `Boolean` und numerischen Typen. Andere Sprachen manchmal führen jedoch diese Konvertierungen wie unterschiedlich die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Methoden.  
  
 Sie sollten nie schreiben Code, der von entsprechenden numerischen Werten für beruht `True` und `False`. Wann immer möglich, beschränken Sie die Verwendung von `Boolean` Variablen auf die logischen Werte, für die sie entworfen werden. Wenn Sie kombinieren müssen `Boolean` und numerische Werte, stellen Sie sicher, dass Sie die Konvertierungsmethode verstehen, die Sie auswählen.  
  
### <a name="conversion-in-visual-basic"></a>Konvertieren in Visual Basic  
 Bei Verwendung der `CType` oder `CBool` Konvertierungsschlüsselwörter Konvertieren von numerischen Datentypen in `Boolean`, wird 0 `False` und alle anderen Werte werden `True`. Bei der Konvertierung `Boolean` Werte in numerische Typen mit den Konvertierungsschlüsselwörtern `False` wird 0 und `True` wird – 1.  
  
### <a name="conversion-in-the-framework"></a>Konvertierung in das Framework  
 Die <xref:System.Convert.ToInt32%2A>Methode der <xref:System.Convert>-Klasse in die <xref:System>Namespace konvertiert `True` bis +&1;.</xref:System> </xref:System.Convert> </xref:System.Convert.ToInt32%2A>  
  
 Wenn Sie konvertieren eine `Boolean` -Wert in einen numerischen Datentyp aufweisen, seien Sie vorsichtig Konvertierungsmethode, die Sie verwenden.  
  
## <a name="character-literal-generates-compiler-error"></a>Zeichenliteral generiert Compilerfehler.  
 In Ermangelung keine Typzeichen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Standarddatentypen für Literale. Der Standardtyp für ein Zeichenliteral – in Anführungszeichen eingeschlossen (`" "`) – ist `String`.  
  
 Die `String` Datentyp wird nicht erweitert werden, um die [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md). Dies bedeutet, dass, wenn Sie ein Literal zuweisen möchten eine `Char` Variablen, Sie stellen eine einschränkende Konvertierung, oder erzwingen Sie das Literal der `Char` Typ.  

|Eine char-Variable zuweisen zu einer Variablen oder Konstanten Literalen erstellen|
|---|  
|1.  Deklarieren Sie die Variable oder Konstante als `Char`.<br />2.  Schließen Sie den Zeichenwert in Anführungszeichen (`" "`).<br />3.  Führen Sie das schließende Anführungszeichen das Literaltypzeichen `C` zu erzwingen, dass das Literal `Char`. Dies ist erforderlich, wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On`, und es ist in jedem Fall wünschenswert.|  
  
 Das folgende Beispiel zeigt sowohl erfolgreiche als auch nicht erfolgreiche Zuweisungen von ein Literal eine `Char` Variable.  
  
 [!code-vb[VbVbalrDataTypes&#12;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Es besteht immer ein Risiko mit einschränkende Konvertierungen, da sie zur Laufzeit fehlschlagen können. Angenommen, eine Konvertierung von `String` auf `Char` kann fehlschlagen, wenn die `String` Wert mehr als ein Zeichen enthält. Es ist daher besser Programmiersprachen verwenden die `C` Zeichen eingeben.  
  
## <a name="string-conversion-fails-at-run-time"></a>Konvertierung zur Laufzeit fehlschlägt.  
 Die [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) nur sehr wenige erweiternde Konvertierungen beteiligt. `String`Erweitert die nur sich selbst und `Object`, und nur `Char` und `Char()` (eine `Char` Array) werden zu `String`. Grund hierfür ist, `String` Variablen und Konstanten können Werte enthalten, die andere Datentypen enthalten können.  
  
 Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On`, der Compiler lässt alle implizite einschränkende Konvertierungen. Dies gilt für die im Zusammenhang mit `String`. Code kann dennoch Konvertierungsschlüsselwörter wie z. B. `CStr` und [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), welche direkt den [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] , die Konvertierung auszuführen.  
  
> [!NOTE]
>  Der Fehler für einschränkende Konvertierung wird unterdrückt für Konvertierungen von den Elementen in einem `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable. Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" im [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Einschränkende Konvertierung Schutz  
 Der Nachteil der einschränkende Konvertierungen ist, dass sie zur Laufzeit fehlschlagen können. Z. B. wenn ein `String` Variable enthält alles andere als "True" oder "False", es konvertiert werden kann `Boolean`. Satzzeichen enthalten, schlägt fehl, die Konvertierung in einen beliebigen numerischen Typ. Es sei denn, Sie wissen, dass Ihre `String` Variable enthält immer die Werte, die der Zieltyp akzeptieren kann, Sie sollten nicht versuchen, eine Konvertierung.  
  
 Konvertieren von muss `String` in einen anderen Datentyp, ist am sichersten, die Konvertierung in den [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Dadurch können Sie den Umgang mit einem Laufzeitfehler.  
  
### <a name="character-arrays"></a>Zeichenarrays  
 Ein einzelnes `Char` und ein Array von `Char` Elemente sowohl zu erweitert `String`. Allerdings `String` wird nicht erweitert, um `Char()`. Konvertieren einer `String` -Wert in einen `Char` Array, können Sie die <xref:System.String.ToCharArray%2A>Methode der <xref:System.String?displayProperty=fullName>Klasse.</xref:System.String?displayProperty=fullName> </xref:System.String.ToCharArray%2A>  
  
### <a name="meaningless-values"></a>Bedeutungslose Werte  
 Im allgemeinen `String` Werte sind nicht in andere Datentypen sinnvoll, und eine Konvertierung ist nur künstliche und sehr gefährlich. Wann immer möglich, beschränken Sie die Verwendung von `String` Variablen auf die Zeichenfolgen, für die sie entworfen werden. Sie sollten nie Code schreiben, der von entsprechenden Werten in anderen Typen abhängt.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
