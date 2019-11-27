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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344076"
---
# <a name="byte-data-type-visual-basic"></a>Byte-Datentyp (Visual Basic)

Enthält ganzzahlige 8-Bit-Zahlen (1 Byte) ohne Vorzeichen, die einen Wert zwischen 0 und 255 enthalten.

## <a name="remarks"></a>Hinweise

Verwenden Sie den `Byte`-Datentyp, um Binärdaten zu enthalten.  
  
Der Standardwert von `Byte` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine `Byte` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn das ganzzahlige Literale außerhalb des Bereichs einer `Byte` liegt (d. h., wenn es kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Byte.MaxValue?displayProperty=nameWithType>ist), tritt ein Kompilierungsfehler auf.

Im folgenden Beispiel werden ganze Zahlen, die gleich 201 sind und als Dezimal-, hexadezimale und binäre Literale dargestellt werden, implizit von einer [Ganzzahl](integer-data-type.md) in `byte` Werte konvertiert.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** Da `Byte` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `Byte`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Short`.
  
- **Format Konvertierungen.** Wenn Visual Basic Dateien liest oder schreibt oder DLLs, Methoden und Eigenschaften aufruft, kann es automatisch zwischen Datenformaten konvertiert werden. Binärdaten, die in `Byte` Variablen und Arrays gespeichert werden, werden bei solchen Formatkonvertierungen beibehalten. Sie sollten keine `String` Variable für binäre Daten verwenden, da der Inhalt während der Konvertierung zwischen ANSI-und Unicode-Formaten beschädigt werden kann.

- **Tet.** Der `Byte`-Datentyp wird auf `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`oder `Double`erweitert. Dies bedeutet, dass Sie `Byte` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.
  
- **Geben Sie Zeichen ein.** `Byte` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel ist `b` eine `Byte` Variable. Die-Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung von BitShift-Operatoren.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Siehe auch

- <xref:System.Byte?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
