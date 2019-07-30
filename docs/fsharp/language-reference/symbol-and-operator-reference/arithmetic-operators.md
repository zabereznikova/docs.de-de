---
title: Arithmetische Operatoren
description: Erfahren Sie, bis die arithmetischen Operatoren, die in der Programmiersprache F# verfügbar sind.
ms.date: 04/04/2018
ms.openlocfilehash: b783a0134541f11f06dde83af97676699b797da1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630785"
---
# <a name="arithmetic-operators"></a>Arithmetische Operatoren

Dieses Thema beschreibt die arithmetische Operatoren, die in F# verfügbar sind.

## <a name="summary-of-binary-arithmetic-operators"></a>Zusammenfassung der binären arithmetischen Operatoren

In der folgenden Tabelle sind die binären arithmetischen Operatoren zusammengefasst, die für ganzzahlige Typen und Gleit Komma Typen ohne Boxed verfügbar sind.

|Binärer Operator|Notizen|
|---------------|-----|
|`+`(Addition, plus)|Benem. Mögliche Überlauf Bedingung, wenn Zahlen addiert werden und die Summe den maximalen absoluten Wert überschreitet, der vom-Typ unterstützt wird.|
|`-`(Subtraktion, minus)|Benem. Mögliche Unterlauf Bedingung, wenn nicht signierte Typen subtrahiert werden, oder wenn Gleit Komma Werte zu klein sind, um durch den Typ dargestellt zu werden.|
|`*`(Multiplikation, Uhrzeiten)|Benem. Mögliche Überlauf Bedingung, wenn Zahlen multipliziert werden und das Produkt den maximalen absoluten Wert überschreitet, der vom Typ unterstützt wird.|
|`/`(Division, dividiert durch)|Division durch Null bewirkt einen <xref:System.DivideByZeroException> für ganzzahlige Typen. Für Gleit Komma Typen bietet die Division durch 0 die besonderen Gleit Komma Werte `+Infinity` oder. `-Infinity` Es gibt auch eine unter Fluss Bedingung, wenn eine Gleit Komma Zahl zu klein ist, um durch den Typ dargestellt zu werden.|
|`%`(Restwert, REM)|Gibt den Rest einer Divisions Operation zurück. Das Vorzeichen des Ergebnisses ist das gleiche wie das Vorzeichen des ersten Operanden.|
|`**`(exponentiell, von)|Mögliche Überlauf Bedingung, wenn das Ergebnis den maximalen absoluten Wert für den Typ überschreitet.<br /><br />Der exponentiations Operator funktioniert nur mit Gleit Komma Typen.|

## <a name="summary-of-unary-arithmetic-operators"></a>Zusammenfassung der unären arithmetischen Operatoren

In der folgenden Tabelle werden die unären arithmetischen Operatoren zusammengefasst, die für ganzzahlige Typen und Gleit Komma Typen verfügbar sind.

|Unärer Operator|Hinweise|
|--------------|-----|
|`+`positive|Kann auf einen beliebigen arithmetischen Ausdruck angewendet werden. Das Vorzeichen des Werts wird nicht geändert.|
|`-`(Negation, negativ)|Kann auf einen beliebigen arithmetischen Ausdruck angewendet werden. Ändert das Vorzeichen des Werts.|

Das Verhalten bei Überlauf oder Unterlauf für ganzzahlige Typen besteht darin, zu umschließen. Dies führt zu einem falschen Ergebnis. Ein ganzzahliger Überlauf ist ein potenziell schwerwiegendes Problem, das zu Sicherheitsproblemen beitragen kann, wenn Software nicht in das Konto geschrieben wird. Wenn dies für Ihre Anwendung von Bedeutung ist, können Sie die überprüften Operatoren in in `Microsoft.FSharp.Core.Operators.Checked`Erwägung gezogen.

## <a name="summary-of-binary-comparison-operators"></a>Zusammenfassung der binären Vergleichs Operatoren

In der folgenden Tabelle sind die binären Vergleichs Operatoren aufgeführt, die für ganzzahlige Typen und Gleit Komma Typen verfügbar sind. Diese Operatoren geben Werte vom `bool`Typ zurück.

Gleit Komma Zahlen sollten niemals direkt auf Gleichheit verglichen werden, da die IEEE-Gleit Komma Darstellung keine genaue Gleichheits Operation unterstützt. Zwei Zahlen, die Sie leicht überprüfen können, indem Sie den Code überprüfen, verfügen möglicherweise über unterschiedliche bitdarstellungen.

|Operator|Hinweise|
|--------|-----|
|`=`(Gleichheit, ist gleich)|Dabei handelt es sich nicht um einen Zuweisungs Operator. Sie wird nur für Vergleiche verwendet. Dabei handelt es sich um einen generischen Operator.|
|`>`(größer als)|Dabei handelt es sich um einen generischen Operator.|
|`<`(kleiner als)|Dabei handelt es sich um einen generischen Operator.|
|`>=`(größer als oder ist)|Dabei handelt es sich um einen generischen Operator.|
|`<=`(kleiner als oder ist)|Dabei handelt es sich um einen generischen Operator.|
|`<>`(ungleich)|Dabei handelt es sich um einen generischen Operator.|

## <a name="overloaded-and-generic-operators"></a>Überladene und generische Operatoren

Alle in diesem Thema behandelten Operatoren sind im Namespace **Microsoft. FSharp. Core. Operators** definiert. Einige der Operatoren werden mit statisch aufgelösten Typparametern definiert. Dies bedeutet, dass für jeden bestimmten Typ, der mit diesem Operator funktioniert, individuelle Definitionen vorhanden sind. Alle unären und binären arithmetischen und bitweisen Operatoren sind in dieser Kategorie. Die Vergleichs Operatoren sind generisch und funktionieren daher mit allen Typen, nicht nur mit primitiven arithmetischen Typen. Diskriminierte Union-und Daten Satz Typen verfügen über eigene benutzerdefinierte Implementierungen, F# die vom Compiler generiert werden. Klassentypen verwenden die- <xref:System.Object.Equals%2A>Methode.

Die generischen Operatoren sind anpassbar. Zum Anpassen der Vergleichsfunktionen überschreiben <xref:System.Object.Equals%2A> Sie, um einen eigenen benutzerdefinierten Gleichheits Vergleich bereit <xref:System.IComparable>zustellen, und implementieren Sie dann. Die <xref:System.IComparable?displayProperty=nameWithType> -Schnittstelle verfügt über eine einzelne <xref:System.IComparable.CompareTo%2A> Methode, die-Methode.

## <a name="operators-and-type-inference"></a>Operatoren und Typrückschluss

Die Verwendung eines Operators in einem Ausdruck schränkt den Typrückschluss für diesen Operator ein. Außerdem verhindert die Verwendung von Operatoren die automatische Generalisierung, da die Verwendung von Operatoren einen arithmetischen Typ impliziert. Wenn keine anderen Informationen vorhanden sind, leitet der F# Compiler `int` den Typ von arithmetischen Ausdrücken ab. Sie können dieses Verhalten überschreiben, indem Sie einen anderen Typ angeben. Folglich werden die Argument `function1` Typen und der Rückgabetyp von im folgenden Code als abgeleitet `int`, aber die Typen für `function2` werden als abgeleitet. `float`

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]

## <a name="see-also"></a>Siehe auch

- [Symbol- und Operatorenreferenz](index.md)
- [Operatorüberladung](../operator-overloading.md)
- [Bitweise Operatoren](bitwise-operators.md)
- [Boolesche Operatoren](boolean-operators.md)
