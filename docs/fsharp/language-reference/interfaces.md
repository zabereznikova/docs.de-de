---
title: Schnittstellen
description: 'Erfahren Sie, wie F #-Schnittstellen Sätze verwandter Member angeben, die von anderen Klassen implementiert werden.'
ms.date: 08/15/2020
ms.openlocfilehash: 36272b52fcff83e8e8a54ccc4e6ecd1252a91819
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558126"
---
# <a name="interfaces"></a>Schnittstellen

*Schnittstellen* geben Sätze verwandter Member an, die von anderen Klassen implementiert werden.

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

## <a name="remarks"></a>Bemerkungen

Schnittstellen Deklarationen ähneln Klassen Deklarationen, außer dass keine Member implementiert werden. Stattdessen sind alle Member abstrakt, wie durch das-Schlüsselwort angegeben `abstract` . Sie stellen keinen Methoden Text für abstrakte Methoden bereit. Sie können jedoch auch eine Standard Implementierung bereitstellen, indem Sie eine separate Definition des Members als Methode in Verbindung mit dem- `default` Schlüsselwort einschließen. Dies entspricht dem Erstellen einer virtuellen Methode in einer Basisklasse in anderen .NET-Sprachen. Eine solche virtuelle Methode kann in Klassen, die die-Schnittstelle implementieren, überschrieben werden.

Der Standard Zugriff für Schnittstellen ist `public` .

Sie können jedem Methoden Parameter optional einen Namen über die normale F #-Syntax übergeben:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

Im obigen `ISprintable` Beispiel verfügt die- `Print` Methode über einen einzelnen Parameter vom Typ `string` mit dem Namen `format` .

Es gibt zwei Möglichkeiten zum Implementieren von Schnittstellen: mithilfe von Objekt Ausdrücken und mithilfe von Klassentypen. In beiden Fällen stellt der Klassentyp oder der Objekt Ausdruck Methoden Körper für abstrakte Methoden der Schnittstelle bereit. Implementierungen sind spezifisch für jeden Typ, der die-Schnittstelle implementiert. Daher können sich Schnittstellen Methoden für verschiedene Typen voneinander unterscheiden.

Die Schlüsselwörter `interface` und `end` , die den Anfang und das Ende der Definition markieren, sind optional, wenn Sie die Lightweight-Syntax verwenden. Wenn Sie diese Schlüsselwörter nicht verwenden, versucht der Compiler zu ableiten, ob der Typ eine Klasse oder eine Schnittstelle ist, indem die Konstrukte analysiert werden, die Sie verwenden. Wenn Sie einen Member definieren oder eine andere Klassen Syntax verwenden, wird der Typ als Klasse interpretiert.

Der .net-Codierungsstil besteht darin, alle Schnittstellen mit einem Kapital zu beginnen `I` .

Sie können mehrere Parameter auf zweierlei Weise angeben: F #-Style und. NET-Stil. Beide werden auf die gleiche Weise für .net-Consumer kompiliert, f #-Style erzwingt jedoch f #-Aufrufer, die Parameter Anwendung und in f # zu verwenden. Der Netzwerk Stil erzwingt F #-Aufrufer, eine Tupel-Argument Anwendung zu verwenden.

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a>Implementieren von Schnittstellen mithilfe von Klassentypen

Sie können eine oder mehrere Schnittstellen in einem Klassentyp mithilfe des `interface` -Schlüssel Worts, des Namens der-Schnittstelle und des- `with` Schlüssel Worts implementieren, gefolgt von den Schnittstellen Element Definitionen, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Schnittstellen Implementierungen werden geerbt, sodass alle abgeleiteten Klassen Sie nicht neu implementieren müssen.

## <a name="calling-interface-methods"></a>Aufrufen von Schnittstellen Methoden

Schnittstellen Methoden können nur über die-Schnittstelle aufgerufen werden, nicht über ein Objekt des Typs, der die-Schnittstelle implementiert. Folglich müssen Sie ggf. den- `:>` Operator oder den-Operator verwenden, um `upcast` Diese Methoden aufzurufen.

Um die Schnittstellen Methode aufzurufen, wenn Sie ein Objekt vom Typ haben `SomeClass` , müssen Sie das Objekt in den Schnittstellentyp umwandeln, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Eine Alternative besteht darin, eine Methode für das Objekt zu deklarieren, das die Schnittstellen Methode upwandelt und aufruft, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementieren von Schnittstellen mithilfe von Objekt Ausdrücken

Objekt Ausdrücke bieten eine kurze Möglichkeit, eine Schnittstelle zu implementieren. Sie sind nützlich, wenn Sie keinen benannten Typ erstellen müssen und nur ein Objekt, das die Schnittstellen Methoden unterstützt, ohne zusätzliche Methoden. Ein Objekt Ausdruck wird im folgenden Code veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Schnittstellenvererbung

Schnittstellen können von einer oder mehreren Basis Schnittstellen erben.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Objektausdrücke](object-expressions.md)
- [Klassen](classes.md)
