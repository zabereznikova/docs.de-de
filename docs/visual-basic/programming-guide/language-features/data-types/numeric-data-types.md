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
ms.openlocfilehash: 75e60cb2a3a934956099ce6fc7d81bf6ecea4d11
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841640"
---
# <a name="numeric-data-types-visual-basic"></a>Numerische Datentypen (Visual Basic)
Visual Basic bietet mehrere *numerische Datentypen* für die Behandlung von Zahlen in verschiedenen Darstellungen bereit. *Ganzzahlige* Typen darstellen, nur ganze Zahlen (Positive und negative und 0 (null)), und *Nonintegral* Typen stellen die Zahlen mit Nachkommastellen und ganze Zahl dar.  
  
 Eine Tabelle mit dem ein Vergleich der Seite-an-Seite der Visual Basic-Datentypen finden Sie [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Ganzzahlige numerische Typen  
 *Ganzzahlige Datentypen* sind diejenigen, die nur Zahlen ohne Sekundenbruchteile darstellen.  
  
 Die *signiert* ganzzahlige Datentypen sind [SByte-Datentyp](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-Bit), [Short-Datentyp](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-Bit), [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-Bit), und [ Long-Datentyp](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-Bit). Wenn eine Variable immer Ganzzahlen anstelle von Bruchzahlen speichert, deklarieren Sie ihn als einen dieser Typen.  
  
 Die *ohne Vorzeichen* Ganzzahltypen sind [Byte-Datentyp](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-Bit), [UShort-Datentyp](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-Bit), [UInteger-Datentyp](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-Bit), und [ ULong-Datentyp](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-Bit). Wenn eine Variable binäre Daten oder Daten unbekannten Typs enthält, deklarieren Sie ihn als einen dieser Typen.  
  
### <a name="performance"></a>Leistung  
 Arithmetische Operationen sind schneller mit ganzzahligen Typen als mit anderen Datentypen. Am schnellsten mit werden die `Integer` und `UInteger` Typen in Visual Basic.  
  
### <a name="large-integers"></a>Große ganze Zahlen  
 Wenn Sie eine ganze Zahl größer als halten müssen die `Integer` -Datentyp enthalten kann, können Sie mit der `Long` Datentyp stattdessen. `Long` Variablen können Zahlen zwischen -9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 enthalten. Vorgänge mit `Long` sind etwas langsamer als bei `Integer`.  
  
 Wenn Sie noch größere Werten benötigen, können Sie die [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Sie können Zahlen von 79.228.162.514.264.337.593.543.950.335 bis 79.228.162.514.264.337.593.543.950.335 in enthalten eine `Decimal` Variable, wenn Sie Dezimalstellen nicht verwendet werden. Allerdings Vorgänge mit `Decimal` Zahlen sind erheblich langsamer als bei einem beliebigen anderen numerischen Datentyp.  
  
### <a name="small-integers"></a>Integer-Werten mit  
 Wenn Sie nicht, dass das gesamte Spektrum benötigen der `Integer` Datentyp aufweisen, können Sie die `Short` -Datentyp, der ganze Zahlen von-32.768 bis 32.767 enthalten kann. Für den kleinsten Integer-Bereich der `SByte` Datentyp enthält ganze Zahlen von-128 bis 127. Wenn Sie eine sehr große Anzahl von Variablen, die kleinen ganzen Zahlen verfügen, wird die common Language Runtime kann manchmal speichern Ihre `Short` und `SByte` Variablen effizienter und Arbeitsspeicher belegt. Allerdings Vorgänge mit `Short` und `SByte` sind etwas langsamer als bei `Integer`.  
  
### <a name="unsigned-integers"></a>Ganze Zahlen ohne Vorzeichen  
 Wenn Sie wissen, dass die Variable muss nie eine negative Zahl enthalten, können Sie mit der *Typen ohne Vorzeichen*`Byte`, `UShort`, `UInteger`, und `ULong`. Jeder dieser Datentypen kann eine positive ganze Zahl doppelt so groß, als das entsprechende Typ signiert enthalten (`SByte`, `Short`, `Integer`, und `Long`). Im Hinblick auf die Leistung zu erzielen ist jeder Typ ohne Vorzeichen genauso leistungsstark wie der entsprechende Typ mit Vorzeichen. Insbesondere `UInteger` teilt mit `Integer` den Unterschied der effizienteste aller elementaren numerischen Datentypen.  
  
## <a name="nonintegral-numeric-types"></a>Nicht ganzzahlige numerische Typen  
 *Nicht ganzzahlige Datentypen* sind diejenigen, die Zahlen mit Nachkommastellen und ganze Zahl darstellen.  
  
 Nicht ganzzahlige numerische Datentypen `Decimal` (128-Bit-festen Punkt), [Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-Bit-Gleitkommazahl), und [Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-Bit-Gleitkomma). Sie sind alle signierten Typen. Wenn eine Variable einen Bruch enthalten kann, deklarieren Sie ihn als einen dieser Typen.  
  
 `Decimal` ist kein Gleitkomma-Datentyp. `Decimal` Zahlen haben einen binären ganzzahligen Wert und eine ganze Zahl-Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist.  
  
 Sie können `Decimal` Variablen für Money-Werte. Der Vorteil ist die Genauigkeit der Werte. Die `Double` -Datentyp ist schneller und weniger Speicher benötigt, aber er Rundungsfehler unterliegt. Die `Decimal` Datentyp behält die vollständige Genauigkeit von bis zu 28 Dezimalstellen.  
  
 Gleitkomma (`Single` und `Double`) Zahlen haben größere Bereiche als `Decimal` Zahlen, jedoch können Rundungsfehler unterliegen. Gleitkomma-Datentypen unterstützt weniger signifikante Ziffern als `Decimal` aber können größere Werte darstellen.  
  
 Nicht ganzzahlige in ausgedrückt werden können als MmmEeee mmm wird die *Mantisse* (die signifikante Stellen) und Eee ist die *Exponent* (eine Potenz von 10). Die höchste positive Werte nicht ganzzahligen Datentypen sind 7.9228162514264337593543950335E + 28 für `Decimal`, 3,4028235E + 38 für `Single`, und 1.79769313486231570E + 308 für `Double`.  
  
### <a name="performance"></a>Leistung  
 `Double` ist der effizienteste Datentyp mit Nachkommastellen, da die Prozessoren auf den aktuellen Plattformen Operationen mit Gleitkommazahlen mit doppelter Genauigkeit ausführen. Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.  
  
### <a name="small-magnitudes"></a>Kleine Größenordnungen  
 Für Zahlen mit der kleinsten möglichen Größe (nahe 0) `Double` können Variablen Zahlen so klein wie - 4.94065645841246544E-324 bei negativen Werten und 4.94065645841246544E-324 für positive Werte.  
  
### <a name="small-fractional-numbers"></a>Kleine Bruchzahlen  
 Wenn Sie nicht, dass das gesamte Spektrum benötigen der `Double` Datentyp aufweisen, können Sie die `Single` -Datentyp, der Gleitkommazahlen von - 3,4028235E + 38 bis 3,4028235E + 38 enthalten kann. Die kleinsten Werte für `Single` Variablen sind - 1.401298E-45, bei negativen Werten und 1.401298E-45 für positive Werte. Wenn Sie eine sehr große Anzahl von Variablen, die kleine Gleitkommazahlen enthalten verfügen, wird die common Language Runtime kann manchmal speichern Ihre `Single` Variablen effizienter und Arbeitsspeicher belegt.  
  
## <a name="see-also"></a>Siehe auch

- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Sonstige Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
