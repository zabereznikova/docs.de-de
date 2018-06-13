---
title: Arithmetische Operatoren (F#)
description: Erfahren Sie, bis die arithmetischen Operatoren, die in der Programmiersprache f# verfügbar sind.
ms.date: 04/04/2018
ms.openlocfilehash: ead0bbd7fdad528b322f99eaf0f73638f060eb51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565937"
---
# <a name="arithmetic-operators"></a>Arithmetische Operatoren

Dieses Thema beschreibt die arithmetische Operatoren, die in der Programmiersprache f# verfügbar sind.

## <a name="summary-of-binary-arithmetic-operators"></a>Zusammenfassung der binäre arithmetische Operatoren
In der folgenden Tabelle werden die binären arithmetischen Operatoren, die für Unboxing Ganzzahl- und Gleitkommatypen verfügbaren zusammengefasst.

|Binärer operator|Notizen|
|---------------|-----|
|`+` (außerdem plus)|Deaktiviert. Möglichen Überlauf bei Zahlen addiert werden und die Summe überschreitet den maximalen Absolutwert vom Typ unterstützt.|
|`-` (Subtraktion, minus)|Deaktiviert. Mögliche Unterlauf Bedingung bei Typen ohne Vorzeichen subtrahiert werden, oder wenn Gleitkommawerte zu klein, um nach dem Typ dargestellt werden sind.|
|`*` (Multiplikation, wie oft)|Deaktiviert. Möglichen Überlauf bei Zahlen multipliziert werden, und das Produkt überschreitet den maximalen Absolutwert vom Typ unterstützt.|
|`/` (Division, dividiert durch)|Division durch Null festgelegt, wird eine <xref:System.DivideByZeroException> für ganzzahlige Typen. Für Gleitkommatypen, Division durch 0 (null) erhalten Sie spezielle Gleitkommawerte `+Infinity` oder `-Infinity`. Es ist auch eine mögliche Unterlauf Bedingung, wenn eine Gleitkommazahl vom Typ dargestellt werden zu klein ist.|
|`%` (Rest, Rem)|Gibt den Rest einer Division zurück. Die Vorzeichen des Ergebnisses werden das Vorzeichen des ersten Operanden identisch.|
|`**` (um die Leistungsfähigkeit von Potenzierung)|Möglicher Überlauf, wenn das Ergebnis den maximalen Absolutwert für den Typ überschreitet.<br /><br />Der Potenzierungsoperator kann nur mit Gleitkomma-Datentypen.|

## <a name="summary-of-unary-arithmetic-operators"></a>Zusammenfassung der unäre arithmetische Operatoren
In der folgenden Tabelle zusammengefasst, die unäre arithmetische Operatoren, die für Ganzzahl- und Gleitkommatypen verfügbar sind.


|Ein unäroperator|Hinweise|
|--------------|-----|
|`+` (positiv)|Kann auf jeden arithmetischen Ausdruck angewendet werden. Die Vorzeichen des Werts wird nicht geändert werden.|
|`-` (Negation, negativ)|Kann auf jeden arithmetischen Ausdruck angewendet werden. Ändert die Vorzeichen des Werts an.|
Das Verhalten bei einem Überlauf oder Unterlauf für ganzzahlige Typen ist umfließt. Dies bewirkt, dass ein falsches Ergebnis. Ganzzahlüberlauf ist ein potenziell schwerwiegendes Problem hin, das Sicherheitsprobleme verursachen können, wenn die Software nicht geschrieben wird, um es zu berücksichtigen. Wenn dies ein Problem für Ihre Anwendung ist, erwägen Sie checked-Operatoren in `Microsoft.FSharp.Core.Operators.Checked`.


## <a name="summary-of-binary-comparison-operators"></a>Zusammenfassung der binäre Vergleichsoperatoren
Die folgende Tabelle zeigt die binäre Vergleichsoperatoren, die für Ganzzahl- und Gleitkommatypen verfügbar sind. Diese Operatoren Rückgabewerte vom Typ `bool`.

Gleitkommazahlen sollten nie direkt für gleich, verglichen werden, da die IEEE-gleitkommadarstellung einen exakter Gleichheit-Vorgang nicht unterstützt. Zwei Zahlen, die Sie überprüfen können, um gleich zu sein, durch den Code überprüfen möglicherweise tatsächlich anderen Bitmustern Darstellungen.



|Operator|Hinweise|
|--------|-----|
|`=` (Gleichheit, gleich)|Dies ist kein Zuweisungsoperator. Es wird nur für den Vergleich verwendet. Dies ist ein generischer Operator.|
|`>` (größer als)|Dies ist ein generischer Operator.|
|`<` (kleiner als)|Dies ist ein generischer Operator.|
|`>=` (größer als oder gleich)|Dies ist ein generischer Operator.|
|`<=` (kleiner als oder gleich)|Dies ist ein generischer Operator.|
|`<>` (ungleich)|Dies ist ein generischer Operator.|

## <a name="overloaded-and-generic-operators"></a>Überladene und generische Operatoren
Alle in diesem Thema erläuterten Operatoren werden definiert, der **Microsoft.FSharp.Core.Operators** Namespace. Einige Operatoren sind mit statisch aufgelösten Typparametern definiert. Dies bedeutet, dass einzelne Definitionen für jeden bestimmten Typ, der mit diesem Operator funktioniert vorhanden sind. Alle unären und binären arithmetische und bitweise Operatoren werden in dieser Kategorie. Die Vergleichsoperatoren sind generisch, und funktioniert daher mit einem beliebigen Typ, nicht nur mit primitiven arithmetischen Typen. Unterscheidungs-Union und Datensatztypen haben eigene benutzerdefinierten Implementierungen, die von f#-Compiler generiert werden. Verwenden Sie die Methode, Klassentypen <xref:System.Object.Equals%2A>.

Die generischen Operatoren können angepasst werden. Überschreiben Sie zum Anpassen der Vergleichsfunktionen <xref:System.Object.Equals%2A> Geben Sie einen eigenen benutzerdefinierten Gleichheitsvergleich und anschließenden implementieren <xref:System.IComparable>. Die <xref:System.IComparable?displayProperty=nameWithType> Schnittstelle verfügt über eine einzelne Methode, die <xref:System.IComparable.CompareTo%2A> Methode.


## <a name="operators-and-type-inference"></a>Operatoren und Typrückschluss
Die Verwendung eines Operators in einem Ausdruck schränkt ein Typrückschluss auf diesen Operator. Darüber hinaus verhindert die Verwendung der Operatoren automatische Verallgemeinerung, da für die Verwendung von Operatoren einen arithmetischen Typ impliziert. In allen anderen Informationen vorhanden ist, leitet der f#-Compiler `int` als Typ des arithmetischen Ausdrücken. Sie können dieses Verhalten überschreiben, indem Sie einen anderen Typ angeben. Daher die Argumenttypen und der Rückgabetyp der `function1` in den folgenden Code wird davon ausgegangen `int`, sondern auch die Typen für `function2` abgeleitet werden `float`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]
    
## <a name="see-also"></a>Siehe auch
[Symbol- und Operatorenreferenz](index.md)

[Operatorüberladung](../operator-overloading.md)

[Bitweise Operatoren](bitwise-operators.md)

[Boolesche Operatoren](boolean-operators.md)
