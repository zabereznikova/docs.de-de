---
title: Byte-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401352"
---
# <a name="byte-data-type-visual-basic"></a>Byte-Datentyp (Visual Basic)

Enthält ganze Ganzzahlen mit nicht signierten 8-Bit-Dateien (1 Byte), die einen Wert von 0 bis 255 aufweisen.

## <a name="remarks"></a>Bemerkungen

Verwenden `Byte` Sie den Datentyp, um Binärdaten zu enthalten.  
  
Der Standardwert von `Byte` lautet 0.

## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `Byte` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen. Wenn sich das integrale Literal `Byte` außerhalb des Bereichs von <xref:System.Byte.MinValue?displayProperty=nameWithType> a <xref:System.Byte.MaxValue?displayProperty=nameWithType>befindet (d. h., wenn es kleiner oder größer als ist ), tritt ein Kompilierungsfehler auf.

Im folgenden Beispiel werden ganzzahlige Zahlen gleich 201, die als Dezimal-, Hexadezimal- und `byte` Binärliterale dargestellt werden, implizit von [Ganzzahl](integer-data-type.md) in Werte konvertiert.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** Da `Byte` es sich um einen nicht signierten Typ handelt, kann er keine negative Zahl darstellen. Wenn Sie den Operator`-`unary minus ( ) für `Byte`einen Ausdruck verwenden, `Short` der als Typ ausgewertet wird, konvertiert Visual Basic den Ausdruck in den ersten.
  
- **Formatkonvertierungen.** Wenn Visual Basic Dateien liest oder schreibt oder DLLs, Methoden und Eigenschaften aufruft, kann es automatisch zwischen Datenformaten konvertieren. Binäre Daten, die in `Byte` Variablen und Arrays gespeichert sind, werden während solcher Formatkonvertierungen beibehalten. Sie sollten keine `String` Variable für Binärdaten verwenden, da derInhalt während der Konvertierung zwischen ANSI- und Unicode-Formaten beschädigt werden kann.

- **Erweiterung.** Der `Byte` Datentyp wird `Short` `UShort`auf `Integer` `UInteger`, `Long` `ULong`, `Decimal` `Single`, `Double`, , , , , , oder erweitert. Dies bedeutet, `Byte` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.
  
- **Typ Zeichen.** `Byte`hat kein Literaltypzeichen oder Bezeichnertypzeichen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel `b` ist `Byte` eine Variable. Die Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung von Bitshift-Operatoren darauf.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Byte?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
