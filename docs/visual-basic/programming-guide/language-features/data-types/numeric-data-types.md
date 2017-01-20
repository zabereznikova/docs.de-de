---
title: "Numeric Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "integral types, Visual Basic"
  - "Short data type, numeric data types"
  - "Double data type, numeric data types"
  - "Long data type, Visual Basic numeric data types"
  - "numbers, whole"
  - "fractions"
  - "numbers"
  - "whole numbers"
  - "integer numbers"
  - "numbers, integer"
  - "fractional data types"
  - "mantissas, of fractional numbers"
  - "mantissas"
  - "data types [Visual Basic], numeric"
  - "Integer data type, numeric data types"
  - "exponent, of fractional numbers"
  - "integers"
  - "numeric data types, Visual Basic"
  - "Single data type, numeric types"
  - "Decimal data type, numeric data types"
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Numeric Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt verschiedene *numerische Datentypen* für die Verarbeitung von Zahlen in unterschiedlichen Darstellungen bereit.  *Ganzzahlige* Typen stellen nur ganze Zahlen \(positive, negative und Null\) dar, während *nicht ganzzahlige* Typen Zahlen darstellen, die aus einem ganzzahligen Wert und aus Nachkommastellen bestehen.  
  
 Eine Tabelle mit einer Gegenüberstellung der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Datentypen finden Sie unter [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Ganzzahlige numerische Typen  
 Bei *Ganzzahldatentypen* handelt es sich um Datentypen, die nur Zahlen ohne Nachkommastellen darstellen.  
  
 Die ganzzahligen Datentypen *mit Vorzeichen* sind [SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) \(8 Bits\), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md) \(16 Bits\), [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md) \(32 Bits\) und [Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md) \(64 Bits\).  Wenn in einer Variablen immer ganze Zahlen und keine Zahlen mit Nachkommastellen gespeichert werden, deklarieren Sie sie als einen dieser Typen.  
  
 Die ganzzahligen Datentypen *ohne Vorzeichen* sind [Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md) \(8 Bits\), [UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) \(16 Bits\), [UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) \(32 Bits\) und [ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) \(64 Bits\).  Wenn eine Variable binäre Daten oder Daten unbekannten Typs enthält, deklarieren Sie die Variable als einen dieser Typen.  
  
### Leistung  
 Arithmetische Operationen werden mit ganzzahligen Typen schneller als mit anderen Typen ausgeführt.  Am schnellsten werden sie in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] mit den Typen `Integer` und `UInteger` ausgeführt.  
  
### Große ganze Zahlen  
 Wenn Sie eine ganze Zahl ablegen müssen, die größer ist als der Wert, der im `Integer`\-Datentyp abgelegt werden kann, können Sie stattdessen den `Long`\-Datentyp verwenden.  `Long`\-Variablen können Zahlen von \-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 enthalten.  Operationen mit `Long`\-Variablen werden geringfügig langsamer ausgeführt als solche mit `Integer`\-Variablen.  
  
 Für noch größere Werte können Sie den [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) verwenden.  In einer `Decimal`\-Variablen können Sie Zahlen von \-79.228.162.514.264.337.593.543.950.335 bis 79.228.162.514.264.337.593.543.950.335 ablegen, wenn keine Dezimalstellen verwendet werden.  Operationen mit `Decimal`\-Zahlen sind jedoch beträchtlich langsamer als Operationen mit anderen numerischen Datentypen.  
  
### Kleine ganze Zahlen  
 Wenn Sie nicht den vollen Bereich des `Integer`\-Datentyps benötigen, können Sie den `Short`\-Datentyp verwenden, der ganze Zahlen von \-32.768 bis 32.767 enthalten kann.  Der `SByte`\-Datentyp deckt mit ganzen Zahlen von \-128 bis 127 den kleinsten Ganzzahlbereich ab.  Wenn Sie sehr viele Variablen mit kleinen ganzen Zahlen verwenden, kann die Common Language Runtime Ihre `Short`\-Variablen und `SByte`\-Variablen unter Umständen effektiver speichern, sodass weniger Arbeitsspeicher benötigt wird.  Operationen mit `Short`\-Variablen  und `SByte`\-Variablen werden jedoch etwas langsamer ausgeführt als solche mit `Integer`\-Variablen.  
  
