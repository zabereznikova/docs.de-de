---
title: Kopieren und Aktualisieren von Datensatzausdrücken
description: Informationen Sie zum Schreiben von 'kopieren und aktualisieren Ausdruck', die kopiert einen vorhandenen Datensatz "oder" anonyme Datensatz "," Updates Felder angegeben und gibt den aktualisierten Datensatz oder anonyme Datensatz zurück.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041729"
---
# <a name="copy-and-update-record-expressions"></a>Kopieren und Aktualisieren von Datensatzausdrücken

Ein *kopieren und Aktualisieren des Datensatzes Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt den aktualisierten Datensatz zurück.

## <a name="syntax"></a>Syntax

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Hinweise

Datensätze und anonyme Datensätze sind standardmäßig unveränderlich, sodass es kein Update einen vorhandenen Datensatz möglich ist. Um eine aktualisierte Datensatz alle Felder eines Datensatzes erstellen müsste erneut angegeben werden. Zur Vereinfachung dieser Aufgabe eine *kopieren und Aktualisieren von Ausdruck* kann verwendet werden. Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue des gleichen Typs mit angegebenen Felder aus dem Ausdruck und das fehlende Feld, das dem angegebenen Ausdruck.

Dies kann nützlich sein, beim Kopieren eines vorhandenen Datensatzes, und möglicherweise einige Werte der Felder ändern.

Nehmen Sie z. B. einen neu erstellten Datensatz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und Aktualisieren des Datensatzes Ausdruck* wie folgt:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Siehe auch

- [Datensätze](records.md)
- [Anonyme Datensätze](anonymous-records.md)
- [F#-Sprachreferenz](index.md)
