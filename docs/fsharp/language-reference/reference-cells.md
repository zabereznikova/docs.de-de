---
title: Referenzzellen (F#)
description: Erfahren Sie, wie f# Referenzzellen Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.
ms.date: 05/16/2016
ms.openlocfilehash: 133aec6b162a13306a05c9afa172f859890565eb
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892419"
---
# <a name="reference-cells"></a>Referenzzellen

*Referenzzellen* sind Speicherorte, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.

## <a name="syntax"></a>Syntax

```fsharp
ref expression
```

## <a name="remarks"></a>Hinweise

Sie verwenden den Operator `ref` vor einem Wert, um eine neue Referenzzelle zu erstellen, die den Wert kapselt. Anschließend können Sie den zugrunde liegenden Wert ändern, da er änderbar ist.

Eine Referenzzelle enthält einen tatsächlichen Wert, sie ist nicht lediglich eine Adresse. Wenn Sie mit dem Operator `ref` eine Referenzzelle erstellen, erstellen Sie eine Kopie des zugrunde liegenden Werts als gekapselten änderbaren Wert.

Mit dem Operator `!` (Bang) können Sie eine Referenzzelle dereferenzieren.

Im folgenden Codebeispiel werden die Deklaration und Verwendung von Referenzzellen veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

Die Ausgabe lautet `50`.

Referenzzellen sind Instanzen des generischen `Ref`-Datensatztyps, der wie folgt deklariert wird.

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

Der Typ `'a ref` ist ein Synonym für `Ref<'a>`. Der Compiler und IntelliSense in der IDE zeigen erstere Version für diesen Typ an, jedoch ist letztere Version die zugrunde liegende Definition.

Mit dem Operator `ref` wird eine neue Referenzzelle erstellt. Der folgende Code ist die Deklaration des Operators `ref`.

```fsharp
let ref x = { contents = x }
```

Die folgende Tabelle enthält die Funktionen, die für die Referenzzelle verfügbar sind.

|Operator, Member oder Feld|Beschreibung|Typ|Definition|
|--------------------------|-----------|----|----------|
|`!` (Dereferenzierungsoperator)|Gibt den zugrunde liegenden Wert zurück.|`'a ref -> 'a`|`let (!) r = r.contents`|
|`:=` (Zuweisungsoperator)|Ändert den zugrunde liegenden Wert.|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|`ref` (Operator)|Kapselt einen Wert in einer neuen Referenzzelle.|`'a -> 'a ref`|`let ref x = { contents = x }`|
|`Value` (Eigenschaft)|Ruft den zugrunde liegenden Wert ab oder legt diesen fest.|`unit -> 'a`|`member x.Value = x.contents`|
|`contents` (Datensatzfeld)|Ruft den zugrunde liegenden Wert ab oder legt diesen fest.|`'a`|`let ref x = { contents = x }`|
Es gibt mehrere Möglichkeiten, auf den zugrunde liegenden Wert zuzugreifen. Der vom Dereferenzierungsoperator (`!`) zurückgegebene Wert ist kein zuweisbarer Wert. Wenn Sie den zugrunde liegenden Wert ändern, müssen Sie daher stattdessen den Zuweisungsoperator (`:=`) verwenden.

Sowohl die `Value`-Eigenschaft als auch das `contents`-Feld sind zuweisbare Werte. Daher können Sie diese verwenden, um auf den zugrunde liegenden Wert zuzugreifen oder diesen zu ändern, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

Die Ausgabe lautet wie folgt.

```
10
10
11
12
```

Das Feld `contents` wird für die Kompatibilität mit anderen Versionen von ML bereitgestellt und gibt während der Kompilierung eine Warnung aus. Verwenden Sie die `--mlcompatibility`-Compileroption, um die Warnung zu deaktivieren. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

Im folgenden Code wird die Verwendung von Referenzzellen beim Übergeben von Parametern veranschaulicht. Der Typ Incrementor hat es sich um eine Methode erhöhen, die einen Parameter akzeptiert, der Byref in den Parametertyp enthält. Byref im Parametertyp gibt an, dass der Aufrufer eine Referenzzelle oder die Adresse einer typischen Variablen des angegebenen Typs, in diesem Fall "int". übergeben müssen Der restliche Code wird veranschaulicht, wie Inkrement mit beide Typen von Argumenten aufrufen, und zeigt die Verwendung von Ref-Operator für eine Variable zum Erstellen einer Referenzzelle (Ref myDelta1). Anschließend wird die Verwendung des address-of-Operators (&amp;) zum Generieren eines entsprechenden Arguments veranschaulicht. Schließlich wird erneut die Increment-Methode aufgerufen, mithilfe einer Referenzzelle, die mit einer Let-Bindung deklariert wird. Die letzte Codezeile veranschaulicht die Verwendung der! Operator zu dereferenzieren der Referenzzelle für den Druck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

Weitere Informationen zur Übergabe als Verweis finden Sie unter [Parameter und Argumente](parameters-and-arguments.md).

>[!NOTE]
C#-Programmierer sollten wissen, dass Ref anders als in f# funktioniert, als dies in c# der Fall ist. Z. B. die Verwendung von Ref, wenn Sie ein Argument übergeben die gleiche Auswirkung in f# keine wie in c#.

>[!NOTE]
`mutable` Variablen automatisch auf heraufgestuft werden `'a ref` ; Closure erfasst finden Sie unter [Werte](values/index.md).

## <a name="consuming-c-ref-returns"></a>Verarbeiten von c# `ref` zurückgibt

Ab f# 4.1 können Sie nutzen können `ref` gibt, die in c# generiert.  Das Ergebnis eines solchen Aufrufs ist eine `byref<_>` Zeiger.

Die folgende C#-Methode:

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

Können transparent von f# mit keine spezielle Syntax aufgerufen werden:

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

Sie können auch deklarieren die Funktionen dieser Vorgang kann eine `ref` zurückgeben als Eingabe, z.B.:

```fsharp
let f (x: byref<int>) = &x
```

Es gibt derzeit keine Möglichkeit zum Generieren einer `ref` zurück in f# die in c# genutzt werden kann.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Parameter und Argumente](parameters-and-arguments.md)
- [Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)
- [Werte](values/index.md)
