---
title: Unit-Typ
description: Erfahren Sie, F# wie der Typ "Unit" häufig verwendet wird, um den Speicherort zu speichern, an dem ein Wert für die Sprachsyntax erforderlich ist, wenn kein Wert erforderlich oder erwünscht ist.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424034"
---
# <a name="unit-type"></a>Unit-Typ

Der `unit` Typ ist ein Typ, der das Fehlen eines bestimmten Werts angibt. der `unit` Typ hat nur einen einzelnen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder benötigt wird.

## <a name="syntax"></a>Syntax

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Hinweise

Jeder F# Ausdruck muss zu einem-Wert ausgewertet werden. Für Ausdrücke, die keinen Wert generieren, der von Interesse ist, wird der Wert des Typs `unit` verwendet. Der `unit` C# -Typ ähnelt dem `void`-Typ in Sprachen wie C++und.

Der `unit` Typ hat einen einzelnen Wert, und dieser Wert wird durch das Token `()`angegeben.

Der Wert des `unit` Typs wird häufig bei F# der Programmierung verwendet, um den Ort zu speichern, an dem ein Wert für die Sprachsyntax erforderlich ist, aber wenn kein Wert erforderlich oder erwünscht ist. Ein Beispiel könnte der Rückgabewert einer `printf`-Funktion sein. Da die wichtigen Aktionen des `printf` Vorgangs in der Funktion auftreten, muss die Funktion keinen tatsächlichen Wert zurückgeben. Daher ist der Rückgabewert vom Typ `unit`.

Einige Konstrukte erwarten einen `unit` Wert. Beispielsweise wird erwartet, dass eine `do` Bindung oder Code auf der obersten Ebene eines Moduls zu einem `unit` Wert ausgewertet wird. Der Compiler meldet eine Warnung, wenn eine `do` Bindung oder Code auf der obersten Ebene eines Moduls ein anderes Ergebnis als den `unit` Wert erzeugt, der nicht verwendet wird, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Diese Warnung ist ein Merkmal der funktionalen Programmierung. Sie wird in anderen .NET-Programmiersprachen nicht angezeigt. In einem rein funktionalen Programm, in dem Funktionen keine Nebeneffekte haben, ist der abschließende Rückgabewert das einzige Ergebnis eines Funktions Aufrufes. Wenn das Ergebnis ignoriert wird, ist es daher ein möglicher Programmierfehler. Obwohl F# es sich nicht um eine rein funktionale Programmiersprache handelt, empfiehlt es sich, nach Möglichkeit den funktionalen Programmierstil zu befolgen.

## <a name="see-also"></a>Siehe auch

- [Christentum](basic-types.md)
- [F#-Sprachreferenz](index.md)
