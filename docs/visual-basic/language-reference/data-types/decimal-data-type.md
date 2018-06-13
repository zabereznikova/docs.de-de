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
ms.openlocfilehash: 9e256e93d7857c8674a1d711fa9cafd3ed9a29f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591618"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal-Datentyp (Visual Basic)
Speichert signierte 128-Bit (16-Byte)-Werte, die ganze Zahl (12-Byte) der 96-Bit-Zahlen mit einer Variablen Potenz von 10 skaliert darstellt. Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. Es reicht von 0 bis 28. Mit einer Skala von 0 (keine Dezimalstellen), ist der größtmögliche Wert +/-Wert 79,228,162,514,264,337,593,543,950,335 (+/-7 .9228162514264337593543950335E + 28). Klicken Sie mit 28 Dezimalstellen +/-7,9228162514264337593543950335 und der Höchstwert ist, und den kleinsten Wert ungleich NULL ist, +/-0,0000000000000000000000000001 (+/-1E-28).  
  
## <a name="remarks"></a>Hinweise  
 Die `Decimal` -Datentyp bietet die größte Anzahl von signifikanten Stellen für eine Zahl. Es unterstützt bis zu 29 signifikanten Stellen und Werte oberhalb 7,9228 x 10 darstellen kann ^ 28. Sie eignet sich besonders für Berechnungen, z. B. Finanzen, die eine große Anzahl von Ziffern erfordern jedoch Rundungsfehler tolerieren kann nicht.  
  
 Der Standardwert von `Decimal` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Mit einfacher Genauigkeit.** `Decimal` ist kein Typ Gleitkommadaten. Die `Decimal` Struktur enthält einen binären ganzzahligen Wert zusammen mit einem Vorzeichenbit und eine ganze Zahl Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist. Aus diesem Grund `Decimal` Zahlen haben eine feiner abgestimmte Darstellung im Arbeitsspeicher als Gleitkommatypen (`Single` und `Double`).  
  
-   **Leistung:** Die `Decimal` -Datentyp ist der langsamste aller numerischen Typen. Wägen Sie die Wichtigkeit der Genauigkeit gegenüber der Leistung aufzufordern, einen Datentyp auf.  
  
-   **Widening.** Die `Decimal` -Datentyp zu `Single` oder `Double`. Dies bedeutet, Sie können konvertieren `Decimal` zu diesen Typen, ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
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
  
     D1 = 2.375, d2 = 1.625, d3 = 4.000 d4 = 4  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.  
  
## <a name="range"></a>Bereich  
 Müssen Sie möglicherweise verwenden Sie die `D` -Typzeichen weisen einen hohen Wert ein, um eine `Decimal` Variable oder Konstante. Diese Anforderung ist, da der Compiler als Literal interpretiert `Long` , wenn ein literal-Typzeichen wie im folgenden Beispiel gezeigt das Literal folgt.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 Die Deklaration für `bigDec1` Überlauf keine erzeugt werden, da der Wert, der ihm zugewiesenen innerhalb des Bereichs liegt `Long`. Die `Long` Wert zugewiesen werden kann, um die `Decimal` Variable.  
  
 Die Deklaration für `bigDec2` einen Überlauffehler generiert, weil der Wert, der ihm zugewiesen ist zu groß für `Long`. Da die numerische Literale zuerst als interpretiert werden kann ein `Long`, er kann nicht zugewiesen werden die `Decimal` Variable.  
  
 Für `bigDec3`, des Literaltypzeichens `D` löst das Problem durch den Compiler, das Literal als interpretieren Erzwingen einer `Decimal` statt als ein `Long`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
