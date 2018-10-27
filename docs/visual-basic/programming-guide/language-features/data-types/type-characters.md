---
title: Typzeichen (Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 1922282ece4dd90c8f55c8dea20ef2866d8b357c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181394"
---
# <a name="type-characters-visual-basic"></a>Typzeichen Sie (Visual Basic)

Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, Sie können den Datentyp der einige Programmierelemente mit Erzwingen einer *Typzeichen*. Das Typzeichen muss unmittelbar auf das Element, ohne jegliche Beteiligte Zeichen folgen.

Das Typzeichen ist nicht Teil des Namens des Elements. Ein Element mit einem Typzeichen definiert kann ohne das Typzeichen verwiesen werden.

## <a name="identifier-type-characters"></a>Typkennzeichen

Visual Basic stellt eine Reihe von *Typkennzeichen* , dass Sie in einer Deklaration verwenden können, um den Datentyp, der eine Variable oder Konstante angeben. Die folgende Tabelle zeigt die verfügbaren Typkennzeichen mit Beispielen für die Nutzung.
  
|Typkennzeichen|Datentyp|Beispiel|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Keine Bezeichner-Typzeichen vorhanden sind, für die `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort` Datentypen oder für ein Zusammengesetzte Datentypen wie z. B. Arrays oder Datenstrukturen.

In einigen Fällen können Sie Anfügen der `$` Zeichen auf eine Visual Basic-Funktion, z. B. `Left$` anstelle von `Left`, um einen Rückgabewert des Typs erhalten `String`.

In allen Fällen muss der Bezeichner-Typzeichen unmittelbar folgen für den Namen des Bezeichners.

## <a name="literal-type-characters"></a>Literaltypzeichen

Ein *literal* ist eine Textdarstellung eines bestimmten Werts einen Datentyp aufweisen.  

### <a name="default-literal-types"></a>Standardliteraltypen

Die Form eines Literals, wie er normalerweise in Ihrem Code angezeigt wird den Datentyp bestimmt. Die folgende Tabelle zeigt die folgenden Standardtypen.  
  
|Textform Literals|Standard-Datentyp|Beispiel|  
|-----------------------------|-----------------------|-------------|  
|Numerisch, nicht Bruchteil|`Integer`|`2147483647`|  
|Numerisch, kein Bruchteil Teil, zu groß für `Integer`|`Long`|`2147483648`|  
|Numerisch, Bruchteil|`Double`|`1.2`|  
|Eingeschlossen in doppelte Anführungszeichen|`String`|`"A"`|  
|Eingeschlossen in Nummernzeichen|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Erzwungene Literale

Visual Basic stellt eine Reihe von *Literaltypzeichen*, womit Sie verwenden können, um ein Literal einen Datentyp als dem der Form annehmen zu erzwingen. Dazu müssen Sie das Zeichen am Ende das Literal anfügen. Die folgende Tabelle zeigt die verfügbaren Literalzeichen und Beispiele für die Verwendung.
  
|Literal-Typzeichen|Datentyp|Beispiel|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

Keine Literalzeichen für den `Boolean`, `Byte`, `Date`, `Object`, `SByte`, oder `String` Datentypen oder für zusammengesetzte Datentypen wie z. B. Arrays oder Datenstrukturen.

Literale können auch die Typkennzeichen (`%`, `&`, `@`, `!`, `#`, `$`), wie Variablen, Konstanten und Ausdrücke können. Allerdings die Literalzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) kann nur mit Literalen verwendet werden.

In allen Fällen muss das literal-Typzeichen unmittelbar den literalen Wert folgen.

## <a name="hexadecimal-binary-and-octal-literals"></a>Hexadezimale, oktale und binäre Literale

Der Compiler interpretiert normalerweise ein Integer-literal in Zahlensystems dezimale (Basis 10) sein. Sie können auch ein Integer-literal definieren, als Hexadezimalwert (Basis 16) Zahl mit der `&H` Präfix als Binärdatei (Basis 2) Zahl mit der `&B` -Präfix und als eine oktale (Basis 8) Zahl mit der `&O` Präfix. Die Ziffern, die das Präfix folgen müssen für das System Anzahl geeignet sein. Dies wird in die folgende Tabelle veranschaulicht.  
  
|Zahlenbasis|Präfix|Gültige Werte|Beispiel|
|-----------------|------------|------------------------|-------------|
|Hexadezimalformat (Basis 16)|`&H`|0-9 und A-F|`&HFFFF`|
|Binärdatei (Basis 2)|`&B`|0-1|`&B01111100`|
|Oktalformat (Basis 8)|`&O`|0-7|`&O77`|

Ab Visual Basic 2017 können Sie den Unterstrich (`_`) als Gruppentrennzeichen um ein ganzzahliges Literal die Lesbarkeit zu verbessern. Im folgenden Beispiel wird die `_` Zeichen um ein binäres literal in 8-Bit-Gruppen zu gruppieren:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

Führen Sie ein Präfix Literal mit einem Literalzeichen. Das folgende Beispiel zeigt dies.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

Im vorherigen Beispiel `counter` hat den Dezimalwert zwischen-32768, und `flags` hat den Dezimalwert + 32768.

Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern. Zum Beispiel:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>Siehe auch

 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
