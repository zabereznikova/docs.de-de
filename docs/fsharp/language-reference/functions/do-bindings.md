---
title: do-Bindungen (F#)
description: "Darüber informieren Sie, wie ein F#-\"Bindung\" do\"wird zum Ausführen von Code ohne die Definition einer Funktion oder Wert."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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

