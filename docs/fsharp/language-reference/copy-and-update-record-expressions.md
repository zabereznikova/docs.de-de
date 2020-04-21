---
title: Kopieren und Aktualisieren von Datensatzausdrücken
description: Erfahren Sie, wie Sie einen "Kopier- und Aktualisierungsausdruck" schreiben, der einen vorhandenen Datensatz oder anonymen Datensatz kopiert, bestimmte Felder aktualisiert und den aktualisierten oder anonymen Datensatz zurückgibt.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739287"
---
# <a name="copy-and-update-record-expressions"></a>Kopieren und Aktualisieren von Datensatzausdrücken

Ein *Kopier- und Aktualisierungsdatensatzausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert, angegebene Felder aktualisiert und den aktualisierten Datensatz zurückgibt.

## <a name="syntax"></a>Syntax

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Bemerkungen

Datensätze und anonyme Datensätze sind standardmäßig unveränderlich, sodass es nicht möglich ist, einen vorhandenen Datensatz zu aktualisieren. Um einen aktualisierten Datensatz zu erstellen, müssten alle Felder eines Datensatzes erneut angegeben werden. Um diese Aufgabe zu vereinfachen, kann ein *Kopier- und Aktualisierungsausdruck* verwendet werden. Dieser Ausdruck nimmt einen vorhandenen Datensatz an, erstellt einen neuen Datensatz desselben Typs mithilfe bestimmter Felder aus dem Ausdruck und des fehlenden Felds, das durch den Ausdruck angegeben wird.

Dies kann nützlich sein, wenn Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Feldwerte ändern müssen.

Nehmen Sie zum Beispiel einen neu erstellten Datensatz.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Um nur zwei Felder in diesem Datensatz zu aktualisieren, können Sie den *Ausdruck "Kopier- und Aktualisierungsdatensatz"* verwenden:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Siehe auch

- [Datensätze](records.md)
- [Anonyme Datensätze](anonymous-records.md)
- [Sprachreferenz](index.md)
