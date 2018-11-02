---
title: Arithmetische Operatoren (F#)
description: Erfahren Sie, bis die arithmetischen Operatoren, die in der Programmiersprache f# verfügbar sind.
ms.date: 04/04/2018
ms.openlocfilehash: 008aa84b8736bb3a734ce8bb9713d34c17f1b76e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45597427"
---
# <a name="arithmetic-operators"></a>Arithmetische Operatoren

Dieses Thema beschreibt die arithmetische Operatoren, die in f# verfügbar sind.

## <a name="summary-of-binary-arithmetic-operators"></a>Zusammenfassung der binären arithmetische Operatoren

Die folgende Tabelle enthält die binäre arithmetischen Operatoren, die für Unboxing ganzzahlige Typen und Gleitkommatypen verfügbar sind.

|Binärer operator|Notizen|
|---------------|-----|
|`+` (außerdem plus)|Deaktiviert. Wenn Zahlen addiert werden. möglicher Überlauf und die Summe überschreitet den maximalen Absolutwert vom Typ unterstützt.|
|`-` (Subtraktion minus)|Deaktiviert. Mögliche Unterlauf Bedingung, wenn Typen ohne Vorzeichen subtrahiert werden, oder wenn es sich bei Gleitkommazahlen-Punktwerte zu klein, um durch den Typ dargestellt werden.|
|`*` (Multiplikation, wie oft)|Deaktiviert. Möglicher Überlauf bei Zahlen multipliziert werden und das Produkt überschreitet den maximalen Absolutwert vom Typ unterstützt.|
|`/` (Division, geteilt durch)|Division durch 0 (null) bewirkt, dass eine <xref:System.DivideByZeroException> für ganzzahlige Typen. Für die Gleitkommatypen Division durch 0 (null) erhalten Sie die spezielle Gleitkommawerte `+Infinity` oder `-Infinity`. Es ist auch eine Bedingung möglich Unterlauf, wenn eine Gleitkommazahl vom Typ dargestellt werden zu klein ist.|
|`%` (Rest, Rem)|Gibt den Rest einer Division zurück. Das Vorzeichen des Ergebnisses ist identisch mit das Vorzeichen des ersten Operanden.|
|`**` (Potenzierung, hoch)|Möglicher Überlauf, wenn das Ergebnis das Absolute Maximum für den Typ überschreitet.<br /><br />Der Potenzierungsoperator funktioniert nur mit Gleitkomma-Datentypen.|

## <a name="summary-of-unary-arithmetic-operators"></a>Zusammenfassung der unäre arithmetische Operatoren

Die folgende Tabelle enthält die unären arithmetischen Operatoren, die für ganzzahlige Typen und Gleitkommatypen verfügbar sind.

|Unäroperator|Hinweise|
|--------------|-----|
|`+` (positiv)|Kann auf alle arithmetischen Ausdruck angewendet werden. Die Vorzeichen des Werts wird nicht geändert werden.|
|`-` (Negation, negativ)|Kann auf alle arithmetischen Ausdruck angewendet werden. Ändert das Vorzeichen des Werts.|
Das Verhalten bei einem Überlauf oder Unterlauf für ganzzahlige Typen ist um fließen. Dies führt zu ein falsches Ergebnis. Ganzzahlüberlauf ist eine ernsthafte Probleme verursachen, die für Sicherheitsprobleme verursachen können, wenn die Software nicht geschrieben wird, um es zu berücksichtigen. Ist dies ein Problem für Ihre Anwendung, erwägen Sie die Verwendung der überprüften Operatoren in `Microsoft.FSharp.Core.Operators.Checked`.

## <a name="summary-of-binary-comparison-operators"></a>Zusammenfassung der binäre Vergleichsoperatoren

Die folgende Tabelle zeigt die binäre Vergleichsoperatoren, die für ganzzahlige Typen und Gleitkommatypen verfügbar sind. Diese Operatoren Rückgabewerte des Typs `bool`.

Gleitkommazahlen sollten nie direkt für gleich, verglichen werden, da der IEEE-gleitkommadarstellung einen exakte Übereinstimmung-Vorgang nicht unterstützt. Zwei Zahlen, die Sie ganz einfach überprüfen können, um gleich zu sein, durch den Code überprüfen möglicherweise tatsächlich anderen Bitmustern Darstellungen.

|Operator|Hinweise|
|--------|-----|
|`=` (Gleichheit, Equals)|Dies ist kein Zuweisungsoperator. Es wird nur für den Vergleich verwendet. Dies ist ein generischer Operator.|
|`>` (größer als)|Dies ist ein generischer Operator.|
|`<` (kleiner als)|Dies ist ein generischer Operator.|
|`>=` (größer als oder gleich)|Dies ist ein generischer Operator.|
|`<=` (kleiner als oder gleich)|Dies ist ein generischer Operator.|
|`<>` (ungleich)|Dies ist ein generischer Operator.|

## <a name="overloaded-and-generic-operators"></a>Überladene und generische Operatoren

Alle Operatoren in diesem Thema erläutert werden definiert, der **Microsoft.FSharp.Core.Operators** Namespace. Einige der Operatoren werden mithilfe von Statisch aufgelöste Typparameter definiert. Dies bedeutet, dass es einzelnen Definitionen für den jeweiligen, die mit dieser Operator funktioniert. Alle unären und binären arithmetische und bitweise Operatoren werden in dieser Kategorie. Die Vergleichsoperatoren sind generisch und funktioniert daher mit einem beliebigen Typ, nicht nur mit primitiven arithmetischen Typen. Unterscheidungs-Union "und" Record-Typen müssen ihre eigenen benutzerdefinierten Implementierungen, die von der F#-Compiler generiert werden. Verwenden Sie die Methode, Klassentypen <xref:System.Object.Equals%2A>.

Die generische Operatoren können angepasst werden. Informationen zum Anpassen der Vergleichsfunktionen überschreiben <xref:System.Object.Equals%2A> Ihre eigenen benutzerdefinierten Gleichheitsvergleich bereitstellen und implementieren Sie anschließend <xref:System.IComparable>. Die <xref:System.IComparable?displayProperty=nameWithType> Schnittstelle verfügt über eine einzelne Methode, die <xref:System.IComparable.CompareTo%2A> Methode.

## <a name="operators-and-type-inference"></a>Operatoren und Typrückschluss

Die Verwendung eines Operators in einem Ausdruck schränkt den Typrückschluss auf diesen Operator. Außerdem wird verhindert, dass die Verwendung Operatoren automatische Verallgemeinerung, da die Verwendung Operatoren einen arithmetischen Typ impliziert. In anderen Informationen vorhanden ist, leitet der F#-Compiler `int` als Typ des arithmetischen Ausdrücken. Sie können dieses Verhalten überschreiben, indem Sie einen anderen Typ angeben. Daher den Argumenttypen und der Rückgabetyp der `function1` in den folgenden Code werden als abgeleitet `int`, aber die Typen für `function2` abgeleitet werden, um werden `float`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]

## <a name="see-also"></a>Siehe auch

- [Symbol- und Operatorenreferenz](index.md)
- [Operatorüberladung](../operator-overloading.md)
- [Bitweise Operatoren](bitwise-operators.md)
- [Boolesche Operatoren](boolean-operators.md)
