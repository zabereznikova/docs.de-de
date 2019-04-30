---
title: Boolesche Operatoren
description: Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache F# verfügbar sind.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925813"
---
# <a name="boolean-operators"></a>Boolesche Operatoren

Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Sprache F#.

## <a name="summary-of-boolean-operators"></a>Zusammenfassung der booleschen Operatoren

Die folgende Tabelle enthält die booleschen Operatoren, die in F# verfügbar sind. Ist der einzige Typ, der von diesen unterstützt die `bool` Typ.

|Operator|Beschreibung|
|--------|-----------|
|`not`|Boolesche negation|
|<code>&#124;&#124;</code>|Boolesche OR|
|`&&`|Boolesche AND|

Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auszuwerten, nur, wenn es um das Gesamtergebnis des Ausdrucks zu bestimmen, die erforderlich ist. Der zweite Ausdruck, der die `&&` Operator wird nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck, der die `||` Operator wird nur ausgewertet, wenn der erste Ausdruck ergibt `false`.

## <a name="see-also"></a>Siehe auch

- [Bitweise Operatoren](bitwise-operators.md)
- [Arithmetische Operatoren](arithmetic-operators.md)
- [Symbol- und Operatorenreferenz](index.md)