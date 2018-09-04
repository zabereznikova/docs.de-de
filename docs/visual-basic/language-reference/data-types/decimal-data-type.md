---
title: Decimal-Datentyp (Visual Basic)
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
ms.openlocfilehash: ffc1cd141ba624d2ce26e4b1c070431ff0ddd6fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554931"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal-Datentyp (Visual Basic)
Speichert signierte 128-Bit (16-Byte)-Werte, die ganze Zahl (12-Byte) der 96-Bit-Zahlen mit einer Variablen Potenz von 10 skaliert darstellt. Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. Es reicht von 0 bis 28. Mit einer Skala von 0 (keine Dezimalstellen) an, der der größte mögliche Wert ist + / – 79.228.162.514.264.337.593.543.950.335 (+/-7 .9228162514264337593543950335E + 28). Der Höchstwert ist + / – 7,9228162514264337593543950335 mit 28 Dezimalstellen und der kleinste Wert ungleich NULL ist + / – 0,0000000000000000000000000001 (+/-1E-28).  
  
## <a name="remarks"></a>Hinweise  
 Die `Decimal` -Datentyp stellt die größte Anzahl von signifikanten Stellen für eine Reihe. Unterstützt bis zu 29 signifikanten Stellen und können darstellen Werte oberhalb 7,9228 x 10 ^ 28. Sie eignet sich besonders für Berechnungen wie Finanz-, erfordern eine große Anzahl von Ziffern, jedoch können keine Rundungsfehler tolerieren.  
  
 Der Standardwert von `Decimal` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Mit einfacher Genauigkeit.** `Decimal` ist kein Gleitkomma-Datentyp. Die `Decimal` Struktur enthält einen binäre Ganzzahl-Wert, zusammen mit einem Vorzeichenbit und eine ganze Zahl, die Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist. Aus diesem Grund `Decimal` Zahlen haben eine genauere Darstellung im Arbeitsspeicher als Gleitkomma-Datentypen (`Single` und `Double`).  
  
-   **Leistung:** Die `Decimal` -Datentyp ist der langsamste der alle numerischen Typen. Wägen Sie die Wichtigkeit der Genauigkeit und Leistung, bevor Sie einen Datentyp auswählen.  
  
-   **Erweiternde.** Die `Decimal` -Datentyp wird zu `Single` oder `Double`. Dies bedeutet, Sie können konvertieren `Decimal` zu diesen Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Nachfolgende Nullen.** Visual Basic speichert keine nachfolgende Nullen in einer `Decimal` literal. Allerdings eine `Decimal` Variablen werden beibehalten, nachfolgenden Nullen rechnerisch abgerufen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     Die Ausgabe des `MsgBox` im vorherigen Beispiel lautet wie folgt:  
  
     D1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.  
  
## <a name="range"></a>Bereich  
 Müssen Sie möglicherweise verwenden Sie die `D` Typzeichen, weisen einen hohen Wert auf eine `Decimal` Variable oder Konstante. Diese Anforderung ist, da der Compiler als Literal interpretiert `Long` , wenn ein literal-Typzeichen, das Literal, wie im folgenden Beispiel gezeigt folgt.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 Die Deklaration für `bigDec1` einen Überlauf nicht erzeugt werden, da der Wert, der ihm zugewiesenen innerhalb des Bereichs für liegt `Long`. Die `Long` Wert zugewiesen werden kann, um die `Decimal` Variable.  
  
 Die Deklaration für `bigDec2` einen Überlauffehler generiert, da der Wert, der ihm zugewiesen ist zu groß für ist `Long`. Da die numerische Literale zuerst als interpretiert werden kann eine `Long`, er kann nicht zugewiesen werden die `Decimal` Variable.  
  
 Für `bigDec3`, des Literaltypzeichens `D` löst das Problem, da der Compiler interpretiert das Literal als ein `Decimal` anstatt als eine `Long`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
