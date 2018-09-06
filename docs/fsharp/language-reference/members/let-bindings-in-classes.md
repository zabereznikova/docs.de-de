---
title: let-Bindungen in Klassen (F#)
description: Erfahren Sie, wie Sie private Felder und private Funktionen für F#-Klassen definieren, mit "let"-Bindungen in der Klassendefinition.
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866792"
---
# <a name="let-bindings-in-classes"></a>let-Bindungen in Klassen

Sie können die privaten Felder und private Funktionen für F#-Klassen definieren, mit `let` Bindungen in der Klassendefinition.

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

Sie können auch die `val` Schlüsselwort, um ein privates Feld erstellen. Bei Verwendung der `val` -Schlüsselwort, das Feld ist kein Wert zugewiesen, wenn das Objekt wird erstellt, jedoch mit einem Standardwert initialisiert wird. Weitere Informationen finden Sie unter [explizite Felder: das Val Schlüsselwort](explicit-fields-the-val-keyword.md).

Sie können auch private Felder in einer Klasse definieren, indem Sie eine Elementdefinition und durch Hinzufügen des Schlüsselworts `private` der Definition. Dies kann nützlich sein, wenn Sie erwarten, um den Zugriff auf ein Element zu ändern, ohne den Code umzuschreiben. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
- [`do`-Bindungen in Klassen](do-bindings-in-classes.md)
- [`let` Bindungen](../functions/let-bindings.md)
