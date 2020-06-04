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
ms.openlocfilehash: 690c8061b6df1115aa24668520170b44edfa8287
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415646"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal-Datentyp (Visual Basic)

Speichert signierte 128-Bit-Werte (16-Byte-Werte), die ganze 96-Bit-Zahlen (12-Byte-Zahlen) darstellen, die mit einer variablen Potenz von 10 skaliert sind. Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. der Bereich reicht von 0 bis 28. Bei einer Skala von 0 (keine Dezimalstellen) ist der größte mögliche Wert +/-337 (+/-7.9228162514264337593543950335E + 28). Bei 28 Dezimalstellen ist der größte Wert +/-7.9228162514264337593543950335, und der kleinste Wert ungleich 0 (null) ist +/-0,0000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Bemerkungen

Der- `Decimal` Datentyp bietet die größte Anzahl von signifikanten Ziffern für eine Zahl. Sie unterstützt bis zu 29 signifikante Ziffern und kann Werte über 7,9228 x 10 ^ 28 darstellen. Sie eignet sich besonders für Berechnungen, z. b. Finanz Weise, die eine große Anzahl von Ziffern erfordern, aber keine Rundungsfehler tolerieren können.

Der Standardwert von `Decimal` lautet 0.

## <a name="programming-tips"></a>Programmiertipps

- **Präziser.** `Decimal`ist kein Gleit Komma Datentyp. Die- `Decimal` Struktur enthält einen binären ganzzahligen Wert, sowie ein Vorzeichen-Bit und einen ganzzahligen Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimal Bruch ist. Aus diesem Grund `Decimal` weisen Zahlen eine präzisere Darstellung im Arbeitsspeicher auf als Gleit Komma Typen ( `Single` und `Double` ).

- **Leistung:** Der- `Decimal` Datentyp ist der langsamste Wert aller numerischen Typen. Vor dem Auswählen eines Datentyps sollten Sie die Wichtigkeit der Genauigkeit vor der Leistung abwägen.

- **Tet.** Der- `Decimal` Datentyp wird zu `Single` oder erweitert `Double` . Dies bedeutet, dass Sie `Decimal` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.

- **Nachfolgende Nullen.** In Visual Basic werden nachfolgende Nullen nicht in einem `Decimal` Literalformat gespeichert. Allerdings `Decimal` behält eine Variable alle nachfolgenden Nullen bei, die rechnerisch abgerufen wurden. Dies wird anhand des folgenden Beispiels veranschaulicht.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  Die Ausgabe von `MsgBox` im vorherigen Beispiel lautet wie folgt:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.

## <a name="range"></a>Range

 Möglicherweise müssen Sie das `D` Typzeichen verwenden, um einer Variablen oder Konstanten einen großen Wert zuzuweisen `Decimal` . Diese Anforderung liegt daran, dass der Compiler ein Literalzeichen als interpretiert `Long` , es sei denn, ein Literaltypzeichen folgt dem Literalen, wie im folgenden Beispiel gezeigt

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

Die Deklaration für `bigDec1` erzeugt keinen Überlauf, da der zugewiesene Wert innerhalb des Bereichs für liegt `Long` . Der `Long` Wert kann der Variablen zugewiesen werden `Decimal` .

Die-Deklaration für `bigDec2` generiert einen Überlauf Fehler, da der zugewiesene Wert für zu groß ist `Long` . Da das numerische Literale nicht als erstes interpretiert werden kann `Long` , kann es der Variablen nicht zugewiesen werden `Decimal` .

Für `bigDec3` löst das Literaltypzeichen `D` das Problem, indem der Compiler gezwungen wird, das Literale `Decimal` als anstelle von als zu interpretieren `Long` .

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Single-Datentyp](single-data-type.md)
- [Double-Datentyp](double-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
