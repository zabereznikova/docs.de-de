---
title: do-Bindungen in Klassen
description: Erfahren Sie, wie Sie F# eine "Do"-Bindung in einer Klassendefinition verwenden, die Aktionen ausführt, wenn das Objekt erstellt wird oder wenn der Typ zum ersten Mal verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627586"
---
# <a name="do-bindings-in-classes"></a>do-Bindungen in Klassen

Eine `do` Bindung in einer Klassendefinition führt Aktionen aus, wenn das Objekt erstellt wird, oder für `do` eine statische Bindung, wenn der Typ zum ersten Mal verwendet wird.

## <a name="syntax"></a>Syntax

```fsharp
[static] do expression
```

## <a name="remarks"></a>Hinweise

Eine `do` Bindung wird mit oder nach `let` Bindungen, aber vor Member-Definitionen in einer Klassendefinition angezeigt. Obwohl das `do` -Schlüsselwort für `do` Bindungen auf Modulebene optional ist, ist es für `do` Bindungen in einer Klassendefinition nicht optional.

Bei der Erstellung jedes Objekts eines beliebigen Typs werden nicht statische `do` Bindungen und nicht statische `let` Bindungen in der Reihenfolge ausgeführt, in der Sie in der Klassendefinition angezeigt werden. Mehrere `do` Bindungen können in einem Typ auftreten. Die nicht statischen `let` Bindungen und die nicht statischen `do` Bindungen werden zum Hauptteil des primären Konstruktors. Der Code im Abschnitt nicht statische `do` Bindungen kann auf die primären Konstruktorparameter und alle Werte oder Funktionen verweisen, die `let` im Bindungs Abschnitt definiert sind.

Nicht statische `do` Bindungen können auf Member der Klasse zugreifen, sofern die Klasse über einen selbst Bezeichner verfügt, der durch ein `as` -Schlüsselwort in der Überschrift der-Klasse definiert wird, und solange alle Verwendungen dieser Member mit dem selbst Bezeichner für die Klasse qualifiziert sind.

Da `let` Bindungen die privaten Felder einer Klasse initialisieren, was häufig notwendig ist, um sicherzustellen, dass sich die Member `do` wie erwartet Verhalten, werden `let` Bindungen in der Regel nach Bindungen `do` eingefügt, sodass der Code in der Bindung Führen Sie mit einem vollständig initialisierten Objekt aus. Wenn Ihr Code versucht, einen Member zu verwenden, bevor die Initialisierung beendet ist, wird eine InvalidOperationException ausgelöst.

Statische `do` Bindungen können auf statische Member oder Felder der einschließenden Klasse verweisen, jedoch nicht auf Instanzmember oder-Felder. Statische `do` Bindungen werden Teil des statischen Initialisierers für die Klasse, die vor der ersten Verwendung der Klasse garantiert ausgeführt wird.

Attribute werden bei `do` Bindungen in Typen ignoriert. Wenn ein Attribut für Code erforderlich ist, der in einer `do` Bindung ausgeführt wird, muss er auf den primären Konstruktor angewendet werden.

Im folgenden Code verfügt eine Klasse über eine statische `do` Bindung und eine nicht statische `do` Bindung. Das-Objekt verfügt über einen Konstruktor mit zwei para `a` Metern `b`: und, und zwei private Felder werden in `let` den Bindungen für die-Klasse definiert. Außerdem werden zwei Eigenschaften definiert. Alle diese Werte befinden sich im Bereich "nicht statische `do` Bindungen", wie in der Zeile veranschaulicht, in der alle diese Werte gedruckt werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

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
- [`do`Land/Region](../functions/do-Bindings.md)
