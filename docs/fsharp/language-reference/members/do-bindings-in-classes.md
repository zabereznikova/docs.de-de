---
title: do-Bindungen in Klassen (F#)
description: "Informationen Sie zum Verwenden einer \"do Bindung in einer Klassendefinition, Aktionen ausgeführt, wenn das Objekt erstellt wird oder wenn der Typ zuerst verwendet wird\" f#."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a>do-Bindungen in Klassen

Ein `do` Bindung in einer Klassendefinition führt Aktionen aus, wenn das Objekt erstellt wurde, oder für einen statischen `do` binden, wenn der Typ zuerst verwendet wird.


## <a name="syntax"></a>Syntax

```fsharp
[static] do expression
```

## <a name="remarks"></a>Hinweise
Ein `do` Bindung angezeigt wird, zusammen mit oder nach `let` Bindungen, aber vor der Definitionen der Elemente in einer Klassendefinition. Obwohl die `do` Schlüsselwort ist optional für `do` Bindungen auf Modulebene, es ist nicht optional für `do` Bindungen in einer Klassendefinition.

Für die Erstellung eines jeden Objekts, eines beliebigen angegebenen Typ, der nicht statischen `do` Bindungen und nicht statische `let` Bindungen werden in der Reihenfolge, in der sie in der Klassendefinition erscheinen, ausgeführt. Mehrere `do` Bindungen in einem auftreten können. Die statische `let` Bindungen und die statische `do` Bindungen Nachrichtentext der primären Konstruktor. Der Code in der statischen `do` im Abschnitt über Bindungen kann die primären Konstruktorparameter und alle Werte oder in definierten Funktionen verweisen die `let` im Abschnitt über Bindungen.

Nicht statische `do` Bindungen können Member der Klasse zugreifen, solange die Klasse verfügt über einen Selbstbezeichner, die von definiert ist ein `as` Schlüsselwort in der Klasse Überschrift bzw. solange alle Vorkommen dieser Elemente mit der Selbstbezeichner für die Klasse qualifiziert sind.

Da `let` Bindungen initialisieren die privaten Felder einer Klasse, die häufig notwendig ist, um sicherzustellen, dass Mitglieder Verhalten sich wie erwartet, `do` Bindungen werden in der Regel nach platziert `let` Bindungen, so dass der code in der `do` Bindung kann Führen Sie ein vollständig initialisiertes Objekt. Wenn Ihr Code versucht, ein Element zu verwenden, bevor die Initialisierung abgeschlossen ist, wird eine InvalidOperationException ausgelöst.

Statische `do` Bindungen können statische Member verweisen oder Felder des einschließenden Klasse aber nicht auf die Instanz Member oder Felder. Statische `do` Bindungen werden Teil der statische Initialisierer für die Klasse, die unbedingt ausführen, bevor die Klasse zuerst verwendet wird.

Attribute werden ignoriert, für `do` Bindungen in Typen. Wenn ein Attribut für Code erforderlich, die ist in führt ein `do` binden, muss angewendet werden an den primären Konstruktor.

Im folgenden Code wird eine Klasse verfügt über einen statischen `do` Bindung und eine nicht statische `do` Bindung. Das Objekt verfügt über einen Konstruktor, der zwei Parameter verfügt `a` und `b`, und zwei private Felder definiert sind, der `let` Bindungen für die Klasse. Zwei Eigenschaften sind auch definiert. Alle diese werden im Bereich der statischen `do` im Abschnitt über Bindungen, wie durch die Linie dargestellt wird, die alle diese Werte ausgibt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

Die Ausgabe lautet wie folgt.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>Siehe auch
[Mitglieder](index.md)

[Klassen](../classes.md)

[Konstruktoren](constructors.md)

[`let`-Bindungen in Klassen](let-bindings-in-classes.md)

[`do`Bindungen](../functions/do-Bindings.md)