### Ganze Zahlen ohne Vorzeichen  
 Wenn Sie wissen, dass Ihre Variable nie eine negative Zahl enthalten wird, können Sie die folgenden *Typen ohne Vorzeichen* verwenden: `Byte`, `UShort`, `UInteger` und `ULong`.  Jeder dieser Datentypen kann eine positive ganze Zahl enthalten, die doppelt so groß ist wie die entsprechende Zahl im Datentyp mit Vorzeichen \(`SByte`, `Short`, `Integer` und `Long`\).  Im Hinblick auf die Leistung ist jeder Datentyp ohne Vorzeichen genauso leistungsstark wie der entsprechende Datentyp mit Vorzeichen.  Insbesondere `UInteger` ist neben `Integer` der effizienteste aller elementaren numerischen Datentypen.  
  
## Nicht ganzzahlige numerische Typen  
 *Nicht\-Ganzzahldatentypen* stellen Daten dar, die sowohl aus einem ganzzahligen Wert als auch aus Nachkommastellen bestehen.  
  
 Die nicht ganzzahligen numerischen Datentypen sind `Decimal` \(128\-Bit\-Festkomma\), der [Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) \(32\-Bit\-Gleitkomma\) und der [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md) \(64\-Bit\-Gleitkomma\).  Alle Typen sind mit Vorzeichen versehen.  Wenn eine Variable Zahlen mit Nachkommastellen enthalten kann, deklarieren Sie sie als einen dieser Typen.  
  
 `Decimal` ist kein Gleitkommadatentyp.  `Decimal`\-Zahlen haben einen binären Ganzzahlwert und einen Ganzzahlskalierungsfaktor, der angibt, bei welchem Teil des Werts es sich um einen Dezimalbruch handelt.  
  
 Sie können Variablen für `Decimal` Geld Attributwerte verwenden.  Der Vorteil ist die Genauigkeit der Werte.  Der `Double`\-Datentyp arbeitet zwar schneller und benötigt weniger Arbeitsspeicher, ist jedoch nicht frei von Rundungsfehlern.  Der Datentyp `Decimal` behält die vollständige Genauigkeit zu 28 Dezimalstellen.  
  
 Mit Gleitkommazahlen \(`Single` und `Double`\) können größere Wertbereiche als mit `Decimal`\-Zahlen dargestellt werden, allerdings können hier Rundungsfehler auftreten.  Gleitkommatypen unterstützen weniger signifikante Stellen als `Decimal`\-Zahlen, können jedoch größere Werte darstellen.  
  
 Nicht ganzzahlige Zahlenwerte können als mmmEeee ausgedrückt werden. Dabei steht mmm für die *Mantisse* \(die signifikanten Stellen\) und eee für den *Exponenten* \(eine Potenz von 10\).  Die höchsten positiven Werte der nicht ganzzahligen Datentypen sind 7,9228162514264337593543950335E\+28 für den `Decimal`\-Datentyp, 3,4028235E\+38 für den `Single`\-Datentyp und 1,79769313486231570E\+308 für den `Double`\-Datentyp.  
  
### Leistung  
 `Double` ist der effizienteste Datentyp mit Nachkommastellen, da die Prozessoren auf den aktuellen Plattformen Gleitkommaoperationen mit doppelter Genauigkeit ausführen.  Operationen mit `Double` werden jedoch langsamer ausgeführt als solche mit ganzzahligen Typen wie `Integer`.  
  
### Kleine Wertgrößen  
 Zahlen mit der kleinstmöglichen Größe \(nahe 0\) können in `Double`\-Variablen abgelegt werden. Der Bereich erstreckt sich von \-4,94065645841246544E\-324 bis 4,94065645841246544E\-324.  
  
### Kleine Bruchzahlen  
 Wenn Sie nicht den vollen Bereich des `Double`\-Datentyps benötigen, können Sie den `Single`\-Datentyp verwenden, der Gleitkommazahlen von \-3,4028235E\+38 bis 3,4028235E\+38 enthalten kann.  Die kleinsten Werte für `Single`\-Variablen sind \-1,401298E\-45 bei negativen Werten und 1,401298E\-45 bei positiven Werten.  Wenn Sie sehr viele Variablen kleine Gleitkommazahlen enthalten, speichert die Common Language Runtime die `Single`\-Variablen unter Umständen effizienter und beansprucht weniger Arbeitsspeicher.  
  
## Siehe auch  
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Miscellaneous Data Types](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)