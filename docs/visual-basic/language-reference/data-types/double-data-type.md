---
title: Double-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 92adb26702d94dee08e51decd845d019c797e195
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630096"
---
# <a name="double-data-type-visual-basic"></a>Double-Datentyp (Visual Basic)

Enthält signierte IEEE 64-Bit (8-Byte)-Gleit Komma Zahlen mit doppelter Genauigkeit, die den Wert from-1.79769313486231570 e + 308 bis-4.94065645841246544 e-324 für negative Werte und von 4.94065645841246544 e-324 bis 1.79769313486231570 e + 308 für positive Werte. Zahlen mit doppelter Genauigkeit speichern eine Näherung einer reellen Zahl.

## <a name="remarks"></a>Hinweise

Der `Double` -Datentyp bietet die größte und kleinste mögliche Vergrößerung für eine Zahl.

Der Standardwert von `Double` lautet 0.

## <a name="programming-tips"></a>Programmiertipps

- **Präziser.** Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bei bestimmten Vorgängen führen, wie z. b. `Mod` Werte Vergleich und Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

- **Nachfolgende Nullen.** Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden NULL-Zeichen. Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2. Folglich werden nachfolgende NULL-Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.

- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`-Datentyp erzwungen. Wenn z. b. auf einen ganzzahligen `R`Wert folgt, wird der Wert in `Double`einen geändert.

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`-Datentyp erzwungen. Im folgenden Beispiel wird die-Variable `num` `Double`als typisiert:

  ```vb
  Dim num# = 3
  ```

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.Double?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
