---
title: Numerische Datentypen (Visual Basic) | Microsoft-Dokumentation
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
- integral types, Visual Basic
- Short data type, numeric data types
- Double data type, numeric data types
- Long data type, Visual Basic numeric data types
- numbers, whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers, integer
- fractional data types
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type, numeric data types
- exponent, of fractional numbers
- integers
- numeric data types, Visual Basic
- Single data type, numeric types
- Decimal data type, numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
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
ms.openlocfilehash: 3c3098370b8d9dcb6aafcb06dcfb8f4e144b899a
ms.lasthandoff: 03/13/2017

---
# <a name="numeric-data-types-visual-basic"></a>Numerische Datentypen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]stellt mehrere *numerische Datentypen* für die Behandlung von Zahlen in unterschiedlichen Darstellungen. *Ganzzahlige* Typen darstellen, nur ganze Zahlen (positiv, negativ und&0; (null)), und *Nonintegral* Zahlen mit Nachkommastellen und ganze Zahl darstellen.  
  
 Eine Tabelle mit einer Side-by-Side-Vergleich der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen finden Sie in [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="integral-numeric-types"></a>Ganzzahlige numerische Typen  
 *Ganzzahlige Datentypen* sind diejenigen, die nur Zahlen ohne Nachkommastellen darstellen.  
  
 Die *signiert* ganzzahlige Datentypen sind [SByte-Datentyp](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-Bit), [Short-Datentyp](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-Bit), [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-Bit) und [vom Typ Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-Bit). Wenn eine Variable immer ganze Zahlen anstelle von Zahlen mit Nachkommastellen speichert, deklarieren Sie sie als einen dieser Typen.  
  
 Die *ohne Vorzeichen* ganzzahligen Typen werden [Byte-Datentyp](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-Bit), [UShort-Datentyp](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-Bit), [UInteger-Datentyp](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-Bit) und [ULong-Datentyp](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-Bit). Wenn eine Variable binäre Daten oder Daten unbekannten Typs enthält, deklarieren Sie sie als einen dieser Typen.  
  
### <a name="performance"></a>Leistung  
 Arithmetische Operationen sind schneller mit ganzzahligen Typen als mit anderen Datentypen. Am schnellsten mit werden die `Integer` und `UInteger` Typen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="large-integers"></a>Große ganze Zahlen  
 Wenn Sie eine ganze Zahl größer als halten müssen die `Integer` Datentyp enthalten kann, können Sie die `Long` Daten geben Sie stattdessen. `Long`-Variablen können Zahlen von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 enthalten. Vorgänge mit `Long` sind etwas langsamer als bei `Integer`.  
  
 Wenn Sie noch größere Werte benötigen, können Sie die [Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Sie können Zahlen von-79.228.162.514.264.337.593.543.950.335 bis 79.228.162.514.264.337.593.543.950.335 in enthalten eine `Decimal` -Variablen verwenden, wenn Sie keine Dezimalstellen verwenden. Allerdings Vorgänge mit `Decimal` Zahlen sind beträchtlich langsamer als ein mit einem anderen numerischen Datentyp.  
  
### <a name="small-integers"></a>Kleine ganze Zahlen  
 Wenn Sie nicht den vollen Umfang der benötigen die `Integer` Datentyp aufweisen, können Sie die `Short` -Datentyp, der ganze Zahlen von-32.768 bis 32.767 enthalten kann. Für den kleinsten Integer-Bereich der `SByte` enthält Zahlen von-128 bis 127. Wenn Sie eine sehr große Anzahl von Variablen, die kleinen ganzen Zahlen verfügen, die common Language Runtime kann manchmal speichern, Ihre `Short` und `SByte` Variablen effizienter und Arbeitsspeicher belegt. Allerdings Vorgänge mit `Short` und `SByte` sind etwas langsamer als bei `Integer`.  
  
### <a name="unsigned-integers"></a>Ganze Zahlen ohne Vorzeichen  
 Wenn Sie wissen, dass Ihre Variable nie eine negative Zahl enthalten muss, können Sie die *Typen ohne Vorzeichen*`Byte`, `UShort`, `UInteger`, und `ULong`. Jeder dieser Datentypen kann eine positive ganze Zahl doppelt so groß wie den entsprechenden Typ signed enthalten (`SByte`, `Short`, `Integer`, und `Long`). Hinsichtlich der Leistung ist jeder Datentyp ohne Vorzeichen genauso leistungsstark wie der entsprechende Datentyp mit Vorzeichen. Insbesondere `UInteger` teilt mit `Integer` die Unterscheidung der effizienteste aller elementaren numerischen Datentypen.  
  
## <a name="nonintegral-numeric-types"></a>Nicht ganzzahlige numerische Typen  
 *Nicht ganzzahlige Datentypen* sind für die Darstellung von Zahlen mit Nachkommastellen und ganze Zahl.  
  
 Die nicht ganzzahligen numerischen Datentypen sind `Decimal` (128-Bit-Festkomma) [Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-Bit-Gleitkomma) und [Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-Bit-Gleitkomma). Sie sind alle signierten Typen. Wenn eine Variable einen Bruch enthalten kann, deklarieren Sie sie als einen dieser Typen.  
  
 `Decimal`ist kein Gleitkommadatentyp. `Decimal`Zahlen haben einen binären Ganzzahlwert und einen Ganzzahlskalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist.  
  
 Sie können `Decimal` -Variablen für Währungswerte. Der Vorteil ist die Genauigkeit der Werte. Die `Double` -Datentyp ist schneller und weniger Speicher benötigt, aber Rundungsfehler unterliegt. Die `Decimal` Datentyp behält die vollständige Genauigkeit von bis zu 28 Dezimalstellen.  
  
 Gleitkomma (`Single` und `Double`) können größere Wertbereiche als `Decimal` Zahlen kann jedoch Rundungsfehler auftreten. Gleitkommatypen unterstützen weniger signifikante Stellen als `Decimal` können jedoch größere Werte darstellen.  
  
 Nicht ganzzahlige können ausgedrückt werden als MmmEeee mmm wird die *Mantisse* (die signifikante Stellen) und Eee ist die *Exponent* (eine Potenz von 10). Die höchsten positiven Werte der nicht ganzzahligen Datentypen sind 7.9228162514264337593543950335E + 28 für `Decimal`, 3,4028235E + 38 für `Single`, und 1, 79769313486231570E + 308 für `Double`.  
  
### <a name="performance"></a>Leistung  
 `Double`ist der effizienteste Datentyp mit Nachkommastellen, da die Prozessoren auf den aktuellen Plattformen Gleitkommaoperationen mit doppelter Genauigkeit ausführen. Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.  
  
### <a name="small-magnitudes"></a>Kleine Werte  
 Für Zahlen mit der kleinstmöglichen Größe (nahe 0) `Double` Variablen können Zahlen enthalten so klein wie - 4.94065645841246544E-324 für negative Werte und 4.94065645841246544E-324 für positive Werte.  
  
### <a name="small-fractional-numbers"></a>Kleine Bruchzahlen  
 Wenn Sie nicht den vollen Umfang der benötigen die `Double` Datentyp aufweisen, können Sie die `Single` -Datentyp, der Gleitkommazahlen von - 3,4028235E + 38 bis 3,4028235E + 38 enthalten kann. Die kleinsten Werte für `Single` Variablen sind - 1.401298E-45 für negative Werte und 1.401298E-45 für positive Werte. Wenn Sie eine sehr große Anzahl von Variablen, die kleine Gleitkommazahlen enthalten verfügen, kann manchmal die common Language Runtime speichern Ihre `Single` Variablen effizienter und Arbeitsspeicher belegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Sonstige Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
