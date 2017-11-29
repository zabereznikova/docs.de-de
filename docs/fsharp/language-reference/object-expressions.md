---
title: "Objektausdrücke (F#)"
description: "Erfahren Sie, wie Objektausdrücke [F#] verwenden, wenn Sie den zusätzlichen Code und Mehraufwands für das Erstellen eines neuen vermeiden möchten benannten Typs dar."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c6dcf4c9-e7fd-4eee-9e4e-1176f4c27f57
ms.openlocfilehash: 28660d430473de02a8a55e37a26609827b364012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
