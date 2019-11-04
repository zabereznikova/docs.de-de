---
title: Zugriffssteuerung
description: Erfahren Sie, wie Sie den Zugriff auf Programmier Elemente (z. b. Typen, Methoden und Funktionen F# ) in der Programmiersprache steuern können.
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425109"
---
# <a name="access-control"></a>Zugriffssteuerung

*Access Control* bezieht sich auf die Deklaration, welche Clients bestimmte Programmelemente verwenden können, z. b. Typen, Methoden und Funktionen.

## <a name="basics-of-access-control"></a>Grundlagen von Access Control

In F#können die zugriffssteuerungsspezifizierer `public`, `internal`und `private` auf Module, Typen, Methoden, Wert Definitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden.

- `public` gibt an, dass alle Aufrufer auf die Entität zugreifen können.

- `internal` gibt an, dass auf die Entität nur von derselben Assembly aus zugegriffen werden kann.

- `private` gibt an, dass nur vom einschließenden Typ oder Modul auf die Entität zugegriffen werden kann.

> [!NOTE]
> Der Zugriffsspezifizierer `protected` wird F#in nicht verwendet. es ist jedoch akzeptabel, wenn Sie Typen verwenden, die in Sprachen erstellt wurden, die `protected` Zugriff unterstützen. Wenn Sie also eine geschützte Methode überschreiben, bleibt die Methode nur innerhalb der Klasse und der untergeordneten Elemente zugänglich.

Im Allgemeinen wird der Spezifizierer vor dem Namen der Entität eingefügt, es sei denn, ein `mutable` oder `inline` Spezifizierer wird verwendet, die nach dem zugriffssteuerungsspezifizierer angezeigt werden.

Wenn kein Zugriffsspezifizierer verwendet wird, wird der Standardwert `public`, mit Ausnahme von `let` Bindungen in einem Typ, die immer dem Typ `private`.

Signaturen in F# bieten einen weiteren Mechanismus zum Steuern des F# Zugriffs auf Programmelemente. Signaturen sind für die Zugriffs Steuerung nicht erforderlich. Weitere Informationen finden Sie unter [Signaturen](signature-files.md).

## <a name="rules-for-access-control"></a>Regeln für Access Control

Die Zugriffs Steuerung unterliegt den folgenden Regeln:

- Vererbungs Deklarationen (d. h. die Verwendung von `inherit`, um eine Basisklasse für eine Klasse anzugeben), Schnittstellen Deklarationen (d. h. die Angabe, dass eine Klasse eine Schnittstelle implementiert) und abstrakte Member haben immer denselben Zugriff wie der einschließende Typ. Daher kann kein zugriffssteuerungsspezifizierer für diese Konstrukte verwendet werden.

- Barrierefreiheit für einzelne Fälle in einer Unterscheidungs-Union wird durch den Zugriff auf die Unterscheidungs-Union selbst festgelegt. Das heißt, dass ein bestimmter Union-Fall nicht weniger zugreifbar ist als die Union selbst.

- Der Zugriff auf einzelne Felder eines Daten Satz Typs wird durch die Barrierefreiheit des Datensatzes bestimmt. Das heißt, eine bestimmte Daten Satz Bezeichnung ist nicht weniger zugreifbar als der Datensatz selbst.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung von zugriffssteuerungsorbezeichgern. Das Projekt enthält zwei Dateien `Module1.fs` und `Module2.fs`. Jede Datei ist implizit ein Modul. Daher gibt es zwei Module: `Module1` und `Module2`. In `Module1`werden ein privater Typ und ein interner Typ definiert. Der Zugriff auf den privaten Typ ist aus `Module2`nicht möglich, der interne Typ ist jedoch möglich.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

Der folgende Code testet den Zugriff auf die Typen, die in `Module1.fs`erstellt wurden.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Signaturen](signature-files.md)
