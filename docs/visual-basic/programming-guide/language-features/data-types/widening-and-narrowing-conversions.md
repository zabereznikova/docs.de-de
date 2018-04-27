---
title: Erweiternde und eingrenzende Konvertierungen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 960b4e4c7184309b6a84247d86fb94ccb2faf877
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Erweiternde und eingrenzende Konvertierungen (Visual Basic)
Ein wichtiger Aspekt mit einer Typumwandlung ist, ob das Ergebnis der Konvertierung innerhalb des Bereichs des Zieltyps Daten ist.  
  
 Ein *erweiternde Konvertierung* ändert einen Wert in einen Datentyp, die für jeden möglichen Wert der ursprünglichen Daten zulassen kann.  Erweiterungskonvertierungen beibehalten des Quellwerts. jedoch kann seine Darstellung zu ändern. Dies geschieht, wenn Sie einen ganzzahligen Typ zu konvertieren `Decimal`, oder von `Char` auf `String`.  
  
 Eine *einschränkende* Konvertierung ändert einen Wert in einen Datentyp, der möglicherweise nicht in der Lage ist, alle möglichen Werte zu speichern. Beispielsweise wird ein Dezimalstellenwert gerundet, bei der Konvertierung in einen ganzzahligen Typ und einen numerischen Typ konvertiert wird, um `Boolean` wird reduziert, entweder `True` oder `False`.  
  
## <a name="widening-conversions"></a>Erweiterungskonvertierungen  
 Die folgende Tabelle zeigt die erweiterungskonvertierungen Standard.  
  
|Datentyp|Wird erweitert, um Datentypen <sup>1</sup>|  
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
|Alle Aufzählungstyp ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Die zugrunde liegenden Ganzzahltyp und beliebigen Typs, der der zugrunde liegenden Typ erweitert werden kann.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char`-Array|`Char` Array, `String`|  
|Beliebiger Typ|[Objekt](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Alle abgeleiteten Typ|Alle Basistypen, die von der sie abgeleitet ist <sup>3</sup>.|  
|Beliebiger Typ|Eine beliebige Schnittstelle implementiert.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Jeder beliebige Datentyp oder der Objekttyp.|  
  
 <sup>1</sup> per Definition jedes-Datentyp wird auf sich selbst.  
  
 <sup>2</sup> Konvertierungen von `Integer`, `UInteger`, `Long`, `ULong`, oder `Decimal` auf `Single` oder `Double` wird unter Umständen in einem Genauigkeitsverlust, aber nie in Verlust der Größe. In diesem Sinn ist kein Verlust von Typinformationen erforderlich.  
  
 <sup>3</sup> scheint es überrascht, dass die Konvertierung eines abgeleiteten Typs auf einen der Basistypen erweiternde Konvertierung ist. Die Ausrichtung ist, dass der abgeleitete Typ alle Member des Basistyps, enthält damit es als eine Instanz des Basistyps qualifiziert. In die entgegengesetzte Richtung enthält der Basistyp keiner neuer Member, die vom abgeleiteten Typ definiert.  
  
 Erweiternde Konvertierungen zur Laufzeit immer erfolgreich sein und Verlust von Daten niemals anfallen. Sie können immer ausführen, werden implizit, gibt an, ob die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) legt die typüberprüfung zu wechseln `On` oder `Off`.  
  
## <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen  
 Die standardmäßigen einschränkenden Konvertierungen umfassen Folgendes:  
  
-   Die umgekehrte Richtung erweiternde Konvertierungen in den vorherigen Tabelle (außer, dass jeder Typ an sich selbst erweitert)  
  
-   Konvertierungen in beide Richtungen zwischen [booleschen](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) und alle numerischen Typen  
  
-   Konvertierungen von numerischen Typen an ein beliebiges Aufzählungstyp (`Enum`)  
  
-   Konvertierungen in beide Richtungen zwischen [Zeichenfolge](../../../../visual-basic/language-reference/data-types/string-data-type.md) und alle numerischen Typen `Boolean`, oder [Datum](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Geben Sie die Konvertierungen von einem Datentyp oder das Objekt in einen Typ, der davon abgeleitete  
  
 Einschränkende Konvertierungen nicht immer erfolgreich ausgeführt werden Sie, zur Laufzeit und können fehlschlagen Sie oder verursachen Sie Datenverlust. Ein Fehler tritt auf, wenn der Zieldatentyp den konvertierten Wert empfangen kann. Beispielsweise kann eine numerische Konvertierung zu einem Überlauf führen. Der Compiler lässt nicht zu, Sie zum Durchführen von einschränkende Konvertierungen implizit, wenn die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) legt der Switch die typüberprüfung `Off`.  
  
> [!NOTE]
>  Die einschränkende Konvertierung Fehler unterdrückt für Konvertierungen von den Elementen in einem `For Each…Next` -Auflistung, um die Loop-Steuerelementvariable. Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Einschränkende Konvertierungen verwenden  
 Verwenden Sie eine einschränkende Konvertierung, wenn Sie wissen, dass der Quellwert in den Zieldatentyp ohne Fehler oder Datenverlust konvertiert werden kann. Angenommen, Sie haben eine `String` , dass Sie wissen, entweder "True" oder "False" enthält, können Sie die `CBool` Schlüsselwort umzuwandeln `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Ausnahmen während der Konvertierung  
 Da immer erweiternde Konvertierungen erfolgreich ausgeführt werden, lösen sie keine Ausnahmen. Die folgenden Ausnahmen einschränkende Konvertierungen, wenn diese nicht am häufigsten ausgelöst werden:  
  
-   <xref:System.InvalidCastException> – Wenn keine Konvertierung zwischen den beiden Typen definiert ist  
  
-   <xref:System.OverflowException> – (nur bei ganzzahligen Typen) Wenn der konvertierte Wert für den Zieltyp zu groß ist.  
  
 Wenn eine Klasse oder Struktur definiert eine [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) als ein Konvertierungsoperator zu oder von dieser Klasse oder Struktur, dienen, `CType` geeignete Ausnahmen auslösen können. Darüber hinaus, `CType` möglicherweise Visual Basic-Funktionen aufrufen oder [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Methoden, die wiederum eine Vielzahl von Ausnahmen auslösen können.  
  
## <a name="changes-during-reference-type-conversions"></a>Änderungen bei Verweis Typkonvertierungen  
 Eine Konvertierung von einem *Verweistyp* kopiert nur die Zeiger auf den Wert. Der Wert selbst wird weder kopiert noch in keiner Weise geändert. Das einzige, das sich ändern kann ist den Datentyp der Variablen den Zeiger. Im folgenden Beispiel der Datentyp wird von der abgeleiteten Klasse von deren Basisklasse umgewandelt, aber das Objekt, das beide Variablen jetzt auf bleibt unverändert.  
  
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
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
