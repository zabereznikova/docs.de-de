---
title: Erweiternde und eingrenzende Konvertierungen (Visual Basic) | Microsoft-Dokumentation
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
- widening conversions
- narrowing conversions
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions, exceptions during conversion
- type conversion, exceptions during conversion
- conversions, data type
- conversions, narrowing
- type conversion, narrowing
- data type conversion, widening
- data type conversion, narrowing
- changing data types
- type conversion, widening
- data type conversion, exceptions during conversion
- conversions, widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 88c5db6e7e82a88ae8015b581e5a795ec389d003
ms.lasthandoff: 03/13/2017

---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Erweiternde und eingrenzende Konvertierungen (Visual Basic)
Ein wichtiger Aspekt mit einer Typumwandlung ist, ob das Ergebnis der Konvertierung innerhalb des Bereichs von den Zieldatentyp ist.  
  
 Ein *erweiternden Konvertierung* ändert einen Wert in einen Datentyp, der alle möglichen Werte der ursprünglichen Daten ermöglichen kann.  Erweiternde Konvertierungen Quellwert beibehalten, aber es können seine Darstellung ändern. Dies geschieht, wenn die Konvertierung von ganzzahligen Typen in `Decimal`, oder von `Char` auf `String`.  
  
 Eine *einschränkende* Konvertierung ändert einen Wert in einen Datentyp, der möglicherweise nicht in der Lage ist, alle möglichen Werte zu speichern. Beispielsweise wird ein Dezimalstellenwert gerundet, bei der Konvertierung in einen ganzzahligen Typ und einen numerischen Typ konvertiert wird, um `Boolean` wird entweder reduziert `True` oder `False`.  
  
## <a name="widening-conversions"></a>Erweiternde Konvertierungen  
 Die folgende Tabelle zeigt die Standard-erweiternde Konvertierungen.  
  
|Datentyp|Erweiterung in Datentypen <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Kurze](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Ganze Zahl](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Lange](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Ulong-Typ](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Beliebiger aufgelisteter Typ ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Der zugrunde liegende ganzzahlige Typ und jeden Typ, der der zugrunde liegende Typ erweitert wird.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char`-Array|`Char`Array`String`|  
|Beliebiger Typ|[Objekt](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Alle abgeleiteten Typ|Alle Basistypen, die von der sie abgeleitet ist <sup>3</sup>.|  
|Beliebiger Typ|Eine Schnittstelle, die er implementiert.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Jeder Datentyp oder Objekttyp.|  
  
 <sup>1</sup> per Definition jeder-Datentyp wird auf sich selbst.  
  
 <sup>2</sup> Konvertierungen von `Integer`, `UInteger`, `Long`, `ULong`, oder `Decimal` auf `Single` oder `Double` Verlust an Genauigkeit, aber nie in Verlust Größenordnung kommen. In diesem Fall führen Sie kein Verlust von Informationen erforderlich.  
  
 <sup>3</sup> es vielleicht überraschend, dass eine Konvertierung von einem abgeleiteten Typ in einem seiner Basistypen erweitern ist. Die Ausrichtung ist, dass der abgeleitete Typ alle Member des Basistyps, enthält damit es als eine Instanz des Basistyps qualifiziert. In der entgegengesetzten Richtung enthält der Basistyp nicht vom abgeleiteten Typ definierten neuen Member.  
  
 Erweiternde Konvertierungen zur Laufzeit immer erfolgreich und nie Datenverlust verursachen. Immer durchführen können sie implizit, ob die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) wird der Typ, wechseln Sie zur Prüfung `On` oder `Off`.  
  
## <a name="narrowing-conversions"></a>Einschränkende Konvertierungen  
 Die standardmäßigen einschränkenden Konvertierungen umfassen Folgendes:  
  
-   Die umgekehrte Richtung der erweiternden Konvertierungen in der vorherigen Tabelle (außer, dass jeder Typ selbst erweitert)  
  
-   Konvertierungen zwischen [boolesche](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) und alle numerischen Typen  
  
-   Beim Konvertieren von numerischen Typ in einen Enumerationstyp (`Enum`)  
  
-   Konvertierungen zwischen [Zeichenfolge](../../../../visual-basic/language-reference/data-types/string-data-type.md) und alle numerischen Typen, `Boolean`, oder [Datum](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Geben Sie zur Konvertierung von einem Datentyp oder das Objekt um einen abgeleiteten Typ  
  
 Einschränkende Konvertierungen nicht immer erfolgreich zur Laufzeit und können fehlschlagen oder Datenverlust verursachen. Ein Fehler tritt auf, wenn der Zieldatentyp nicht den konvertierten Wert empfangen kann. Beispielsweise kann eine numerische Konvertierung zu einem Überlauf führen. Der Compiler lässt keine auszuführenden einschränkende Konvertierungen implizit, wenn Sie die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) legt die Schalter für die Typprüfung `Off`.  
  
> [!NOTE]
>  Der Fehler für einschränkende Konvertierung wird unterdrückt für Konvertierungen von den Elementen in einer `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable. Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" im [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Einschränkende Konvertierungen verwenden  
 Verwenden Sie eine einschränkende Konvertierung, wenn Sie wissen, dass der Quellwert in den Zieldatentyp ohne Fehler oder Datenverlust konvertiert werden kann. Angenommen, Sie haben eine `String` wissen Sie entweder "True" oder "False" enthält, können Sie die `CBool` Schlüsselwort umzuwandeln `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Ausnahmen während der Konvertierung  
 Da immer erweiternde Konvertierungen erfolgreich ausgeführt werden, werden sie keine Ausnahmen auslösen. Die folgenden Ausnahmen einschränkende Konvertierungen, wenn sie sich nicht am häufigsten ausgelöst werden:  
  
-   <xref:System.InvalidCastException>– Wenn keine Konvertierung zwischen den beiden Typen definiert ist</xref:System.InvalidCastException>  
  
-   <xref:System.OverflowException>– (nur bei ganzzahligen Typen) Wenn der konvertierte Wert für den Zieltyp zu groß ist.</xref:System.OverflowException>  
  
 Wenn eine Klasse oder Struktur definiert ein [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) als Operator für die Konvertierung in oder aus dieser Klasse oder Struktur an, die `CType` geeignete Ausnahmen auslösen können. Darüber hinaus, `CType` Aufrufen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Funktionen oder [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Methoden, die wiederum verschiedene Ausnahmen auslösen können.  
  
## <a name="changes-during-reference-type-conversions"></a>Änderungen, die während der Verweis Typumwandlungen  
 Eine Konvertierung von einem *Referenztyp* wird nur der Zeiger auf den Wert. Der Wert selbst werden nicht kopiert oder in keiner Weise geändert. Das einzige, das ändern können ist der Datentyp der Variablen den Zeiger. Im folgenden Beispiel wird der Datentyp von deren Basisklasse aus der abgeleiteten Klasse konvertiert das Objekt, dem nun beide Variablen verweisen ist allerdings nicht geändert.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
