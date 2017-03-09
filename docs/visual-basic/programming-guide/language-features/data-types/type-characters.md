---
title: "Type Characters (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "&H prefix for hexadecimal values"
  - "hexadecimal literals"
  - "F literal type character"
  - "& identifier type character"
  - "type characters"
  - "octal literals"
  - "literals, hexadecimal"
  - "&O prefix for octal values"
  - "literals, default types"
  - "defaults, literal types"
  - "C literal type character"
  - "type characters, literal"
  - "$ identifier type character"
  - "L literal type character"
  - "UI literal type characters"
  - "default literal types"
  - "D literal type character"
  - "literals, octal"
  - "S literal type character"
  - "! identifier type character"
  - "US literal type characters"
  - "% identifier type character"
  - "data types [Visual Basic], type characters"
  - "characters, identifier type"
  - "type characters, identifier"
  - "# identifier type character"
  - "identifier type characters"
  - "literal type characters"
  - "I literal type character"
  - "R literal type character"
  - "@ identifier type character"
  - "UL literal type characters"
  - "literal types, default"
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Type Characters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Der Datentyp kann in einer Deklarationsanweisung angegeben werden. Darüber hinaus können Sie den Datentyp einiger Programmierelemente auch mit einem *Typzeichen* erzwingen.  Das Typzeichen muss unmittelbar auf das Element folgen; es darf kein Zeichen dazwischen stehen.  
  
 Das Typzeichen gehört nicht zum Namen des Elements.  Auf ein mit einem Typzeichen definiertes Element kann ohne das Typzeichen verwiesen werden.  
  
## Typkennzeichen  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stehen verschiedene *Typkennzeichen* zur Verfügung, mit deren Hilfe Sie in einer Deklaration den Datentyp einer Variablen oder einer Konstanten angeben können.  Die folgende Tabelle zeigt die verfügbaren Typkennzeichen und Beispiele für deren Verwendung.  
  
|Typkennzeichen|Datentyp|Beispiel|  
|--------------------|--------------|--------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 Für die Datentypen `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong` oder `UShort` sowie für zusammengesetzte Datentypen, wie etwa Arrays oder Strukturen, gibt es keine Typkennzeichen.  
  
 In einigen Fällen können Sie das `$`\-Zeichen an eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Funktion anhängen, beispielsweise `Left$` statt `Left`, um einen Rückgabewert vom Typ `String` zu erhalten.  
  
 Das Typkennzeichen muss jedoch immer unmittelbar auf den Bezeichner folgen.  
  
## Literalzeichen  
 Ein *Literal* ist eine Textdarstellung eines bestimmten Werts eines Datentyps.  
  
### Standardliteraltypen  
 Der Datentyp eines Literals richtet sich in der Regel nach dessen Format im Code.  Die Standardtypen sind in der folgenden Tabelle zusammengefasst.  
  
|Textdarstellung des Literals|Standarddatentyp|Beispiel|  
|----------------------------------|----------------------|--------------|  
|Numerisch, kein Bruchteil|`Integer`|`2147483647`|  
|Numerisch, kein Bruchteil, zu groß für `Integer`|`Long`|`2147483648`|  
|Numerisch, Bruchteil|`Double`|`1.2`|  
|In doppelten Anführungszeichen eingeschlossen|`String`|`"A"`|  
|Eingeschlossen in Nummernzeichen|`Date`|`#5/17/1993 9:32 AM#`|  
  
### Erzwungene Literale  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stehen verschiedene *Literalzeichen* zur Verfügung, mit denen Sie erzwingen können, dass ein Literal einen anderen als den durch seine Form angezeigten Datentyp annimmt.  Dafür fügen Sie das Zeichen an das Ende des Literals an.  Die folgende Tabelle zeigt die verfügbaren Literalzeichen und Beispiele für deren Verwendung.  
  
|Literalzeichen|Datentyp|Beispiel|  
|--------------------|--------------|--------------|  
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
  
 Für die Datentypen `Boolean`, `Byte`, `Date`, `Object`, `SByte` oder `String` sowie für zusammengesetzte Datentypen, wie etwa Arrays oder Strukturen, gibt es keine Literalzeichen.  
  
 Genau wie in Variablen, Konstanten und Ausdrücken können in Literalen ebenfalls die Typkennzeichen \(`%`, `&`, `@`, `!`, `#`, `$`\) verwendet werden.  Die Literalzeichen \(`S`, `I`, `L`, `D`, `F`, `R`, `C`\) können allerdings nur für Literale benutzt werden.  
  
 Das Literalzeichen muss in jedem Fall unmittelbar auf den Literalwert folgen.  
  
## Hexadezimale und oktale Literale  
 Der Compiler geht in der Regel davon aus, dass ein Integer\-Literal auf dem Dezimalzahlensystem \(Basis 10\) aufbaut.  Sie können allerdings mit dem Präfix `&H` erzwingen, dass ein Integer\-Literal als Hexadezimalzahl \(Basis 16\) interpretiert wird. Mit dem Präfix `&O` können Sie erzwingen, dass ein Integer\-Literal als Oktalzahl \(Basis 8\) interpretiert wird.  Die Ziffern, die dem Präfix folgen, müssen dem jeweiligen Zahlensystem entsprechen.  Dies wird aus der folgenden Tabelle ersichtlich:  
  
|Zahlenbasis|Präfix|Gültige Werte|Beispiel|  
|-----------------|------------|-------------------|--------------|  
|Hexadezimalformat \(Basis 16\)|`&H`|0 bis 9 und A bis F|`&HFFFF`|  
|Oktalformat \(Basis 8\)|`&O`|0\-7|`&O77`|  
  
 Einem Literal mit Präfix kann ein Literalzeichen folgen.  Im folgenden Beispiel wird dies veranschaulicht.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 Im vorhergehenden Beispiel hat `counter` den Dezimalwert \-32768, und `flags` hat den Dezimalwert \+32768.  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)