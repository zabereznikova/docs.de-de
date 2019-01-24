---
title: Erweiternde und eingrenzende Konvertierungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: d1b573dbafbead20330a4fd0f62e8f21f27dce81
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610928"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Erweiternde und eingrenzende Konvertierungen (Visual Basic)
Ein wichtiger Aspekt bei einer typkonvertierung ist, ob das Ergebnis der Konvertierung innerhalb des Bereichs des Ziel-Datentyps.  
  
 Ein *eine erweiternde Konvertierung* ändert einen Wert in einen Datentyp, die für jeden möglichen Wert der ursprünglichen Daten ermöglichen.  Erweiternde Konvertierungen den Quellwert beibehalten, aber es können die Darstellung ändern. Dies geschieht, wenn Sie einen ganzzahligen Typ zu konvertieren `Decimal`, oder von `Char` zu `String`.  
  
 Eine *einschränkende* Konvertierung ändert einen Wert in einen Datentyp, der möglicherweise nicht in der Lage ist, alle möglichen Werte zu speichern. Zum Beispiel wird ein Dezimalstellenwert gerundet, bei der Konvertierung in einen ganzzahligen Typ und einen numerischen Typ konvertiert wird, um `Boolean` wird reduziert, entweder `True` oder `False`.  
  
## <a name="widening-conversions"></a>Erweiterungskonvertierungen  
 Die folgende Tabelle zeigt die Standard-erweiternde Konvertierungen.  
  
|Datentyp|Datentypen erweitert <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Einem Enumerationstyp ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Die zugrunde liegenden ganzzahligen Typ und einen beliebigen Typ, der zugrunde liegenden Typ erweitert wird.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char`-Array|`Char` Array `String`|  
|Beliebiger Typ|[Objekt](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Alle abgeleiteten Typ|Alle Basistyp, die von der sie abgeleitet ist <sup>3</sup>.|  
|Beliebiger Typ|Jede Schnittstelle, die er implementiert.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Jeder Datentyp oder ein Objekttyp.|  
  
 <sup>1</sup> per Definition an, die für jeden Datentyp an sich selbst erweitert wird.  
  
 <sup>2</sup> Konvertierungen von `Integer`, `UInteger`, `Long`, `ULong`, oder `Decimal` zu `Single` oder `Double` kann dazu führen, dass Genauigkeit verloren gehen, niemals in der Verlust der Größe. In diesem Sinne fallen sie keine Informationen verloren gehen.  
  
 <sup>3</sup> es vielleicht überraschend, dass die Konvertierung eines abgeleiteten Typs auf einen der Basistypen erweiternde Konvertierung ist. Die Ausrichtung ist, dass der abgeleitete Typ alle Member des Basistyps, enthält damit es als eine Instanz des Basistyps qualifiziert. In die entgegengesetzte Richtung enthält der Basistyp keine neuen Member, die vom abgeleiteten Typ definiert.  
  
 Erweiternde Konvertierungen immer erfolgreich, zur Laufzeit und verursachen keine Daten verloren gehen. Immer durchführen können sie implizit, ob die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) bestimmt den Typ an, wechseln Sie zur Überprüfung `On` oder `Off`.  
  
## <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen  
 Die standardmäßige einschränkenden Konvertierungen umfassen Folgendes:  
  
-   Die umgekehrte erfahren Sie, wie der erweiternden Konvertierungen in der vorherigen Tabelle (außer, dass jeder Typ an sich selbst erweitert wird)  
  
-   Konvertierungen in beide Richtungen zwischen [booleschen](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) und alle numerischen Typen  
  
-   Konvertierungen von numerischen Typen in einen Enumerationstyp (`Enum`)  
  
-   Konvertierungen in beide Richtungen zwischen [Zeichenfolge](../../../../visual-basic/language-reference/data-types/string-data-type.md) und alle numerischen Typen, `Boolean`, oder [Datum](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Geben Sie die Konvertierungen von einem Datentyp oder das Objekt zu einem Typ abgeleitet wird  
  
 Einschränkende Konvertierungen nicht immer erfolgreich zur Laufzeit und können fehlschlagen oder Datenverlust verursachen. Ein Fehler tritt auf, wenn den konvertierte Wert nicht der Zieldatentyp erhalten kann. Beispielsweise kann eine numerische Konvertierung zu einem Überlauf führen. Der Compiler lässt nicht zum Durchführen von einschränkende Konvertierungen implizit, wenn die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) bestimmt den Typ an, wechseln Sie zur Überprüfung `Off`.  
  
> [!NOTE]
>  Der einschränkende Konvertierung-Fehler unterdrückt für Konvertierungen aus den Elementen in einem `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable. Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" in [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Verwenden Sie einschränkende Konvertierungen  
 Verwenden Sie eine einschränkende Konvertierung, wenn Sie wissen, dass sich der Quellwert in den Zieltyp für die Daten ohne Fehler oder Datenverlust konvertiert werden kann. Angenommen, Sie haben eine `String` , dass Sie wissen, entweder "True" oder "False" enthält, können Sie die `CBool` Schlüsselwort konvertiert `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Ausnahmen während der Konvertierung  
 Da immer erweiternde Konvertierungen erfolgreich ausgeführt werden, werden sie keine Ausnahmen auslösen. Einschränkende Konvertierungen, wenn ein Fehler auftritt, löst am häufigsten gelten folgenden Ausnahmen:  
  
-   <xref:System.InvalidCastException> Wenn keine Konvertierung zwischen den beiden Typen definiert ist  
  
-   <xref:System.OverflowException> – (nur bei ganzzahligen Typen), wenn der konvertierte Wert für den Zieltyp zu groß ist.  
  
 Wenn eine Klasse oder Struktur definiert eine [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) als Operator für die Konvertierung in oder aus dieser Klasse oder Struktur, dienen, `CType` können geeignete Ausnahmen auslösen. Darüber hinaus, `CType` kann Visual Basic-Funktionen aufrufen oder [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Methoden, die wiederum eine Vielzahl von Ausnahmen auslösen können.  
  
## <a name="changes-during-reference-type-conversions"></a>Änderungen bei der Verweistypkonvertierungen  
 Eine Konvertierung von einem *Verweistyp* wird nur der Zeiger auf den Wert. Der Wert selbst werden nicht kopiert oder in einer Weise geändert. Das einzige, das geändert werden kann ist den Datentyp der Variablen den Zeiger enthält. Klicken Sie im folgenden Beispiel der Datentyp aus der abgeleiteten Klasse konvertiert wird, mit der Basisklasse, aber das Objekt, dem beide Variablen zeigen jetzt auf bleibt unverändert.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Siehe auch
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
