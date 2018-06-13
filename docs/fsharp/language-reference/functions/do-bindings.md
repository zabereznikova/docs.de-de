---
title: do-Bindungen (F#)
description: Darüber informieren Sie, wie ein F#-"Bindung" do"wird zum Ausführen von Code ohne die Definition einer Funktion oder Wert.
ms.date: 05/16/2016
ms.openlocfilehash: 6fd084090a204beab0da1c2deb5b5ae2a86281c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562335"
---
# <a name="do-bindings"></a>do-Bindungen

Ein `do` Bindung verwendet, um Code auszuführen, ohne die Definition einer Funktion oder Wert. Darüber hinaus werden Bindungen können werden in Klassen verwendet werden, finden Sie unter [ `do` Bindungen in Klassen](../members/do-bindings-in-classes.md).


## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Hinweise
Verwenden einer `do` binden, wenn der Code unabhängig von der Definition einer Funktion oder Wert ausgeführt werden soll. Der Ausdruck in einem `do` Bindung muss zurückgeben `unit`. Code in einem der obersten Ebene `do` Bindung wird ausgeführt, wenn das Modul initialisiert wird. Das Schlüsselwort `do` ist optional.

Attribute können auf einem der obersten Ebene angewendet werden `do` Bindung. Z. B. Wenn Ihr Programm COM-Interop verwendet, Sie möchten gelten die `STAThread` -Attribut auf das Programm. Sie erreichen dies, indem Sie ein Attribut auf eine `do` binden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](../index.md)

[Funktionen](index.md)

