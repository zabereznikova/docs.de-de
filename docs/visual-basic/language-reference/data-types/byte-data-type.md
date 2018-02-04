---
title: Byte-Datentyp (Visual Basic)
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02234afc0dc51a2c1338cdd16d1f97765f64b45e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="byte-data-type-visual-basic"></a>Byte-Datentyp (Visual Basic)
Enthält die 8-Bit (1-Byte)-Ganzzahlen ohne Vorzeichen, die im Wert von 0 bis 255 liegen.

## <a name="remarks"></a>Hinweise

Verwenden der `Byte` -Datentyp, um Binärdaten enthalten.  
  
Der Standardwert von `Byte` lautet 0.

## <a name="literal-assignments"></a>Literal Zuweisungen

Sie können deklarieren und Initialisieren einer `Byte` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal. Ganzzahlige Literal ist außerhalb des Bereichs von einer `Byte` (d. h., wenn es ist kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Byte.MaxValue?displayProperty=nameWithType>), tritt ein Kompilierungsfehler auf.

Im folgenden Beispiel Ganzzahlen 201, die als dezimale, hexadezimale, dargestellt sind gleich und binäre Literale werden implizit konvertiert, aus [Ganzzahl](integer-data-type.md) zu `byte` Werte.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern. Zum Beispiel:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Tipps für die Programmierung

-   **Negative Zahlen.** Da `Byte` ein Typ ohne Vorzeichen ist es nicht darstellen kann eine negative Zahl. Bei Verwendung der unäres minus (`-`) Operator auf einen Ausdruck, der ausgewertet wird, um geben `Byte`, konvertiert den Ausdruck, der Visual Basic `Short` erste.
  
-   **Konvertierung des Formats.** Wenn Sie Visual Basic liest oder schreibt Dateien oder beim Aufrufen von DLLs, Methoden und Eigenschaften, können sie automatisch zwischen Datenformate konvertieren. Binäre Daten, die in gespeicherten `Byte` Variablen und Arrays werden solche Konvertierungen Format beibehalten. Verwenden Sie keine `String` Variable für binäre Daten, da der Inhalt bei der Konvertierung zwischen ANSI- und Unicode-Formaten beschädigt werden können.

-   **Widening.** Die `Byte` -Datentyp zu `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, oder `Double`. Dies bedeutet, Sie können konvertieren `Byte` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.
  
-   **Typzeichen.** `Byte`hat kein literal-Typzeichen oder Bezeichner-Typzeichen.

-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel `b` ist eine `Byte` Variable. Die Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung Bitschiebeoperatoren darauf.

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>Siehe auch

 <xref:System.Byte?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
