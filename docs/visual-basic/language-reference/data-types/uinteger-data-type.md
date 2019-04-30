---
title: UInteger-Datentyp (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: 4d93b1e40371b00f9d1ff69ec31ad0983beb493f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971729"
---
# <a name="uinteger-data-type"></a>UInteger-Datentyp

Enthält 32-Bit (4-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 4.294.967.295.  
  
## <a name="remarks"></a>Hinweise

 Die `UInteger` -Datentyp bietet den größten Wert ohne Vorzeichen in die Breite der effizienteste.  
  
 Der Standardwert von `UInteger` lautet 0.  
  
## <a name="literal-assignments"></a>Zuweisung von literalen

Sie können deklarieren und initialisieren eine `UInteger` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern. Zum Beispiel:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch einschließen, die `UI` oder `ui` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) zur Angabe der `UInteger` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Tipps für die Programmierung

 Die `UInteger` und `Integer` Datentypen auf einem 32-Bit-Prozessor, eine optimale Leistung bereit, da die kleineren ganzzahlige Typen (`UShort`, `Short`, `Byte`, und `SByte`), auch wenn sie weniger Bits verwendet mehr Zeit in Anspruch Laden, speichern und abrufen.  
  
- **Negative Zahlen.** Da `UInteger` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen. Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `UInteger`, konvertiert den Ausdruck, der Visual Basic `Long` erste.  
  
- **CLS-Kompatibilität.** Die `UInteger` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.
  
- **Interop-Überlegungen.** Wenn Sie anbinden, Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen müssen bedenken, die Typen wie `uint` haben eine andere Datenbreite (16 Bits) in anderen Umgebungen. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UShort` anstelle von `UInteger` in verwaltetem Visual Basic-Code.  
  
- **Erweiternde.** Die `UInteger` -Datentyp wird zu `Long`, `ULong`, `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `UInteger` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
- **Typzeichen.** Durch Anhängen des Literaltypzeichens `UI` an ein Literal wird der `UInteger` -Datentyp. `UInteger` verfügt über keine Typkennzeichen aus.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.UInt32>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
