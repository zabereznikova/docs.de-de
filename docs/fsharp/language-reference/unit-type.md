---
title: Unit-Typ
description: Erfahren Sie, wie der F#-Typ "Unit" häufig verwendet wird, um die Stelle zu speichern, in dem ein Wert durch die Syntax der erforderlich ist, wenn kein Wert erforderlich oder gewünscht ist.
ms.date: 05/16/2016
ms.openlocfilehash: f1866ff12f36f4f8d3eaa1275551c42fc4ade216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982526"
---
# <a name="unit-type"></a>Unit-Typ

Die `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts; gibt an, die `unit` Typ verfügt über nur einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder erforderlich ist.

## <a name="syntax"></a>Syntax

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Hinweise

Jede F# Ausdruck muss zu einem Wert ausgewertet. Für Ausdrücke, die keinen Wert generieren, die von Interesse sind, wird der Wert des Typs `unit` verwendet wird. Die `unit` Typ ähnelt der `void` Typ in Sprachen wie C# und C++.

Die `unit` Typ verfügt über einen einzelnen Wert und diesen Wert angegeben wird, durch das Token `()`.

Der Wert des der `unit` wird häufig verwendet F# Programmierung, um die Stelle zu speichern, ein Wert von der Sprachsyntax erforderlich ist, aber wenn kein Wert erforderlich oder gewünscht ist. Ein Beispiel handelt es sich möglicherweise um den Rückgabewert einer `printf` Funktion. Da die wichtigen Aktionen von der `printf` Vorgang auftreten, in der Funktion, die Funktion muss nicht unbedingt einen tatsächlichen Wert zurückgeben. Aus diesem Grund der Rückgabewert ist vom Typ `unit`.

Einige Konstrukte erwarten eine `unit` Wert. Z. B. eine `do` -Bindung oder Code auf der obersten Ebene eines Moduls wird erwartet, ergibt eine `unit` Wert. Der Compiler meldet eine Warnung bei eine `do` Bindung oder den Code auf der obersten Ebene eines Moduls, erzeugt ein Ergebnis außer der `unit` -Wert, der nicht verwendet wird, wie im folgenden Beispiel gezeigt,.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Diese Warnung ist ein Merkmal der funktionalen Programmierung. Es wird nicht in anderen .NET-Programmiersprachen angezeigt. In einem rein funktionaler-Programm in der Funktionen aller möglichen Nebeneffekte, keine ist der letzte zurückgegebene Wert das einzige Ergebnis eines Funktionsaufrufs. Wenn das Ergebnis ignoriert wird, ist es daher möglicherweise ein Programmierfehler. Obwohl F# ist nicht rein funktionale Programmiersprache, es empfiehlt sich, führen die funktionalen Programmierstils, wann immer möglich ist.

## <a name="see-also"></a>Siehe auch

- [Primitive](primitive-types.md)
- [F#-Sprachreferenz](index.md)