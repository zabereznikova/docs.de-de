---
title: "Widening and Narrowing Conversions (Visual Basic) | Microsoft Docs"
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
  - "widening conversions"
  - "narrowing conversions"
  - "conversions, type"
  - "data types [Visual Basic], changing"
  - "variables [Visual Basic], changing data type"
  - "conversions, exceptions during conversion"
  - "type conversion, exceptions during conversion"
  - "conversions, data type"
  - "conversions, narrowing"
  - "type conversion, narrowing"
  - "data type conversion, widening"
  - "data type conversion, narrowing"
  - "changing data types"
  - "type conversion, widening"
  - "data type conversion, exceptions during conversion"
  - "conversions, widening"
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Widening and Narrowing Conversions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Ein wichtiger Aspekt von Typkonvertierungen ist, ob das Ergebnis der Konvertierung innerhalb des Bereichs des Zieldatentyps liegt.  
  
 Eine *erweiternde Konvertierung* wird ein Wert in einen Datentyp, der einen beliebigen Wert der ursprünglichen Daten zulassen kann.  Bei erweiternden Konvertierungen bleibt der Wert erhalten, seine Darstellung wird jedoch geändert.  Dies geschieht, wenn Sie mit einem ganzzahligen Typ zu konvertieren `Decimal`, oder `Char` zu `String`auf.  
  
 Bei einer *eingrenzenden Konvertierung* wird ein Wert in einen Datentyp geändert, der unter Umständen nicht alle möglichen Werte enthält.  Beispielsweise wird ein Brucher Wert gerundet, wenn er zu einem ganzzahligen Typ konvertiert werden und ein numerischer Typ, der in `Boolean` konvertiert wird, ist entweder `True` oder `False`reduziert.  
  
## Erweiternde Konvertierungen  
 In der folgenden Tabelle sind die standardmäßigen erweiternden Konvertierungen zusammengefasst.  
  
|||  
|-|-|  
|Datentyp|Erweiterung in Datentypen <sup>1</sup>|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Beliebiger aufgelisteter Typ \([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)\)|Der zugrunde liegende ganzzahliger Typ und jeder Typ, in den der zugrunde liegende Typ erweitert wird.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char`\-Array|`Char`\-Array, `String`|  
|Beliebiger Typ|[Objekt](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Beliebiger abgeleiteter Typ|Beliebiger Basistyp, von dem er abgeleitet <sup>3</sup>ist.|  
|Beliebiger Typ|Beliebige Schnittstelle, die sie implementiert.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Beliebiger Datentyp oder Objekttyp.|  
  
 <sup>1</sup> Per Definition wird jeder Datentyp in sich selbst erweitert.  
  
 <sup>2</sup> Bei Konvertierungen von `Integer`, `UInteger`, `Long`, `ULong` oder `Decimal` in `Single` bzw. `Double` können zwar Ungenauigkeiten, aber niemals Größenverluste auftreten.  In diesem Sinne tritt kein Informationsverlust auf.  
  
 <sup>3</sup> Es mag überraschen, dass es sich bei der Konvertierung von einem abgeleiteten Typ in einen seiner Basistypen um eine erweiternde Konvertierung handelt.  Dies ist der Fall, da der abgeleitete Typ alle Member des Basistyps enthält, sodass er als eine Instanz des Basistyps qualifiziert wird.  Umgekehrt enthält der Basistyp nicht die vom abgeleiteten Typ definierten neuen Member.  
  
 Erweiternde Konvertierungen sind zur Laufzeit immer erfolgreich. Datenverluste treten hier nie auf.  Sie können sie stets implizit ausführen, unabhängig davon, ob die [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) für die Typüberprüfung `On` oder `Off` festlegt.  
  
## Eingrenzende Konvertierungen  
 Es gibt die folgenden standardmäßigen eingrenzenden Konvertierungen:  
  
-   Konvertierungen in die umgekehrte Richtung zu den erweiternden Konvertierungen in der obigen Tabelle \(mit der Ausnahme, dass jeder Typ sich in sich selbst erweitert\)  
  
-   Konvertierungen in beide Richtungen zwischen [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) und einem beliebigen numerischen Typ  
  
-   Konvertierungen von einem beliebigen numerischen Typ in einen beliebigen Enumerationstyp \(`Enum`\)  
  
-   Konvertierungen in beide Richtungen zwischen [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) und einem beliebigen numerischen Typ, `Boolean` oder [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Konvertierungen von einem Datentyp oder Objekttyp in einen davon abgeleiteten Typ  
  
 Eingrenzende Konvertierungen sind zur Laufzeit nicht immer erfolgreich. Sie können fehlschlagen, oder es können Datenverluste auftreten.  Ein Fehler tritt auf, wenn der Zieldatentyp nicht den konvertierten Wert empfangen kann.  So kann bei einer numerischen Konvertierung beispielsweise ein Überlauf auftreten.  Mit dem Compiler können Sie implizit keine eingrenzende Konvertierungen ausführen, es sei denn, die [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) setzt die Typüberprüfung auf `Off`.  
  
> [!NOTE]
>  Der Fehler für einschränkende Konvertierung wird unterdrückt für Konvertierungen von den Elementen in einer `For Each…Next`\-Auflistung zur Schleifensteuerungsvariable.  Weitere Informationen und Beispiele finden Sie im Abschnitt "Eingrenzende Konvertierungen" unter [For Each...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### Verwendungsmöglichkeiten für eingrenzende Konvertierungen  
 Sie verwenden eingrenzende Konvertierungen, wenn Sie genau wissen, dass der Ausgangswert in den Zieldatentyp konvertiert werden kann, ohne dass dabei Fehler oder Datenverluste auftreten.  Wenn Sie beispielsweise `String` verfügen, das Sie enthalten entweder „True“ oder „False“ bekannt, können Sie das `CBool`\-Schlüsselwort verwenden, um es zu `Boolean`zu konvertieren.  
  
## Ausnahmen während der Konvertierung  
 Da erweiternde Konvertierungen immer erfolgreich sind, lösen sie keine Ausnahmen aus.  Eingrenzende Konvertierungen lösen bei Fehlschlagen in der Regel die folgenden Ausnahmen aus:  
  
-   <xref:System.InvalidCastException>, wenn keine Konvertierung zwischen den beiden Typen definiert ist  
  
-   <xref:System.OverflowException>, \(nur bei ganzzahligen Typen\) wenn der konvertierte Wert für den Zieltyp zu groß ist  
  
 Wenn in einer Klasse oder Struktur eine [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) definiert ist, die als Operator für die Konvertierung in diese oder aus dieser Klasse bzw. Struktur dient, kann diese `CType`\-Funktion eine geeignete Ausnahme auslösen.  Zusätzlich kann `CType` ggf. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Funktionen oder [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Methoden aufrufen, die wiederum verschiedene Ausnahmen auslösen können.  
  
## Veränderungen bei der Konvertierung von Verweistypen  
 Bei der Konvertierung eines *Verweistyps* wird nur der Zeiger auf den Wert konvertiert.  Der Wert an sich wird weder kopiert noch in irgendeiner Weise verändert.  Lediglich der Datentyp der Variablen, die den Zeiger enthält, kann sich ändern.  Im folgenden Beispiel wird der Datentyp von der abgeleiteten Klasse in die Basisklasse konvertiert. Das Objekt, auf das nun beide Variablen zeigen, wird dabei allerdings nicht verändert.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)