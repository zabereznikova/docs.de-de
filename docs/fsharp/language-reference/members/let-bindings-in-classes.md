---
title: let-Bindungen in Klassen
description: Informationen zum Definieren der privaten Felder und private Funktionen für F# Klassen mit "let" Bindungen in der Klassendefinition.
ms.date: 05/16/2016
ms.openlocfilehash: 03dd583a141971284e6a8ddaad02272236cd1e4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903766"
---
# <a name="let-bindings-in-classes"></a>let-Bindungen in Klassen

Sie können private Felder und private Funktionen für definieren F# Klassen mit `let` Bindungen in der Klassendefinition.

## <a name="syntax"></a>Syntax

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Hinweise

Die vorherige Syntax wird nach den Klassendeklarationen Überschrift und Vererbung, aber vor Memberdefinitionen angezeigt. Die Syntax lautet wie `let` Bindungen außerhalb von Klassen, aber die Namen in einer Klasse definiert haben, einen Bereich, auf die Klasse beschränkt ist. Ein `let` Bindung erstellt wird, ein privates Feld bzw. die Funktion; zum Verfügbarmachen von Daten oder Funktionen zu einer Eigenschaft oder ein Membermethode öffentlich deklarieren.

Ein `let` Bindung, ist nicht statisch ist eine Instanz namens `let` Bindung. Instanz `let` Bindungen ausgeführt, wenn Objekte erstellt werden. Statische `let` Bindungen sind Teil der statische Initialisierer für die Klasse, die unbedingt ausführen, bevor Sie der Typ zuerst verwendet wird.

Der Code innerhalb der Instanz `let` der primäre Konstruktor Parameter von Bindungen verwendet werden kann.

Attribute und Zugriffsmodifizierer dürfen nicht auf `let` Bindungen in Klassen.

Die folgenden Codebeispiele veranschaulichen verschiedene Arten von `let` Bindungen in Klassen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

Die Ausgabe lautet wie folgt.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Alternative Möglichkeiten zum Erstellen von Feldern

Sie können auch die `val` Schlüsselwort, um ein privates Feld erstellen. Bei Verwendung der `val` -Schlüsselwort, das Feld ist kein Wert zugewiesen, wenn das Objekt wird erstellt, jedoch mit einem Standardwert initialisiert wird. Weitere Informationen finden Sie unter [explizite Felder: Das Val Schlüsselwort](explicit-fields-the-val-keyword.md).

Sie können auch private Felder in einer Klasse definieren, indem Sie eine Elementdefinition und durch Hinzufügen des Schlüsselworts `private` der Definition. Dies kann nützlich sein, wenn Sie erwarten, um den Zugriff auf ein Element zu ändern, ohne den Code umzuschreiben. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
- [`do`-Bindungen in Klassen](do-bindings-in-classes.md)
- [`let` Bindungen](../functions/let-bindings.md)