---
title: do-Bindungen
description: Erfahren Sie, wie ein F# 'do', Bindung werden verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert.
ms.date: 05/16/2016
ms.openlocfilehash: d29f8557fda06097d2e85748ab6286f0415730b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683378"
---
# <a name="do-bindings"></a>do-Bindungen

Ein `do` Bindung wird verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert. Darüber hinaus werden Bindungen möglich in Klassen finden Sie in [ `do` Bindungen in Klassen](../members/do-bindings-in-classes.md).

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Hinweise

Verwenden einer `do` binden, wenn Sie möchten, dass zum Ausführen von Code unabhängig von der Definition einer Funktion oder Wert. Der Ausdruck in einem `do` Bindung muss zurückgeben `unit`. Code in einem der obersten Ebene `do` Bindung ausgeführt wird, wenn das Modul initialisiert wird. Das Schlüsselwort `do` ist optional.

Attribute können auf oberster Ebene angewendet werden `do` Bindung. Z. B. Wenn Ihr Programm COM-Interop verwendet, Sie möchten gelten die `STAThread` -Attribut auf Ihr Programm. Sie erreichen dies, indem Sie ein Attribut auf eine `do` binden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](../index.md)
- [Funktionen](index.md)