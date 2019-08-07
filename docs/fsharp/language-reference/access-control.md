---
title: Zugriffssteuerung
description: Informationen Sie zum Steuern des Zugriffs auf Programmierelemente wie Typen, Methoden und Funktionen, die in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: 38f8f3fd4114c0428fbe8baca71594cd07740b2c
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817852"
---
# <a name="access-control"></a>Zugriffssteuerung

*Access Control* bezieht sich auf die Deklaration, welche Clients bestimmte Programmelemente verwenden können, z. b. Typen, Methoden und Funktionen.

## <a name="basics-of-access-control"></a>Grundlagen von Access Control

In F#, Steuern der Zugriff Spezifizierer `public`, `internal`, und `private` kann auf Module, Typen, Methoden, wertedefinitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden.

- `public`Gibt an, dass alle Aufrufer auf die Entität zugreifen können.

- `internal`Gibt an, dass auf die Entität nur aus derselben Assembly zugegriffen werden kann.

- `private`Gibt an, dass nur vom einschließenden Typ oder Modul auf die Entität zugegriffen werden kann.

> [!NOTE]
> Der Zugriffsspezifizierer `protected` wird nicht in F# verwendet, obwohl es akzeptabel ist, bei Verwendung von Typen, die in Sprachen, unterstützen erstellte `protected` Zugriff. Wenn Sie also eine geschützte Methode überschreiben, bleibt die Methode nur innerhalb der Klasse und der untergeordneten Elemente zugänglich.

Im Allgemeinen wird der Spezifizierer vor dem Namen der Entität eingefügt, es sei denn, es `mutable` wird `inline` ein-oder-Spezifizierer verwendet, der nach dem zugriffssteuerungsspezifizierer angezeigt wird.

Wenn kein Zugriffsspezifizierer verwendet wird, `public`ist der Standard `let` Wert, mit Ausnahme von Bindungen in einem `private` Typ, bei denen es sich immer um den-Typ handelt.

Signaturen in F#-Geben Sie einen anderen Mechanismus zur Steuerung des Zugriffs auf Programmelemente in F#. Signaturen sind für die Zugriffs Steuerung nicht erforderlich. Weitere Informationen finden Sie unter [Signaturen](signatures.md).

## <a name="rules-for-access-control"></a>Regeln für Access Control

Die Zugriffs Steuerung unterliegt den folgenden Regeln:

- Vererbungs Deklarationen (d. h. `inherit` die Verwendung von, um eine Basisklasse für eine Klasse anzugeben), Schnittstellen Deklarationen (d. h. die Angabe, dass eine Klasse eine Schnittstelle implementiert) und abstrakte Member haben immer die gleiche Barrierefreiheit wie der einschließende Typ. Daher kann kein zugriffssteuerungsspezifizierer für diese Konstrukte verwendet werden.

- Barrierefreiheit für einzelne Fälle in einer Unterscheidungs-Union wird durch den Zugriff auf die Unterscheidungs-Union selbst festgelegt. Das heißt, dass ein bestimmter Union-Fall nicht weniger zugreifbar ist als die Union selbst.

- Der Zugriff auf einzelne Felder eines Daten Satz Typs wird durch die Barrierefreiheit des Datensatzes bestimmt. Das heißt, eine bestimmte Daten Satz Bezeichnung ist nicht weniger zugreifbar als der Datensatz selbst.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung von zugriffssteuerungsorbezeichgern. Das Projekt enthält zwei Dateien, `Module1.fs` und. `Module2.fs` Jede Datei ist implizit ein Modul. Daher gibt es zwei Module: `Module1` und. `Module2` In `Module1`werden ein privater Typ und ein interner Typ definiert. Der Zugriff `Module2`auf den privaten Typ ist nicht möglich, aber der interne Typ ist möglich.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

Mit dem folgenden Code wird der Zugriff auf die Typen getestet `Module1.fs`, die in erstellt wurden.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Signaturen](signatures.md)
