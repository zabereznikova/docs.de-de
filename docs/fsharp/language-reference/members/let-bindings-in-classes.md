---
title: let-Bindungen in Klassen
description: Erfahren Sie, wie Sie private Felder und private Funktionen F# für Klassen mithilfe von let-Bindungen in der Klassendefinition definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 0086d3a91f85395c2bd0555f978c5d951c363357
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627486"
---
# <a name="let-bindings-in-classes"></a>let-Bindungen in Klassen

Sie können private Felder und private Funktionen für F# Klassen definieren, indem `let` Sie in der Klassendefinition Bindungen verwenden.

## <a name="syntax"></a>Syntax

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Hinweise

Die vorherige Syntax wird nach der Klassen Überschrift und den Vererbungs Deklarationen, jedoch vor allen Element Definitionen angezeigt. Die Syntax ähnelt `let` der Bindung außerhalb von Klassen, aber die in einer Klasse definierten Namen haben einen Bereich, der auf die Klasse beschränkt ist. Eine `let` Bindung erstellt ein privates Feld oder eine private Funktion. um Daten oder Funktionen öffentlich verfügbar zu machen, deklarieren Sie eine Eigenschaft oder eine Member-Methode.

Eine `let` Bindung, die nicht statisch ist, wird als `let` instanzbindung bezeichnet. Instanzbindungen `let` werden ausgeführt, wenn Objekte erstellt werden. Statische `let` Bindungen sind Teil des statischen Initialisierers für die-Klasse, die vor der ersten Verwendung des Typs garantiert ausgeführt wird.

Der Code in instanzbindungen `let` kann die Parameter des primären Konstruktors verwenden.

Attribute und Zugriffsmodifizierer `let` sind für Bindungen in Klassen nicht zulässig.

In den folgenden Codebeispielen werden verschiedene Typen `let` von Bindungen in Klassen veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

Die Ausgabe lautet wie folgt.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Alternative Möglichkeiten zum Erstellen von Feldern

Sie können auch das `val` -Schlüsselwort verwenden, um ein privates Feld zu erstellen. Wenn Sie das `val` -Schlüsselwort verwenden, wird dem Feld kein Wert zugewiesen, wenn das Objekt erstellt wird, sondern mit einem Standardwert initialisiert wird. Weitere Informationen finden [Sie unter Explizite Felder: Das Val-](explicit-fields-the-val-keyword.md)Schlüsselwort.

Sie können auch private Felder in einer Klasse definieren, indem Sie eine Element Definition verwenden und der `private` Definition das Schlüsselwort hinzufügen. Dies kann hilfreich sein, wenn Sie die Barrierefreiheit eines Members ändern möchten, ohne den Code neu zu schreiben. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-control.md).

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
- [`do`-Bindungen in Klassen](do-bindings-in-classes.md)
- [`let`Land](../functions/let-bindings.md)
