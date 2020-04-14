---
title: Decimal-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243322"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal-Datentyp (Visual Basic)

Speichert signierte 128-Bit-Werte (16-Byte-Werte), die ganze 96-Bit-Zahlen (12-Byte-Zahlen) darstellen, die mit einer variablen Potenz von 10 skaliert sind. Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. sie reicht von 0 bis 28. Bei einer Skala von 0 (keine Dezimalstellen) ist der größtmögliche Wert +/-79,228,162,514,264,337,593,543,950,335 (+/-7.92281625142643375935439503355E+28). Mit 28 Dezimalstellen ist der größte Wert +/-7.92281625142643375935439503335, und der kleinste Wert ungleich Null ist +/-0.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000

## <a name="remarks"></a>Bemerkungen

Der `Decimal` Datentyp stellt die größte Anzahl signifikanter Ziffern für eine Zahl bereit. Es unterstützt bis zu 29 signifikante Ziffern und kann Werte von mehr als 7,9228 x 10 x 28 darstellen. Es eignet sich besonders für Berechnungen, wie z. B. finanzielle, die eine große Anzahl von Ziffern erfordern, aber Rundungsfehler nicht tolerieren können.

Der Standardwert von `Decimal` lautet 0.

## <a name="programming-tips"></a>Programmiertipps

- **Präzision.** `Decimal`ist kein Gleitkommadatentyp. Die `Decimal` Struktur enthält einen binären Ganzzahlwert zusammen mit einem Vorzeichenbit und einem ganzzahligen Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist. Aus diesem `Decimal` Grund haben Zahlen eine genauere Darstellung im`Single` `Double`Speicher als Gleitkommatypen ( und ).

- **Leistung.** Der `Decimal` Datentyp ist der langsamste aller numerischen Typen. Sie sollten die Bedeutung der Genauigkeit gegen die Leistung abwägen, bevor Sie einen Datentyp auswählen.

- **Erweiterung.** Der `Decimal` Datentyp wird `Single` `Double`auf oder erweitert. Dies bedeutet, `Decimal` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne dass ein Fehler auftritt.

- **Trailing Zeros.** Visual Basic speichert keine nachgestellten `Decimal` Nullen in einem Literal. Eine `Decimal` Variable behält jedoch alle nachgestellten Nullen bei, die rechnerisch erfasst wurden. Dies wird anhand des folgenden Beispiels veranschaulicht.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  Die Ausgabe `MsgBox` im vorherigen Beispiel ist wie folgt:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Typ Zeichen.** Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.

## <a name="range"></a>Bereich

 Möglicherweise müssen Sie `D` das Typzeichen verwenden, um `Decimal` einer Variablen oder Konstante einen großen Wert zuzuweisen. Diese Anforderung liegt daran, dass `Long` der Compiler ein Literal so interpretiert, dass ein Literaltypzeichen nicht dem Literal folgt, wie das folgende Beispiel zeigt.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

Die Deklaration für `bigDec1` erzeugt keinen Überlauf, da der ihm zugewiesene `Long`Wert innerhalb des Bereichs für liegt. Der `Long` Wert kann der `Decimal` Variablen zugewiesen werden.

Die Deklaration für `bigDec2` generiert einen Überlauffehler, da der `Long`ihm zugewiesene Wert für zu groß ist. Da das numerische Literal nicht zuerst `Long`als eine interpretiert werden kann, kann es der `Decimal` Variablen nicht zugewiesen werden.

Für `bigDec3`löst das `D` Literaltypzeichen das Problem, indem es den `Decimal` Compiler zwingt, das Literal als a und nicht als `Long`zu interpretieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
