---
title: do-Bindungen (F#)
description: Erfahren Sie, wie eine F#-"Bindung" do"verwendet wird, Code auszuführen, ohne die Definition einer Funktion oder einen Wert.
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45973143"
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
