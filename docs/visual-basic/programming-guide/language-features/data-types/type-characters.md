---
title: Typzeichen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bd017db40fc28c78e960a889947cc7323e3e156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-characters-visual-basic"></a>Geben Sie die Zeichen (Visual Basic)

Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, Sie können erzwingen, dass den Datentyp der einige Programmierelemente mit einem *-Typzeichen*. Das Typzeichen muss unmittelbar auf das Element, ohne dazwischenliegende Zeichen jeglicher Art folgen.

Das Typzeichen ist nicht Teil des Namens des Elements. Ein mit einem Typzeichen definiertes Element kann ohne das Typzeichen verwiesen werden.

## <a name="identifier-type-characters"></a>Typkennzeichen

Visual Basic stellt eine Reihe von *Typkennzeichen* , dass Sie in einer Deklaration verwenden können, um den Datentyp einer Variable oder Konstante angeben. Die folgende Tabelle zeigt die verfügbaren Typkennzeichen mit Beispielen für die Verwendung.
  
|Typkennzeichen|Datentyp|Beispiel|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Keine Typkennzeichen vorhanden, für die `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort` Datentypen oder für ein Zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.

In einigen Fällen können Sie Anfügen der `$` Zeichen für eine Visual Basic-Funktion, z. B. `Left$` anstelle von `Left`, um einen Rückgabewert vom Typ erhalten `String`.

In allen Fällen muss die Typkennzeichen den Bezeichnernamen unmittelbar folgen.

## <a name="literal-type-characters"></a>Literaltypzeichen

Ein *literal* ist eine Textdarstellung eines bestimmten Werts einen Datentyp aufweisen.  

### <a name="default-literal-types"></a>Standardliteraltypen

Die Form eines Literals, wie er im Code, in der Regel enthalten Angabe des Datentyps bestimmt. Die folgende Tabelle zeigt diese Standarddatentypen.  
  
|Textform Literal|Standard-Datentyp|Beispiel|  
|-----------------------------|-----------------------|-------------|  
|Numerisch, kein Bruchteil|`Integer`|`2147483647`|  
|Numerisch, kein Bruchteil Teil, zu groß für`Integer`|`Long`|`2147483648`|  
|Numerisch, Bruchteil|`Double`|`1.2`|  
|Eingeschlossen in doppelte Anführungszeichen|`String`|`"A"`|  
|Eingeschlossen in Nummernzeichen|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Erzwungene Literaltypen

Visual Basic stellt eine Reihe von *Literaltypzeichen*, womit Sie verwenden können, um ein Literal an einen anderen Datentyp als dem seiner Form anzunehmen zu erzwingen. Dazu müssen Sie das Zeichen am Ende das Literal anfügen. Die folgende Tabelle zeigt die verfügbaren Literalzeichen mit Beispielen für die Verwendung.
  
|(Literalzeichen)|Datentyp|Beispiel|  
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

Keine Literalzeichen für die `Boolean`, `Byte`, `Date`, `Object`, `SByte`, oder `String` Datentypen oder für zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.

Literale können auch die Typkennzeichen (`%`, `&`, `@`, `!`, `#`, `$`), wie Variablen, Konstanten und Ausdrücke können. Allerdings die Literalzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) kann nur mit Literalen verwendet werden.

In allen Fällen muss das literal-Typzeichen den Literalwert unmittelbar folgen.

## <a name="hexadecimal-binary-and-octal-literals"></a>Hexadezimal, binäre und oktale Literale

Der Compiler interpretiert normalerweise ein Integer-literal um im System Anzahl Dezimalzahl (Basis 10) sein. Sie können auch ein Integer-literal als Zahl mit Hexadezimalformat (Basis 16) definieren die `&H` Präfix, als Zahl Binärdatei (Basis 2) mit der `&B` Präfix, und als eine oktale (Basis 8) Zahl mit der `&O` Präfix. Die Ziffern, die das Präfix folgen müssen für das System die Zahlen geeignet sein. Dies wird anhand die folgende Tabelle veranschaulicht.  
  
|Zahlenbasis|Präfix|Gültige Werte|Beispiel|
|-----------------|------------|------------------------|-------------|
|Hexadezimalformat (Basis 16)|`&H`|0-9 und A-F|`&HFFFF`|
|Binär (Basis 2)|`0B`|0-1|`&B01111100`|
|Oktalformat (Basis 8)|`&O`|0-7|`&O77`|

In Visual Basic 2017 starten, können Sie das Unterstrich-Zeichen (`_`) als Gruppentrennzeichen um die Lesbarkeit der ein ganzzahliges Literal zu verbessern. Im folgenden Beispiel wird die `_` Zeichen um ein binäres literal in 8-Bit-Gruppen zu gruppieren:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

Sie können einem Literal mit einem literal-Typzeichen Präfix folgen. Das folgende Beispiel zeigt dies.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

Im vorherigen Beispiel `counter` hat den Dezimalwert zwischen-32768, und `flags` hat den Dezimalwert + 32768.

## <a name="see-also"></a>Siehe auch

 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
