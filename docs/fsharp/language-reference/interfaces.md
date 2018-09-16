---
title: Schnittstellen (F#)
description: Erfahren Sie, wie F#-Schnittstellen für Gruppen von verwandten Elementen angeben, die anderen Klassen implementiert.
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45683189"
---
# <a name="interfaces"></a>Schnittstellen

*Schnittstellen* angeben von Gruppen von verwandten Elementen, die anderen Klassen implementiert.

## <a name="syntax"></a>Syntax

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>Hinweise

Deklarationen von Schnittstellen entsprechen Klassendeklarationen keine Member implementiert werden. Stattdessen werden alle Member abstrakt, wie durch das Schlüsselwort `abstract`. Sie bieten keine Methodentext für abstrakte Methoden. Sie können jedoch eine standardmäßige Implementierung bereitstellen, dazu auch eine separate Definition des Members als Methode zusammen mit den `default` Schlüsselwort. Auf diese Weise ist gleichbedeutend mit eine virtuelle Methode in einer Basisklasse in anderen .NET-Sprachen erstellen. In Klassen, die die Schnittstelle implementieren, kann solche eine virtuelle Methode überschrieben werden.

Der Standardzugriff für Schnittstellen ist `public`.

Optional können jeden Methodenparameter Geben Sie einen Namen mit normalen F#-Syntax:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

In der obigen `ISprintable` beispielsweise die `Print` Methode verfügt über einen einzelnen Parameter des Typs `string` mit dem Namen `format`.

Es gibt zwei Möglichkeiten, um Schnittstellen zu implementieren: mithilfe von Object-Ausdrücke und mithilfe von Klassentypen. In beiden Fällen bietet der Klasse Typ oder ein Objekt Ausdruck Methodentext für abstrakte Methoden der Schnittstelle an. Implementierungen sind spezifisch für jeden Typ, der die Schnittstelle implementiert. Aus diesem Grund können Schnittstellenmethoden auf verschiedene Arten voneinander abweichen.

Die Schlüsselwörter `interface` und `end`, die Anfang und Ende der Definition kennzeichnen, sind optional, wenn Sie einfache Syntax verwenden. Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler, um rückzufolgern, ob der Typ ist eine Klasse oder Schnittstelle, durch die Analyse der erstellt, die Sie verwenden. Wenn Sie ein Element definieren oder andere Klassensyntax verwenden, wird der Typ als eine Klasse interpretiert.

Das .NET codierstil begonnen werden soll alle Schnittstellen im wahrsten Sinne `I`.

## <a name="implementing-interfaces-by-using-class-types"></a>Implementieren von Schnittstellen mit Klassentypen

Sie können in einem Klassentyp eine oder mehrere Schnittstellen implementieren, mit der `interface` Schlüsselwort, den Namen der Schnittstelle und die `with` -Schlüsselwort, gefolgt von den Definitionen für Schnittstellen Member, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Schnittstellenimplementierungen werden geerbt, sodass keine abgeleiteten Klassen nicht erneut implementieren, sie benötigen.

## <a name="calling-interface-methods"></a>Aufrufen von Schnittstellenmethoden

Schnittstellenmethoden können nur über die Schnittstelle, nicht über ein Objekt des Typs aufgerufen werden, die die Schnittstelle implementiert. Daher möglicherweise müssen Sie Typumwandlung nach oben in den Schnittstellentyp mithilfe der `:>` Operator oder die `upcast` Operator, um diese Methoden aufrufen.

Die Schnittstellenmethode aufrufen, wenn Sie ein Objekt des Typs haben `SomeClass`, müssen Sie Typumwandlung nach oben das Objekt, das den Schnittstellentyp an, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Eine Alternative besteht darin, eine Methode für das Objekt deklariert wird, werden und ruft die Schnittstellenmethode, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementieren von Schnittstellen mit Objektausdrücken

Object-Ausdrücke bieten eine mühelose Möglichkeit, eine Schnittstelle implementieren. Sie sind hilfreich, wenn Sie keinen benannten Typ erstellen, und sollen einfach nur ein Objekt, das die Schnittstellenmethoden, ohne zusätzlichen Methoden unterstützt. Ein Object-Ausdruck wird im folgenden Code veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Schnittstellenvererbung

Schnittstellen können von einem oder mehreren Basisschnittstellen erben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Objektausdrücke](object-expressions.md)
- [Klassen](classes.md)
