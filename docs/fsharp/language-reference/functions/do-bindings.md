---
title: do-Bindungen
description: Erfahren Sie, F# wie eine "Do"-Bindung verwendet wird, um Code auszuführen, ohne eine Funktion oder einen Wert zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630541"
---
# <a name="do-bindings"></a>do-Bindungen

Eine `do` Bindung wird verwendet, um Code auszuführen, ohne eine Funktion oder einen Wert zu definieren. Außerdem können do-Bindungen in Klassen verwendet werden. weitere [ `do` ](../members/do-bindings-in-classes.md)Informationen finden Sie unter Bindungen in Klassen.

## <a name="syntax"></a>Syntax

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Hinweise

Verwenden Sie `do` eine Bindung, wenn Sie Code unabhängig von einer Funktions-oder Werte Definition ausführen möchten. Der Ausdruck in einer `do` Bindung muss zurück `unit`geben. Der Code in einer Bindung auf `do` oberster Ebene wird ausgeführt, wenn das Modul initialisiert wird. Das Schlüssel `do` Wort ist optional.

Attribute können auf eine Bindung auf oberster Ebene `do` angewendet werden. Wenn das Programm z. b. com-Interop verwendet, sollten Sie das `STAThread` -Attribut auf Ihr Programm anwenden. Hierfür können Sie ein Attribut in einer `do` Bindung verwenden, wie im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](../index.md)
- [Funktionen](index.md)
