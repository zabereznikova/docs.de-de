---
title: Widening and Narrowing Conversions
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
ms.openlocfilehash: 72cc1a2179db4f057c45cd2ff4de82a6437d6b58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348696"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Erweiternde und eingrenzende Konvertierungen (Visual Basic)
Ein wichtiger Aspekt bei einer Typkonvertierung ist, ob das Ergebnis der Konvertierung innerhalb des Bereichs des Ziel Datentyps liegt.  
  
 Eine *erweiternde Konvertierung* ändert einen Wert in einen Datentyp, der einen möglichen Wert der ursprünglichen Daten zulässt.  Erweiternde Konvertierungen behalten den Quellwert bei, können jedoch seine Darstellung ändern. Dies tritt auf, wenn Sie einen ganzzahligen Typ in `Decimal`oder von `Char` in `String`konvertieren.  
  
 Eine *einschränkende* Konvertierung ändert einen Wert in einen Datentyp, der möglicherweise nicht in der Lage ist, alle möglichen Werte zu speichern. Beispielsweise wird ein Bruch Wert gerundet, wenn er in einen ganzzahligen Typ konvertiert wird, und ein numerischer Typ, der in `Boolean` konvertiert wird, wird auf `True` oder `False`reduziert.  
  
## <a name="widening-conversions"></a>Erweiternde Konvertierungen  
 In der folgenden Tabelle sind die standarderweiternde Konvertierungen aufgeführt.  
  
|Datentyp|Wird zu den Datentypen <sup>1</sup> erweitert.|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single``Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Beliebiger Enumerationstyp[(](../../../../visual-basic/language-reference/statements/enum-statement.md)Enumeration)|Der zugrunde liegende ganzzahlige Typ und alle Typen, auf die sich der zugrunde liegende Typ ausdehnt.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char`-Array|`Char` Array `String`|  
|Beliebiger Typ|[Objekt](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Abgeleiteter Typ|Jeder Basistyp, von dem er abgeleitet ist <sup>3</sup>.|  
|Beliebiger Typ|Jede Schnittstelle, die Sie implementiert.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Jeder Datentyp oder Objekttyp.|  
  
 <sup>1</sup> definitionsgemäß wird jeder Datentyp zu sich selbst erweitert.  
  
 <sup>2</sup> Konvertierungen von `Integer`, `UInteger`, `Long`, `ULong`oder `Decimal` zu `Single` oder `Double` können zu einem Genauigkeits Verlust führen, jedoch nie zu einem Verlust der Größe. In diesem Sinne entstehen keine Informationsverluste.  
  
 <sup>3</sup> es mag überraschend erscheinen, dass eine Konvertierung von einem abgeleiteten Typ in einen seiner Basis Typen erweitert wird. Die Begründung ist, dass der abgeleitete Typ alle Member des Basistyps enthält, sodass er als Instanz des Basistyps qualifiziert ist. In umgekehrter Richtung enthält der Basistyp keine neuen Member, die vom abgeleiteten Typ definiert werden.  
  
 Erweiternde Konvertierungen sind immer zur Laufzeit erfolgreich und verursachen niemals Datenverluste. Sie können Sie immer implizit ausführen, unabhängig davon, ob die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) den Schalter für die Typüberprüfung auf `On` oder `Off`festlegt.  
  
## <a name="narrowing-conversions"></a>Einschränkende Konvertierungen  
 Die standardeinschränkenden Konvertierungen umfassen Folgendes:  
  
- Die umgekehrten Richtungen der erweiternden Konvertierungen in der vorangehenden Tabelle (mit der Ausnahme, dass jeder Typ zu sich selbst umvergrößert wird)  
  
- Konvertierungen in beide Richtungen zwischen [booleschen](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) Werten und beliebigen numerischen Typen  
  
- Konvertierungen von beliebigen numerischen Typen in beliebige Enumerationstypen (`Enum`)  
  
- Konvertierungen in beide Richtungen zwischen [Zeichen](../../../../visual-basic/language-reference/data-types/string-data-type.md) folgen und numerischen Typen, `Boolean`oder [Datums](../../../../visual-basic/language-reference/data-types/date-data-type.md) Angaben  
  
- Konvertierungen von einem Datentyp oder Objekttyp in einen von ihm abgeleiteten Typ  
  
 Einschränkende Konvertierungen sind zur Laufzeit nicht immer erfolgreich und können fehlschlagen oder Datenverluste verursachen. Ein Fehler tritt auf, wenn der Ziel Datentyp den konvertierten Wert nicht empfangen kann. Beispielsweise kann eine numerische Konvertierung zu einem Überlauf führen. Der Compiler gestattet Ihnen nicht, einschränkende Konvertierungen implizit auszuführen, es sei denn, die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) legt den Schalter für die Typüberprüfung auf `Off`fest.  
  
> [!NOTE]
> Der einschränkende Konvertierungs Fehler wird für Konvertierungen der Elemente in einer `For Each…Next` Auflistung in die Schleifen Steuerungs Variable unterdrückt. Weitere Informationen und Beispiele finden Sie im Abschnitt "einschränkende Konvertierungen" unter [for each... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Verwendung von einschränkenden Konvertierungen  
 Sie verwenden eine einschränkende Konvertierung, wenn Sie wissen, dass der Quellwert ohne Fehler oder Datenverlust in den Ziel Datentyp konvertiert werden kann. Wenn Sie z. b. eine `String` haben, dass Sie wissen, dass Sie entweder "true" oder "false" enthält, können Sie das `CBool`-Schlüsselwort verwenden, um es in `Boolean`zu konvertieren.  
  
## <a name="exceptions-during-conversion"></a>Ausnahmen während der Konvertierung  
 Da erweiternde Konvertierungen immer erfolgreich sind, lösen Sie keine Ausnahmen aus. Einschränkende Konvertierungen, wenn Sie fehlschlagen, lösen in der Regel die folgenden Ausnahmen aus:  
  
- <xref:System.InvalidCastException> –, wenn zwischen den beiden Typen keine Konvertierung definiert ist.  
  
- <xref:System.OverflowException> – (nur ganzzahlige Typen), wenn der konvertierte Wert für den Zieltyp zu groß ist  
  
 Wenn eine Klasse oder Struktur eine [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) definiert, die als Konvertierungs Operator für diese Klasse oder Struktur fungieren soll, kann diese `CType` eine beliebige Ausnahme auslösen, die Sie als geeignet erachtet. Außerdem kann diese `CType` Visual Basic Funktionen oder .NET Framework Methoden aufzurufen, die wiederum eine Vielzahl von Ausnahmen auslösen könnten.  
  
## <a name="changes-during-reference-type-conversions"></a>Änderungen bei Verweistyp Konvertierungen  
 Bei einer Konvertierung von einem *Verweistyp* wird nur der Zeiger auf den Wert kopiert. Der Wert selbst wird weder kopiert noch auf irgendeine Weise geändert. Das einzige, was geändert werden kann, ist der Datentyp der Variablen, die den Zeiger enthält. Im folgenden Beispiel wird der Datentyp von der abgeleiteten Klasse in seine Basisklasse konvertiert, aber das Objekt, auf das beide Variablen nun zeigen, ist unverändert.  
  
```vb  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
