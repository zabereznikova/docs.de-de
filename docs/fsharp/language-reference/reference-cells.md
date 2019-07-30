---
title: Referenzzellen
description: Erfahren Sie, wie F# Referenzzellen Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.
ms.date: 05/16/2016
ms.openlocfilehash: faaa4a6b54ff0366163b6821edff7fa4cb2f5a88
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627253"
---
# <a name="reference-cells"></a>Referenzzellen

*Verweis Zellen* sind Speicherorte, die es Ihnen ermöglichen, änderbare Werte mit Verweis Semantik zu erstellen.

## <a name="syntax"></a>Syntax

```fsharp
ref expression
```

## <a name="remarks"></a>Hinweise

Sie verwenden den Operator `ref` vor einem Wert, um eine neue Referenzzelle zu erstellen, die den Wert kapselt. Anschließend können Sie den zugrunde liegenden Wert ändern, da er änderbar ist.

Eine Referenzzelle enthält einen tatsächlichen Wert, sie ist nicht lediglich eine Adresse. Wenn Sie mit dem Operator `ref` eine Referenzzelle erstellen, erstellen Sie eine Kopie des zugrunde liegenden Werts als gekapselten änderbaren Wert.

Mit dem Operator `!` (Bang) können Sie eine Referenzzelle dereferenzieren.

Im folgenden Codebeispiel werden die Deklaration und Verwendung von Referenzzellen veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

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

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

Die Ausgabe lautet wie folgt.

```
10
10
11
12
```

Das Feld `contents` wird für die Kompatibilität mit anderen Versionen von ML bereitgestellt und gibt während der Kompilierung eine Warnung aus. Verwenden Sie die `--mlcompatibility`-Compileroption, um die Warnung zu deaktivieren. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

C#Programmierer sollten wissen, `ref` dass C# in nicht der gleiche ist wie `ref` in F#. Die entsprechende Konstrukte in F# sind [Byrefs](byrefs.md), die ein anderes Konzept als Referenzzellen sind.

Als `mutable`markierte Werte werden möglicherweise automatisch auf `'a ref` herauf gestuft, wenn Sie durch einen Abschluss aufgezeichnet werden. siehe [Werte](./values/index.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Parameter und Argumente](parameters-and-arguments.md)
- [Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)
- [Werte](./values/index.md)
