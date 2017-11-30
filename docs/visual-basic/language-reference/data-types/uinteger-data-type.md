---
title: UInteger-Datentyp
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
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
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a>UInteger-Datentyp

Enthält 32-Bit (4-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 4.294.967.295.  
  
## <a name="remarks"></a>Hinweise

 Die `UInteger` -Datentyp stellt den größten Wert ohne Vorzeichen in die effizienteste Datenbreite bereit.  
  
 Der Standardwert von `UInteger` lautet 0.  
  
## <a name="literal-assignments"></a>Literal Zuweisungen

Sie können deklarieren und Initialisieren einer `UInteger` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

Numerische Literale zählen auch die `UI` oder `ui` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `UInteger` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a>Tipps für die Programmierung

 Die `UInteger` und `Integer` Datentypen bereitstellen auf einem 32-Bit-Prozessor eine optimale Leistung, weil die kleineren ganzzahlige Typen (`UShort`, `Short`, `Byte`, und `SByte`), auch wenn sie weniger Bits verwendet mehr Zeit in Anspruch nehmen Laden, speichern und abrufen.  
  
-   **Negative Zahlen.** Da `UInteger` ein Typ ohne Vorzeichen ist es nicht darstellen kann eine negative Zahl. Bei Verwendung der unäres minus (`-`) Operator auf einen Ausdruck, der ausgewertet wird, um geben `UInteger`, konvertiert den Ausdruck, der Visual Basic `Long` erste.  
  
-   **CLS-Kompatibilität.** Die `UInteger` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, die verwendet werden.
  
-   **Interop-Überlegungen.** Wenn Sie Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen Datenbreite bedenken, die von wie z. B. Typen `uint` in anderen Umgebungen können eine andere Datenbreite (16 Bits) vorhanden sein. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` im verwalteten Visual Basic-Code.  
  
-   **Widening.** Die `UInteger` -Datentyp zu `Long`, `ULong`, `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `UInteger` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Typzeichen.** Anhängen des Literaltypzeichens `UI` an ein Literal wird der `UInteger` -Datentyp. `UInteger`verfügt über keine Typkennzeichen aus.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.UInt32>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
