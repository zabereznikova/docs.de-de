---
title: Boolesche Operatoren (F#)
description: Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0b11b5133b02b6f507c7886b2fbaebf30abf46cb
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="boolean-operators"></a>Boolesche Operatoren

Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Programmiersprache f#.


## <a name="summary-of-boolean-operators"></a>Zusammenfassung der booleschen Operatoren
In der folgenden Tabelle zusammengefasst, die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind. Der einzige von diesen Operatoren unterstützte Typ ist der `bool` Typ.

|Operator|Beschreibung|
|--------|-----------|
|`not`|Boolesche negation|
|<code>&#124;&#124;</code>|Boolesche OR|
|`&&`|Boolesche AND|

Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auswerten, nur bei Bedarf das Gesamtergebnis des Ausdrucks bestimmt. Der zweite Ausdruck, der die `&&` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck des der `||` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `false`.

## <a name="see-also"></a>Siehe auch
[Bitweise Operatoren](bitwise-operators.md)

[Arithmetische Operatoren](arithmetic-operators.md)

[Symbol- und Operatorenreferenz](index.md)
