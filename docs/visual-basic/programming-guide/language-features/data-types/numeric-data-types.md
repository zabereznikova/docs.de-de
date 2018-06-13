---
title: Numerische Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
ms.openlocfilehash: 8fa88172c9914a071e1b24e959c9030e6d219a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654202"
---
# <a name="numeric-data-types-visual-basic"></a>Numerische Datentypen (Visual Basic)
Visual Basic stellt mehrere *numerische Datentypen* für die Behandlung von Zahlen in verschiedenen Darstellungen bereit. *Ganzzahlige* Typen darstellen, nur ganze Zahlen (Positive und negative und 0 (null)), und *Nonintegral* Typen darstellen von Zahlen mit Nachkommastellen und ganze Zahl.  
  
 Eine Tabelle mit einer Seite-an-Seite-Vergleich der Visual Basic-Datentypen, finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="integral-numeric-types"></a>Ganzzahlige numerische Typen  
 *Ganzzahlige Datentypen* sind solche, die nur Zahlen ohne Nachkommastellen darstellen.  
  
 Die *signiert* ganzzahlige Datentypen sind [SByte-Datentyp](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-Bit), [Short-Datentyp](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-Bit), [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-Bit) und [ Long-Datentyp](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-Bit). Wenn eine Variable Ganzzahlen anstelle von Brüchen speichert, deklarieren Sie sie als einen dieser Typen.  
  
 Die *ohne Vorzeichen* ganzzahlige Typen sind [Byte-Datentyp](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-Bit), [UShort-Datentyp](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-Bit), [UInteger-Datentyp](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-Bit) und [ ULong-Datentyp](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-Bit). Wenn eine Variable binäre Daten, oder unbekannten Typs enthält, deklarieren Sie sie als einen dieser Typen an.  
  
### <a name="performance"></a>Leistung  
 Arithmetische Operationen sind mit Ganzzahltypen mit anderen Datentypen als schneller. Am schnellsten mit werden die `Integer` und `UInteger` Typen in Visual Basic.  
  
### <a name="large-integers"></a>Große ganze Zahlen  
 Wenn Sie eine ganze Zahl größer als halten müssen die `Integer` Datentyp aufnehmen kann, können Sie mithilfe der `Long` Datentyp stattdessen. `Long` Variablen können Zahlen von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 enthalten. Vorgänge mit `Long` sind etwas langsamer als bei `Integer`.  
  
 Wenn Sie noch größere Werte benötigen, können Sie die [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Sie können Zahlen von-79.228.162.514.264.337.593.543.950.335 bis Wert 79,228,162,514,264,337,593,543,950,335 in enthalten eine `Decimal` Variable, wenn Sie Dezimalstellen nicht verwendet werden. Allerdings Vorgänge mit `Decimal` Zahlen sind erheblich langsamer als bei einem beliebigen anderen numerischen Datentyp.  
  
### <a name="small-integers"></a>Integer-Werten  
 Wenn Sie nicht das gesamte Spektrum der benötigen die `Integer` -Datentyp, können Sie die `Short` -Datentyp, der ganze Zahlen von-32.768 bis 32.767 enthalten kann. Für den kleinsten Integer-Bereich der `SByte` -Datentyp enthält ganze Zahlen von-128 bis 127. Haben eine sehr große Anzahl von Variablen, die small Integers enthalten, kann in einigen Fällen die common Language Runtime speichern Ihre `Short` und `SByte` Variablen effizienter und Arbeitsspeicher belegt. Allerdings Vorgänge mit `Short` und `SByte` sind etwas langsamer als bei `Integer`.  
  
### <a name="unsigned-integers"></a>Ganzzahlen ohne Vorzeichen  
 Wenn Sie wissen, dass die Variable muss nie eine negative Zahl aufnehmen, können Sie mithilfe der *Typen ohne Vorzeichen*`Byte`, `UShort`, `UInteger`, und `ULong`. Jeder dieser Datentypen kann eine positive ganze Zahl zweimal so groß wie dem entsprechenden Typ einen signierten enthalten (`SByte`, `Short`, `Integer`, und `Long`). Im Hinblick auf Leistung ist jeder Typ ohne Vorzeichen genau so effizient wie der entsprechende Datentyp mit Vorzeichen. Insbesondere `UInteger` teilt mit `Integer` die Unterscheidung der effizienteste aller elementaren numerischen Datentypen.  
  
## <a name="nonintegral-numeric-types"></a>Nicht ganzzahlige numerische Typen  
 *Nicht ganzzahlige Datentypen* sind diejenigen, die Zahlen mit Nachkommastellen und ganze Zahl darstellen.  
  
 Die nicht integrale numerische Datentypen sind `Decimal` (128-Bit-Festkommazahl) [Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-Bit-Gleitkommazahl), und [Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-Bit-Gleitkommazahl). Sie sind alle signierten Typen. Wenn eine Variable einen Bruch enthalten kann, deklarieren Sie sie als einen dieser Typen an.  
  
 `Decimal` ist kein Typ Gleitkommadaten. `Decimal` Zahlen haben einen binären ganzzahligen Wert und eine ganze Zahl Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist.  
  
 Sie können `Decimal` Variablen für Währungswerte. Der Vorteil ist die Genauigkeit der Werte. Die `Double` -Datentyp ist schneller und weniger Speicher benötigt, aber es Rundungsfehler unterliegt. Die `Decimal` Datentyp behält vollständige Genauigkeit mit 28 Dezimalstellen an.  
  
 Gleitkomma (`Single` und `Double`) Zahlen haben größere Bereiche als `Decimal` Zahlen aber unterliegen Rundungsfehler werden können. Gleitkommatypen unterstützen weniger signifikante Ziffern als `Decimal` aber größere Werte darstellen können.  
  
 Nicht ganzzahlige in ausgedrückt werden können als MmmEeee mmm also die *Mantisse* (die signifikante Stellen) und Eee ist die *Exponenten* (eine Potenz von 10). Die höchste positive Werte die Ganzzahltypen sind 7.9228162514264337593543950335E + 28 für `Decimal`, 3,4028235E + 38 für `Single`, und 1.79769313486231570E + 308 für `Double`.  
  
### <a name="performance"></a>Leistung  
 `Double` ist der effizienteste die Datentypen mit Nachkommastellen, da die Prozessoren auf den aktuellen Plattformen Operationen mit Gleitkommazahlen mit doppelter Genauigkeit ausführen. Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.  
  
### <a name="small-magnitudes"></a>Kleine Magnituden  
 Zahlen mit der kleinstmöglichen Größe (nahe 0) `Double` können Variablen Zahlen so klein wie - 4.94065645841246544E-324 für negative Werte und 4.94065645841246544E-324 für positive Werte zulässig sind.  
  
### <a name="small-fractional-numbers"></a>Kleine Bruchzahlen  
 Wenn Sie nicht das gesamte Spektrum der benötigen die `Double` -Datentyp, können Sie die `Single` -Datentyp, der Gleitkommazahlen von - 3,4028235E + 38 bis 3,4028235E + 38 aufnehmen kann. Die kleinsten Werte für `Single` Variablen sind - 1.401298E-45 für negative Werte und 1.401298E-45 für positive Werte zulässig sind. Haben eine sehr große Anzahl von Variablen, die kleine Gleitkommazahlen enthalten, kann in einigen Fällen die common Language Runtime speichern Ihre `Single` Variablen effizienter und Arbeitsspeicher belegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Sonstige Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
