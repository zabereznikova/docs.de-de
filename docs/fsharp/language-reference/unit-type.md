---
title: Unit-Typ (F#)
description: Erfahren Sie, wie der f#-Typ "Unit" häufig verwendet wird, um die Stelle zu speichern, in dem ein Wert durch die Syntax der erforderlich ist, wenn kein Wert erforderlich oder gewünscht ist.
ms.date: 05/16/2016
ms.openlocfilehash: c3dfa5f63c25a1e8abc0f75b905c129b311479af
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "44204655"
---
# <a name="unit-type"></a>Unit-Typ

Die `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts; gibt an, die `unit` Typ verfügt über nur einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder erforderlich ist.

## <a name="syntax"></a>Syntax

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Hinweise

Alle F#-Ausdruck muss zu einem Wert ausgewertet werden. Für Ausdrücke, die keinen Wert generieren, die von Interesse sind, wird der Wert des Typs `unit` verwendet wird. Die `unit` Typ ähnelt der `void` Typ in Sprachen wie c# und C++.

Die `unit` Typ verfügt über einen einzelnen Wert und diesen Wert angegeben wird, durch das Token `()`.

Der Wert des der `unit` wird häufig in F#-Programmierung, um die Stelle zu speichern, ein Wert von der Sprachsyntax erforderlich ist, aber wenn kein Wert erforderlich oder gewünscht wird verwendet. Ein Beispiel handelt es sich möglicherweise um den Rückgabewert einer `printf` Funktion. Da die wichtigen Aktionen von der `printf` Vorgang auftreten, in der Funktion, die Funktion muss nicht unbedingt einen tatsächlichen Wert zurückgeben. Aus diesem Grund der Rückgabewert ist vom Typ `unit`.

Einige Konstrukte erwarten eine `unit` Wert. Z. B. eine `do` -Bindung oder Code auf der obersten Ebene eines Moduls wird erwartet, ergibt eine `unit` Wert. Der Compiler meldet eine Warnung bei eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls, erzeugt ein Ergebnis außer der `unit` -Wert, der nicht verwendet wird, wie im folgenden Beispiel gezeigt,.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Diese Warnung ist ein Merkmal der funktionalen Programmierung. Es wird nicht in anderen .NET-Programmiersprachen angezeigt. In einem rein funktionaler-Programm in der Funktionen aller möglichen Nebeneffekte, keine ist der letzte zurückgegebene Wert das einzige Ergebnis eines Funktionsaufrufs. Wenn das Ergebnis ignoriert wird, ist es daher möglicherweise ein Programmierfehler. F# ist, zwar keine rein funktionale Programmiersprache ist es sich bewährt, führen die funktionalen Programmierstils, wann immer möglich.

## <a name="see-also"></a>Siehe auch

- [Primitive](primitive-types.md)
- [F#-Sprachreferenz](index.md)
