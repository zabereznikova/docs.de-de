---
title: Byte-Datentyp (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b106005ff07f55e05ae66dba94041cd8b5c24bb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482297"
---
# <a name="byte-data-type-visual-basic"></a>Byte-Datentyp (Visual Basic)
Enthält die 8-Bit (1-Byte)-Ganzzahlen ohne Vorzeichen, die im Wert von 0 bis 255 liegen.

## <a name="remarks"></a>Hinweise

Verwenden der `Byte` -Datentyp, um binäre Daten enthalten.  
  
Der Standardwert von `Byte` lautet 0.

## <a name="literal-assignments"></a>Zuweisung von literalen

Sie können deklarieren und initialisieren eine `Byte` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal. Ganzzahlige Literal ist außerhalb des Bereichs von einer `Byte` (d. h., wenn es ist kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Byte.MaxValue?displayProperty=nameWithType>), tritt ein Kompilierungsfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 201 hat, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden implizit konvertiert, von [Ganzzahl](integer-data-type.md) zu `byte` Werte.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern. Zum Beispiel:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Tipps für die Programmierung

-   **Negative Zahlen.** Da `Byte` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen. Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `Byte`, konvertiert den Ausdruck, der Visual Basic `Short` erste.
  
-   **Format-Konvertierungen.** Wenn Visual Basic liest oder schreibt Dateien oder beim Aufrufen von DLLs, Methoden und Eigenschaften, können sie automatisch zwischen den Datenformaten konvertieren. Binäre Daten, die in `Byte` Variablen und Arrays während solche Konvertierungen Format beibehalten wird. Verwenden Sie keine `String` Variablen, um binäre Daten verwenden, da der Inhalt während der Konvertierung zwischen ANSI- und Unicode-Formaten beschädigt werden können.

-   **Erweiternde.** Die `Byte` -Datentyp wird zu `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, oder `Double`. Dies bedeutet, Sie können konvertieren `Byte` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.
  
-   **Typzeichen.** `Byte` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.

-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel `b` ist eine `Byte` Variable. Den Bereich der Variablen und die Anwendung von Bitschiebeoperatoren, führen Sie die Anweisungen vor.

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>Siehe auch

 <xref:System.Byte?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
