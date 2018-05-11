---
title: Schnittstellen (F#)
description: Erfahren Sie, wie Schnittstellen f# Sätze von verwandten Elementen angeben, die anderen Klassen implementieren.
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="interfaces"></a>Schnittstellen

*Schnittstellen* geben Sätze von verwandten Elementen, die anderen Klassen implementiert werden.

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
Schnittstellendeklarationen ähneln Klassendeklarationen, mit dem Unterschied, dass keine Member implementiert werden. Stattdessen sind alle Member abstrakt, wie durch das Schlüsselwort angegeben `abstract`. Sie bieten keine keinen Methodentext für abstrakte Methoden. Sie können jedoch eine standardmäßige Implementierung bereitstellen, indem Sie auch eine separate Definition des Members als Methode zusammen mit der `default` Schlüsselwort. Auf diese Weise wird die gleiche Funktion wie eine virtuelle Methode in einer Basisklasse in anderen .NET-Sprachen erstellen. In Klassen, die die Schnittstelle implementieren, kann solche eine virtuelle Methode überschrieben werden.

Der Standardzugriff für Schnittstellen ist `public`.

Sie können jeden Methodenparameter mit normalen F#-Syntax einen Namen geben:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

In den oben genannten `ISprintable` beispielsweise die `Print` Methode verfügt über einen einzelnen Parameter des Typs `string` mit dem Namen `format`.

Es gibt zwei Möglichkeiten, um Schnittstellen zu implementieren: mit Objektausdrücken und mithilfe von Klassentypen. In beiden Fällen enthält die Klasse Typs oder der Objektinstanz Ausdruck Methodentexte für abstrakte Methoden der Schnittstelle. Implementierungen sind spezifisch für jeden Typ, der die Schnittstelle implementiert. Aus diesem Grund können Schnittstellenmethoden für verschiedene Typen voneinander abweichen.

Die Schlüsselwörter `interface` und `end`, die den Beginn und Ende von der Definition kennzeichnen, sind optional, wenn Sie einfachen Syntax verwenden. Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler anweisen abzuleiten, ob der Typ ist eine Klasse oder eine Schnittstelle, durch die Analyse der Konstrukte, die Sie verwenden. Wenn Sie ein Element definieren oder andere Klassensyntax verwenden, wird der Typ als Klasse interpretiert.

.NET Stil Codierung ist auf allen Schnittstellen mit einem Großbuchstaben beginnen `I`.


## <a name="implementing-interfaces-by-using-class-types"></a>Implementieren von Schnittstellen mit Klassentypen
Sie können eine oder mehrere Schnittstellen auf einen Klassentyp implementieren, mit der `interface` Schlüsselwort, den Namen der Schnittstelle, und die `with` Schlüsselwort, gefolgt von den Schnittstellenmemberdefinitionen, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Schnittstellenimplementierungen werden geerbt, sodass keine abgeleiteten Klassen brauchen diese neu implementiert werden muss.


## <a name="calling-interface-methods"></a>Schnittstellenmethoden aufrufen
Schnittstellenmethoden können nur über die Benutzeroberfläche, nicht über ein Objekt des Typs aufgerufen werden, die die Schnittstelle implementiert. Daher möglicherweise müssen Sie Typumwandlung nach oben, um den Schnittstellentyp mithilfe der `:>` Operator oder die `upcast` Operator, um diese Methoden aufrufen.

Die Schnittstellenmethode aufgerufen werden, wenn Sie ein Objekt des Typs haben `SomeClass`, müssen Sie Upcast das Objekt, das den Schnittstellentyp, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Eine Alternative besteht darin, eine Methode für das Objekt deklariert wird, wandelt und ruft die Schnittstellenmethode, wie im folgenden Beispiel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementieren von Schnittstellen mit Objektausdrücken
Objektausdrücke bieten eine kurze Möglichkeit, eine Schnittstelle zu implementieren. Sie sind hilfreich, wenn Sie keinen benannten Typ erstellen, und Sie nur ein Objekt, das die Schnittstellenmethoden, ohne zusätzlichen Methoden unterstützt werden soll. Ein Objektausdrücke wird im folgenden Code veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>Schnittstellenvererbung
Schnittstellen können von einem oder mehreren Basisschnittstellen erben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Objektausdrücke](object-expressions.md)

[Klassen](classes.md)
