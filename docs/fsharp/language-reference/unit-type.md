---
title: Unit-Typ (F#)
description: Erfahren Sie, wie der f#-Typ "Einheit" häufig verwendet wird, um den Ort zu speichern, in dem ein Wert von der Sprachsyntax erforderlich ist, wenn kein Wert erforderlich oder gewünscht ist.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1a8c8f74e31c5426a9fb6a7143e9d2ac9a7104c0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="unit-type"></a>Unit-Typ

Die `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts; gibt an, die `unit` Typ verfügt über einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden ist oder benötigt wird.


## <a name="syntax"></a>Syntax

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Hinweise
Jeder f#-Ausdruck muss zu einem Wert ausgewertet werden. Für Ausdrücke, die keinen Wert generieren, die von Interesse sind, den Wert des Typs `unit` verwendet wird. Die `unit` Typ ähnelt dem `void` Typ in Sprachen wie c# und C++.

Die `unit` Typ verfügt über einen einzelnen Wert und diesen Wert angegeben wird, von dem Token `()`.

Der Wert, der die `unit` Typ werden häufig in F#-Programmierung die Stelle halten, während ein Wert von der Sprachsyntax erforderlich ist, jedoch kein Wert erforderlich oder gewünscht ist. Ein Beispiel handelt es sich möglicherweise um den Rückgabewert einer `printf` Funktion. Da die wichtigen Aktionen von der `printf` Vorgang auftreten, in der Funktion die Funktion muss es sich nicht in einen tatsächlichen Wert zurückgeben. Aus diesem Grund ist der Rückgabewert vom Typ `unit`.

Einige Konstrukte erwarten einen `unit` Wert. Z. B. eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls muss ergeben eine `unit` Wert. Meldet der Compiler eine Warnung, wenn eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls erzeugt ein Ergebnis außer der `unit` -Wert, der nicht verwendet wird, wie im folgenden Beispiel gezeigt,.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Diese Warnung ist ein Merkmal der funktionalen Programmierung. Es wird nicht in anderen .NET-Programmiersprachen angezeigt. In einem reinen funktionalen-Programm in die Funktionen keine keine Nebeneffekte aufweisen, ist der letzte Rückgabewert das einzige Ergebnis eines Funktionsaufrufs. Wenn das Ergebnis ignoriert wird, ist es daher möglicherweise ein Programmierfehler. F# ist, zwar keiner reinen funktionalen Programmiersprache Ihrer Wahl ist es empfiehlt sich, führen die funktionalen Programmierstils, wann immer möglich.

## <a name="see-also"></a>Siehe auch
[Primitive](primitive-types.md)

[F#-Sprachreferenz](index.md)
