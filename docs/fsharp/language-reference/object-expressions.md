---
title: Objektausdrücke (F#)
description: Erfahren Sie, wie Objektausdrücke [F#] verwenden, wenn Sie den zusätzlichen Code und Mehraufwands für das Erstellen eines neuen vermeiden möchten benannten Typs dar.
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564390"
---
# <a name="object-expressions"></a>Objektausdrücke

Ein *-Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz eines Objekttyps dynamisch erstellte, anonymes, das erstellt wird basierend auf eine vorhandene Basistyp, eine Schnittstelle oder eine Gruppe von Schnittstellen.


## <a name="syntax"></a>Syntax

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax der *Typename* einer vorhandenen Klassen- oder Schnittstellentyp darstellt. *Typ-Params* beschreibt die optionalen generischen Typparameter. Die *Argumente* werden nur für Klassentypen, die Konstruktorparameter erfordern verwendet. Die *Memberdefinitionen* sind überschreibungen von Methoden der Basisklasse oder Implementierungen abstrakte Methoden aus einer Basisklasse oder Schnittstelle.

Das folgende Beispiel zeigt verschiedene Typen von Objektausdrücke.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Objektausdrücke verwenden
Objektausdrücke werden verwendet, wenn Sie möchten, um zu vermeiden, die zusätzlichen Code und den Aufwand, die zum Erstellen eines neuen benannten Typ erforderlich ist. Wenn Sie Objektausdrücke verwenden, minimiert die Anzahl von Typen, die in einem Programm erstellt, können Sie reduzieren die Anzahl der Codezeilen und zu verhindern, dass der unnötige Vervielfältigung von Typen. Statt viele Typen nur, um bestimmte Situationen zu bewältigen, können Sie ein Objektausdrücke, die einen vorhandenen Typ passt, oder stellt eine geeignete Implementierung einer Schnittstelle für den speziellen Fall zur hand.


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
