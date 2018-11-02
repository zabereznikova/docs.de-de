---
title: Objektausdrücke (F#)
description: Erfahren Sie, wie F#-Object-Ausdrücke verwenden, wenn Sie den zusätzlichen Code und zum Erstellen einer neuen erforderlichen Aufwand vermeiden möchten, mit dem Namen geben.
ms.date: 05/16/2016
ms.openlocfilehash: 1a971044d680d3bf5a6fff38affdaf001d5403b4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865461"
---
# <a name="object-expressions"></a>Objektausdrücke

Ein *Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz von einem dynamisch erstellten anonymen Objekttyps erstellt basiert auf einem vorhandenen Basistyp, Schnittstelle oder Satz von Schnittstellen.

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

In der vorherigen Syntax wird die *Typename* darstellt, einen vorhandenen Klassen- oder Schnittstellentyp. *Typ-Params* wird beschrieben, die optional generischen Typparameter. Die *Argumente* werden verwendet, nur für Klassentypen, die Konstruktorparameter erforderlich ist. Die *Memberdefinitionen* sind überschreibungen von Basisklassenmethoden oder Implementierungen von abstrakten Methoden von einer Basisklasse oder Schnittstelle.

Das folgende Beispiel veranschaulicht verschiedene Arten von Object-Ausdrücke.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Verwenden von Object-Ausdrücke

Sie verwenden die Object-Ausdrücke, wenn Sie möchten, um zu vermeiden, die zusätzlichen Code und den Aufwand, die zum Erstellen einer neuen benannten Typ erforderlich ist. Wenn Sie Object-Ausdrücke verwenden, um die Anzahl der in einem Programm erstellten Typen zu minimieren, können Sie reduzieren Sie die Anzahl von Codezeilen und zu verhindern, dass die unnötige die Verbreitung von Typen. Anstatt zu erstellen, viele Typen nur, um bestimmte Situationen zu behandeln, können Sie einen Object-Ausdruck, der einen vorhandenen Typ anpasst, oder eine geeignete Implementierung der Schnittstelle für den speziellen Fall zur Verfügung stellt.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
