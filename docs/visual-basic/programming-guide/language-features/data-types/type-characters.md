---
title: Geben Sie die Zeichen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6e112e7d221ef8e7a660094306bbb242c988e843
ms.lasthandoff: 03/13/2017

---
# <a name="type-characters-visual-basic"></a>Typzeichen (Visual Basic)
Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, können Sie den Datentyp des einige Programmierelemente mit Erzwingen einer *Typzeichen*. Das Typzeichen muss unmittelbar auf das Element, ohne dazwischenliegende Zeichen jeglicher Art folgen.  
  
 Das Typzeichen ist nicht Teil des Namens des Elements. Ein mit einem Typzeichen definiertes Element kann ohne das Typzeichen verwiesen werden.  
  
## <a name="identifier-type-characters"></a>Typkennzeichen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Stellt eine Reihe von *Typkennzeichen*, die Sie in einer Deklaration verwenden können, um den Datentyp einer Variablen oder Konstanten angeben. Die folgende Tabelle zeigt die verfügbaren Typkennzeichen mit Beispielen für die Verwendung.  
  
|Typkennzeichen|Datentyp|Beispiel|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Keine Typkennzeichen für die `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort` Datentypen oder zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.  
  
 In einigen Fällen können Sie Anfügen der `$` das Zeichen eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Funktion, z. B. `Left$` anstelle von `Left`, um einen Rückgabewert vom Typ erhalten `String`.  
  
 In allen Fällen muss die Typkennzeichen unmittelbar auf den Namen des Bezeichners folgen.  
  
## <a name="literal-type-characters"></a>Literaltypzeichen  
 Ein *Zeichenfolgenliteral* ist eine Textdarstellung eines bestimmten Werts eines Datentyps.  
  
### <a name="default-literal-types"></a>Standardliteraltypen  
 Die Form eines Literals richtet in Ihrem Code in der Regel sich Datentyp. Die folgende Tabelle zeigt diese Standardtypen.  
  
|Textform literalen|Standard-Datentyp|Beispiel|  
|-----------------------------|-----------------------|-------------|  
|Numerisch, kein Bruchteil|`Integer`|`2147483647`|  
|Numerisch, kein Bruchteil Teil, zu groß für`Integer`|`Long`|`2147483648`|  
|Numerisch, Bruchteil|`Double`|`1.2`|  
|Eingeschlossen in doppelte Anführungszeichen|`String`|`"A"`|  
|Eingeschlossen in Nummernzeichen|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a>Erzwungene Literale  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Stellt eine Reihe von *Literaltypzeichen*, womit Sie verwenden können, erzwingen Sie ein Literal einen Datentyp als seine Form annimmt. Dazu fügen Sie das Zeichen am Ende des Literals. Die folgende Tabelle zeigt die verfügbaren Literalzeichen und Beispiele für deren Verwendung.  
  
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
  
 Keine Literalzeichen für die `Boolean`, `Byte`, `Date`, `Object`, `SByte`, oder `String` Datentypen oder zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.  
  
 Literale können auch die Typkennzeichen (`%`, `&`, `@`, `!`, `#`, `$`), wie Variablen, Konstanten und Ausdrücken können. Allerdings die Literalzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) kann nur mit Literalen verwendet werden.  
  
 In allen Fällen muss das Literalzeichen unmittelbar auf den Literalwert folgen.  
  
## <a name="hexadecimal-and-octal-literals"></a>Hexadezimale und oktale Literale  
 Der Compiler construes normalerweise ein Ganzzahlliteral im Dezimalformat (Basis 10) Zahlensystem. Sie können erzwingen, dass eine ganze Zahl literal werden Hexadezimalformat (Basis 16) mit der `&H` Präfix, und Sie können erzwingen, dass oktale (Basis 8) werden die `&O` Präfix. Die Ziffern, die dem Präfix folgen müssen Zahlensystem geeignet sein. Dies wird in die folgende Tabelle veranschaulicht.  
  
|Zahlenbasis|Präfix|Gültige Werte|Beispiel|  
|-----------------|------------|------------------------|-------------|  
|Hexadezimalformat (Basis 16)|`&H`|0-9 und A-F|`&HFFFF`|  
|Oktalformat (Basis 8)|`&O`|0-7|`&O77`|  
  
 Sie können ein vorangestellter Literal mit einem Literalzeichen folgen. Das folgende Beispiel zeigt dies.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 Im vorherigen Beispiel `counter` hat den Dezimalwert-32768, und `flags` hat den Dezimalwert +&32768;.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
