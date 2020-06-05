---
title: Byte-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 97acd1bc2ff29bac6588216b9ee4a4f187078815
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374316"
---
# <a name="byte-data-type-visual-basic"></a>Byte-Datentyp (Visual Basic)

Enthält ganzzahlige 8-Bit-Zahlen (1 Byte) ohne Vorzeichen, die einen Wert zwischen 0 und 255 enthalten.

## <a name="remarks"></a>Bemerkungen

Verwenden Sie den- `Byte` Datentyp, um Binärdaten zu enthalten.  
  
Der Standardwert von `Byte` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine Variable deklarieren und initialisieren, `Byte` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn sich das ganzzahlige Literale außerhalb des Bereichs von befindet (d. h `Byte` ., wenn es kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als ist <xref:System.Byte.MaxValue?displayProperty=nameWithType> ), tritt ein Kompilierungsfehler auf.

Im folgenden Beispiel werden ganze Zahlen gleich 201, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, implizit von [ganzzahligen](integer-data-type.md) Werten in- `byte` Werte konvertiert.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** Da `Byte` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus ( `-` )-Operator für einen Ausdruck verwenden, der den Typ ergibt `Byte` , konvertiert Visual Basic den Ausdruck in den `Short` ersten.
  
- **Format Konvertierungen.** Wenn Visual Basic Dateien liest oder schreibt oder DLLs, Methoden und Eigenschaften aufruft, kann es automatisch zwischen Datenformaten konvertiert werden. Binärdaten, die in Variablen und Arrays gespeichert werden, werden `Byte` bei solchen Formatkonvertierungen beibehalten. Sie sollten keine `String` Variable für binäre Daten verwenden, da der Inhalt während der Konvertierung zwischen ANSI-und Unicode-Formaten beschädigt werden kann.

- **Tet.** Der- `Byte` Datentyp wird zu `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` oder erweitert `Double` . Dies bedeutet `Byte` , dass Sie in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.
  
- **Geben Sie Zeichen ein.** `Byte`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel `b` ist eine `Byte` Variable. Die-Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung von BitShift-Operatoren.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Byte?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
