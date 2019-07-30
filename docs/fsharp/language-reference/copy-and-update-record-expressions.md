---
title: Kopieren und Aktualisieren von Datensatzausdrücken
description: Erfahren Sie, wie Sie einen "Kopieren und aktualisieren"-Ausdruck schreiben, der einen vorhandenen Datensatz oder einen anonymen Datensatz kopiert, bestimmte Felder aktualisiert und den aktualisierten Datensatz oder anonymen Datensatz zurückgibt.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630375"
---
# <a name="copy-and-update-record-expressions"></a>Kopieren und Aktualisieren von Datensatzausdrücken

Ein *Kopier-und Update Daten Satz Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert, bestimmte Felder aktualisiert und den aktualisierten Datensatz zurückgibt.

## <a name="syntax"></a>Syntax

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Hinweise

Datensätze und anonyme Datensätze sind standardmäßig unveränderlich, sodass kein Update eines vorhandenen Datensatzes möglich ist. Zum Erstellen eines aktualisierten Datensatzes müssten alle Felder eines Datensatzes erneut angegeben werden. Um diese Aufgabe zu vereinfachen, kann ein *Kopier-und Update Ausdruck* verwendet werden. Dieser Ausdruck nimmt einen vorhandenen Datensatz an, erstellt einen neuen desselben Typs, indem er die angegebenen Felder aus dem Ausdruck und das fehlende Feld verwendet, das durch den Ausdruck angegeben wird.

Dies kann hilfreich sein, wenn Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Feldwerte ändern müssen.

Nehmen Sie zum Beispiel einen neu erstellten Datensatz.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Wenn Sie nur ein Feld dieses Datensatzes aktualisieren möchten, können Sie den *Ausdruck zum Kopieren und Aktualisieren von Datensätzen* wie folgt verwenden:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Siehe auch

- [Datensätze](records.md)
- [Anonyme Datensätze](anonymous-records.md)
- [F#-Sprachreferenz](index.md)
