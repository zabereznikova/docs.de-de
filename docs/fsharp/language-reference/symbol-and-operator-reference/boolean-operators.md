---
title: Boolesche Operatoren (F#)
description: "Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
