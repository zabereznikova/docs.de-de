---
title: Referenzzellen (F#)
description: Erfahren Sie, wie F# Referenzzellen Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.
ms.date: 05/16/2016
ms.openlocfilehash: e2e1a91c62fd76e4992bc5ae11bb672766850718
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "44192255"
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

C#-Programmierer sollten wissen, dass `ref` in c# ist nicht dasselbe wie `ref` in F# erläutert werden. Die entsprechende Konstrukte in F# sind [Byrefs](byrefs.md), die ein anderes Konzept als Referenzzellen sind.

Werte gekennzeichnet, als `mutable`automatisch auf heraufgestuft werden `'a ref` ; Closure erfasst finden Sie unter [Werte](values/index.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Parameter und Argumente](parameters-and-arguments.md)
- [Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)
- [Werte](values/index.md)
