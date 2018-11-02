---
title: Kopieren und Aktualisieren von Datensatzausdrücken (f#)
description: Informationen Sie zum Schreiben von 'kopieren und aktualisieren Datensatz Ausdruck', die einen vorhandenen Datensatz, Updates kopiert Felder angegeben und gibt den aktualisierten Datensatz zurück.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: d2b089e8a7fc5c7ee26139003e23d2eaa8a3174e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45990842"
---
# <a name="copy-and-update-record-expressions"></a>Kopieren und Aktualisieren von Datensatzausdrücken

Ein *kopieren und Aktualisieren des Datensatzes Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt den aktualisierten Datensatz zurück.

## <a name="syntax"></a>Syntax

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Hinweise

Datensätze sind standardmäßig unveränderlich, sodass es kein Update einen vorhandenen Datensatz möglich ist. Um eine aktualisierte Datensatz alle Felder eines Datensatzes erstellen müsste erneut angegeben werden. Zur Vereinfachung dieser Aufgabe eine *kopieren und Aktualisieren des Datensatzes Ausdruck* kann verwendet werden. Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue des gleichen Typs mit angegebenen Felder aus dem Ausdruck und das fehlende Feld, das dem angegebenen Ausdruck.
Dies kann nützlich sein, beim Kopieren eines vorhandenen Datensatzes, und möglicherweise einige Werte der Felder ändern.

Nehmen Sie z. B. einen neu erstellten Datensatz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und Aktualisieren des Datensatzes Ausdruck* wie folgt:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Siehe auch

- [Datensätze](records.md)
- [F#-Sprachreferenz](index.md)
