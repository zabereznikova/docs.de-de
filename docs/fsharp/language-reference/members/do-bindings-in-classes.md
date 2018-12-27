---
title: do-Bindungen in Klassen
description: Erfahren Sie, wie Sie mit einem F# 'do'-Bindung in einer Klassendefinition, Aktionen ausgeführt werden, wenn das Objekt erstellt wird, oder wenn der Typ zuerst verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddf2b5ca458d0950c2e07bf2c37c205877e2173
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613114"
---
# <a name="do-bindings-in-classes"></a>do-Bindungen in Klassen

Ein `do` Bindung in einer Klassendefinition führt Aktionen aus, wenn das Objekt erstellt wird, oder, für eine statische `do` binden, wenn der Typ zuerst verwendet wird.

## <a name="syntax"></a>Syntax

```fsharp
[static] do expression
```

## <a name="remarks"></a>Hinweise

Ein `do` Bindung angezeigt wird, zusammen mit oder nach `let` Bindungen, aber vor den Definitionen der Elemente in einer Klassendefinition. Obwohl die `do` -Schlüsselwort ist optional für `do` Bindungen auf Modulebene, es ist nicht optional für `do` Bindungen in einer Klassendefinition.

Für die Erstellung der jedes Objekt eines beliebigen angegebenen Typs, die nicht statische `do` Bindungen und nicht statische `let` Bindungen werden in der Reihenfolge in der Definition der Klasse ausgeführt. Mehrere `do` Bindungen in einem Typ auftreten können. Die nicht statische `let` Bindungen und die nicht statische `do` Bindungen werden der Text des primären Konstruktors. Der Code in der nicht statischen `do` Parameter des primären Konstruktors und alle Werte oder Funktionen, die definiert sind, kann im Abschnitt über Bindungen verweisen die `let` im Abschnitt über Bindungen.

Nicht statische `do` Bindungen können auf Member der Klasse zugreifen, solange die Klasse verfügt über ein Self-Bezeichner, die von definiert ist ein `as` Schlüsselwort in der Klasse, die Spaltenüberschrift, und so lange, wie Sie alle Vorkommen dieser Elemente mit der Selbstbezeichner für die Klasse qualifiziert sind.

Da `let` Bindungen initialisieren die privaten Felder einer Klasse, die häufig notwendig ist, um sicherzustellen, dass Mitglieder Verhalten sich wie erwartet, `do` Bindungen werden in der Regel fügen Sie nach dem `let` Bindungen, so dass der code in die `do` Bindung kann Führen Sie mit der ein vollständig initialisiertes Objekt. Wenn Ihr Code versucht, einen Member zu verwenden, bevor die Initialisierung abgeschlossen ist, wird eine "InvalidOperationException" ausgelöst.

Statische `do` Bindungen können auf statische Member verweisen oder Felder der einschließenden Klasse aber für die Instanz nicht, Member oder Felder. Statische `do` Bindungen Teil der statische Initialisierer für die Klasse, die Ausführung vor der ersten Verwendung die Klasse gewährleistet ist.

Attribute werden ignoriert, für die `do` Bindungen in Typen. Wenn ein Attribut für Code erforderlich ist, der ausgeführt wird ein `do` binden, muss angewendet werden auf den primären Konstruktor.

Im folgenden Code wird eine Klasse weist eine statische `do` Bindung und eine nicht statische `do` Bindung. Das Objekt hat einen Konstruktor, der zwei Parameter verfügt `a` und `b`, zwei private Felder werden in definiert die `let` Bindungen für die Klasse. Außerdem werden die zwei Eigenschaften definiert. Alle diese befinden sich im Gültigkeitsbereich, in der nicht statischen `do` Bindungsabschnitt, wie durch die Linie dargestellt wird, die alle diese Werte ausgibt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

Die Ausgabe lautet wie folgt.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
- [Klassen](../classes.md)
- [Konstruktoren](constructors.md)
- [`let`-Bindungen in Klassen](let-bindings-in-classes.md)
- [`do` Bindungen](../functions/do-Bindings.md)