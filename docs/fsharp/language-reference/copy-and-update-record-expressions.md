---
title: Kopieren und Update der Datensatz Ausdrücke (f#)
description: Informationen Sie zum Schreiben 'kopieren und Update Datensatz Ausdruck', der einen vorhandenen Datensatz, Updates kopiert Felder angegeben und den aktualisierten Datensatz zurückgegeben.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 000746b6e76349ae6d8f338519a58034f4e29020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="copy-and-update-record-expressions"></a>Kopieren und Aktualisieren von Datensatzausdrücken

Ein *kopieren und update der Datensatz Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt die aktualisierte Datensatz zurück.


## <a name="syntax"></a>Syntax

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Hinweise
Datensätze sind unveränderlich ist, wird standardmäßig, sodass es kein Update einen vorhandenen Datensatz möglich ist. Um eine aktualisierte Datensatz aller Felder eines Datensatzes erstellen müssten erneut angegeben werden. Um diese Aufgabe zu vereinfachen ein *kopieren und update der Datensatz Ausdruck* kann verwendet werden. Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue desselben Typs mithilfe des angegebenen Felder aus dem Ausdruck und das fehlende Feld mit dem angegebenen Ausdruck.
Dies kann nützlich sein, wenn Sie zum Kopieren eines vorhandenen Datensatzes und möglicherweise einige der Werte der Felder ändern.

Nehmen Sie z. B. einen neu erstellten Datensatz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und update der Datensatz Ausdruck* wie folgt:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Siehe auch
[Datensätze](records.md)

[F#-Sprachreferenz](index.md)
