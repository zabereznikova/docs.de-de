---
title: Numerische Datentypen
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
ms.openlocfilehash: 72cdca295e209935687f67ad290e816775d9fe13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393675"
---
# <a name="numeric-data-types-visual-basic"></a>Numerische Datentypen (Visual Basic)
Visual Basic stellt mehrere *numerische Datentypen* für die Verarbeitung von Zahlen in verschiedenen Darstellungen bereit. Ganzzahlige Typen stellen nur ganze Zahlen dar (positiv, negativ und null), und *nicht* ganzzahlige *Typen stellen* Zahlen mit ganzzahligen und Bruchteilen dar.  
  
 Eine Tabelle, die einen parallelen Vergleich der Visual Basic-Datentypen anzeigt, finden Sie unter [Datentypen](../../../language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Ganzzahlige numerische Typen  
 Ganzzahlige *Datentypen* sind solche, die nur Zahlen ohne Bruchteile darstellen.  
  
 Die *signed* [ganzzahligen](../../../language-reference/data-types/integer-data-type.md) Datentypen mit Vorzeichen sind [SByte-Datentyp](../../../language-reference/data-types/sbyte-data-type.md) (8-Bit), [Short-Datentyp](../../../language-reference/data-types/short-data-type.md) (16-Bit), Integer-Datentyp (32 Bit) und [Long-Datentyp](../../../language-reference/data-types/long-data-type.md) (64 Bit). Wenn eine Variable immer ganze Zahlen und keine Bruchzahlen speichert, deklarieren Sie Sie als einen dieser Typen.  
  
 Die ganzzahligen Typen *ohne* Vorzeichen sind [Byte-Datentyp](../../../language-reference/data-types/byte-data-type.md) (8-Bit), [UShort-Datentyp](../../../language-reference/data-types/ushort-data-type.md) (16-Bit), [UInteger-Datentyp](../../../language-reference/data-types/uinteger-data-type.md) (32 Bit) und [ULong-Datentyp](../../../language-reference/data-types/ulong-data-type.md) (64 Bit). Wenn eine Variable Binärdaten oder Daten unbekannter Natur enthält, deklarieren Sie Sie als einen dieser Typen.  
  
### <a name="performance"></a>Leistung  
 Arithmetische Operationen sind bei ganzzahligen Typen schneller als bei anderen Datentypen. Sie sind am schnellsten mit `Integer` den `UInteger` Typen und in Visual Basic.  
  
### <a name="large-integers"></a>Große ganze Zahlen  
 Wenn Sie eine ganze Zahl speichern müssen, die größer `Integer` ist, als der Datentyp enthalten kann, können Sie stattdessen den- `Long` Datentyp verwenden. `Long`Variablen können Zahlen von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 enthalten. Vorgänge mit `Long` sind etwas langsamer als mit `Integer` .  
  
 Wenn Sie noch größere Werte benötigen, können Sie den [Decimal-Datentyp](../../../language-reference/data-types/decimal-data-type.md)verwenden. Sie können Zahlen von 337 bis 337 in einer Variablen speichern, `Decimal` Wenn Sie keine Dezimalstellen verwenden. Vorgänge mit `Decimal` Zahlen sind jedoch deutlich langsamer als bei einem anderen numerischen Datentyp.  
  
### <a name="small-integers"></a>Kleine ganze Zahlen  
 Wenn Sie nicht den vollständigen Bereich des `Integer` Datentyps benötigen, können Sie den `Short` -Datentyp verwenden, der ganzzahlige Werte von-32.768 bis 32.767 enthalten kann. Für den kleinsten ganzzahligen Bereich `SByte` enthält der Datentyp ganze Zahlen von-128 bis 127. Wenn Sie über eine sehr große Anzahl von Variablen verfügen, die kleine ganze Zahlen enthalten, können die Common Language Runtime manchmal Ihre `Short` -und-Variablen effizienter speichern `SByte` und den Speicherverbrauch verbrauchen. Vorgänge mit `Short` und sind jedoch `SByte` etwas langsamer als mit `Integer` .  
  
### <a name="unsigned-integers"></a>Ganze Zahlen ohne Vorzeichen  
 Wenn Sie wissen, dass die Variable nie eine negative Zahl enthalten muss, können Sie die *unsignierten Typen* `Byte` , `UShort` , `UInteger` und verwenden `ULong` . Jeder dieser Datentypen kann eine positive Ganzzahl doppelt so groß wie der entsprechende signierte Typ ( `SByte` , `Short` , `Integer` und `Long` ) enthalten. Im Hinblick auf die Leistung ist jeder nicht signierte Typ genau so effizient wie der zugehörige signierte Typ. Insbesondere gibt es die `UInteger` `Integer` Unterscheidung zwischen allen elementaren numerischen Datentypen.  
  
## <a name="nonintegral-numeric-types"></a>Nicht ganzzahlige numerische Typen  
 *Nicht integrale Datentypen* sind solche, die Zahlen mit ganzzahligen und Bruchteilen darstellen.  
  
 Die nicht ganzzahligen numerischen Datentypen sind `Decimal` (128-Bit-fester Punkt), [einzelner Datentyp](../../../language-reference/data-types/single-data-type.md) (32 Bit Gleit Komma) und [Double-Datentyp](../../../language-reference/data-types/double-data-type.md) (64-Bit-Gleit Komma Zahl). Sie sind alle signierte Typen. Wenn eine Variable einen Bruchteil enthalten kann, deklarieren Sie Sie als einen dieser Typen.  
  
 `Decimal`ist kein Gleit Komma Datentyp. `Decimal`Zahlen haben einen binären ganzzahligen Wert und einen ganzzahligen Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimal Bruch ist.  
  
 Sie können `Decimal` Variablen für Money-Werte verwenden. Der Vorteil ist die Genauigkeit der Werte. Der `Double` -Datentyp ist schneller und erfordert weniger Arbeitsspeicher, unterliegt jedoch Rundungsfehlern. Der- `Decimal` Datentyp behält die komplette Genauigkeit bei 28 Dezimalstellen bei.  
  
 Gleit Komma Zahlen ( `Single` und `Double` ) weisen größere Bereiche als `Decimal` Zahlen auf, können aber auch Rundungsfehler unterliegen. Gleit Komma Typen unterstützen weniger signifikante Ziffern als, `Decimal` können jedoch Werte höherer Größe darstellen.  
  
 Nicht ganzzahlige Zahlenwerte können als mmmeeee ausgedrückt werden, wobei MMM die *Mantisse* (die signifikanten Ziffern) und Eee der *Exponent* (eine Potenz von 10) ist. Die höchsten positiven Werte der nicht ganzzahligen Typen sind 7.9228162514264337593543950335 e + 28 für `Decimal` , 3.4028235 e + 38 für `Single` und 1.79769313486231570 e + 308 für `Double` .  
  
### <a name="performance"></a>Leistung  
 `Double`ist die effizienteste der Bruch Datentypen, da die Prozessoren auf aktuellen Plattformen Gleit Komma Vorgänge mit doppelter Genauigkeit ausführen. Vorgänge mit sind jedoch `Double` nicht so schnell wie bei den ganzzahligen Typen wie `Integer` .  
  
### <a name="small-magnitudes"></a>Kleine Größenordnungen  
 Für Zahlen mit der kleinsten möglichen Größe (die am nächsten 0 liegt) `Double` können Variablen Zahlen wie-4.94065645841246544 e-324 für negative Werte und 4.94065645841246544 e-324 für positive Werte enthalten.  
  
### <a name="small-fractional-numbers"></a>Kleine Bruchzahlen  
 Wenn Sie nicht den vollständigen Bereich des `Double` Datentyps benötigen, können Sie den `Single` -Datentyp verwenden, der Gleit Komma Zahlen von-3.4028235 e + 38 bis 3.4028235 e + 38 enthalten kann. Die kleinsten Größen für `Single` Variablen sind- -1 401298E e-45 für negative Werte und -1 401298E e-45 für positive Werte. Wenn Sie über eine sehr große Anzahl von Variablen verfügen, die kleine Gleit Komma Zahlen enthalten, können Sie die Variablen manchmal effizienter speichern und Common Language Runtime die Arbeits `Single` Speichernutzung einsparen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Elementare Datentypen](elementary-data-types.md)
- [Zeichendatentypen](character-data-types.md)
- [Sonstige Datentypen](miscellaneous-data-types.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
