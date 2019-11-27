---
title: Typzeichen
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
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352926"
---
# <a name="type-characters-visual-basic"></a>Typzeichen (Visual Basic)

Zusätzlich zur Angabe eines Datentyps in einer Deklarations Anweisung können Sie den Datentyp einiger Programmier Elemente mit einem *Typzeichen*erzwingen. Das Typzeichen muss unmittelbar auf das-Element folgen, ohne dass dabei dazwischen liegende Zeichen vorhanden sind.

Das Typzeichen ist nicht Teil des Namens des Elements. Auf ein Element, das mit einem Typzeichen definiert ist, kann ohne das Typzeichen verwiesen werden.

## <a name="identifier-type-characters"></a>Bezeichnertyp Zeichen

Visual Basic stellt einen Satz von *Bezeichnertyp Zeichen* bereit, die Sie in einer-Deklaration verwenden können, um den Datentyp einer Variablen oder Konstanten anzugeben. In der folgenden Tabelle werden die verfügbaren Bezeichnertyp Zeichen und Verwendungs Beispiele angezeigt.
  
|Bezeichnertyp Zeichen|Datentyp|Beispiel|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Es sind keine Bezeichnertyp Zeichen für die Datentypen "`Boolean`", "`Byte`", "`Char`", "`Date`", "`Object`", "`SByte`", "`Short`", "`UInteger`", "`ULong`" oder "`UShort`" vorhanden.

In einigen Fällen können Sie das `$` Zeichen an eine Visual Basic Funktion anfügen, z. b. `Left$` anstelle `Left`, um einen Rückgabewert vom Typ `String`zu erhalten.

In allen Fällen muss das Bezeichnertyp Zeichen direkt auf den Bezeichnernamen folgen.

## <a name="literal-type-characters"></a>Literaltypzeichen

Ein *Literalwert* ist eine Textdarstellung eines bestimmten Werts eines Datentyps.  

### <a name="default-literal-types"></a>Standardliteraltypen

Die Form eines Literals, wie er im Code angezeigt wird, bestimmt normalerweise seinen Datentyp. In der folgenden Tabelle sind diese Standardtypen aufgeführt.  
  
|Textform des Literals|Standard Datentyp|Beispiel|  
|-----------------------------|-----------------------|-------------|  
|Numerisch, kein Bruchteil|`Integer`|`2147483647`|  
|Numerisch, kein Bruchteile, zu groß für `Integer`|`Long`|`2147483648`|  
|Numerisch, Bruchteile|`Double`|`1.2`|  
|Eingeschlossen in doppelte Anführungszeichen.|`String`|`"A"`|  
|Eingeschlossen in Nummern Zeichen|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Erzwungene Literaltypen

Visual Basic stellt einen Satz von *Literaltypzeichen*bereit, die Sie verwenden können, um zu erzwingen, dass ein Literale einen anderen Datentyp annimmt als den, der vom Formular angegeben wird. Dies erreichen Sie, indem Sie das Zeichen an das Ende des Literals anhängen. In der folgenden Tabelle sind die verfügbaren Literaltypzeichen und Verwendungs Beispiele aufgeführt.
  
|Literaltypzeichen|Datentyp|Beispiel|  
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

Für die Datentypen "`Boolean`", "`Byte`", "`Date`", "`Object`", "`SByte`" oder "`String`" oder für zusammengesetzte Datentypen wie Arrays oder Strukturen sind keine Literaltypzeichen vorhanden.

Literale können auch die Bezeichnertyp Zeichen (`%`, `&`, `@`, `!`, `#`, `$`) verwenden, ebenso wie Variablen, Konstanten und Ausdrücke. Die Literaltypzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) können jedoch nur mit Literalen verwendet werden.

In allen Fällen muss das Literaltypzeichen unmittelbar auf den Literalwert folgen.

## <a name="hexadecimal-binary-and-octal-literals"></a>Hexadezimale, binäre und oktale Literale

Der Compiler interpretiert normalerweise ein Ganzzahlliteral, das im Dezimalzahlen System (Base 10) liegt. Sie können ein Ganzzahlliteral auch als hexadezimale Zahl (Basis 16) mit dem `&H`-Präfix definieren, als binäre (Basis 2) Zahl mit dem `&B` Präfix und als oktale (Basis 8)-Nummer mit dem `&O` Präfix. Die Ziffern, die dem Präfix folgen, müssen für das Zahlensystem geeignet sein. Dies wird in der folgenden Tabelle veranschaulicht.  
  
|Zahlenbasis|Präfix|Gültige Ziffern Werte|Beispiel|
|-----------------|------------|------------------------|-------------|
|Hexadezimalformat (Basis 16)|`&H`|0-9 und A-F|`&HFFFF`|
|Binary (Basis 2)|`&B`|0-1|`&B01111100`|
|Oktalformat (Basis 8)|`&O`|0-7|`&O77`|

Ab Visual Basic 2017 können Sie den Unterstrich (`_`) als Gruppen Trennzeichen verwenden, um die Lesbarkeit eines ganzzahligen Literals zu verbessern. Im folgenden Beispiel wird das `_` Zeichen verwendet, um ein binäres wahrsten in 8-Bit-Gruppen zu gruppieren:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

Sie können einem Literalzeichen ein Literalzeichen folgen. Dies wird im folgenden Beispiel veranschaulicht.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

Im vorherigen Beispiel hat `counter` den Dezimalwert-32768 und `flags` den Dezimalwert + 32768.

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
