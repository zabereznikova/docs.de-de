---
title: NULL-Werte
description: 'Erfahren Sie, wie der NULL-Wert in der Programmiersprache F # verwendet wird.'
ms.date: 08/15/2020
ms.openlocfilehash: 3b2c7ebe7b8eff08f7c3e76b9715ccab1bbd5d36
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558347"
---
# <a name="null-values"></a>NULL-Werte

In diesem Thema wird beschrieben, wie der NULL-Wert in F # verwendet wird.

## <a name="null-value"></a>Nullwert

Der NULL-Wert wird normalerweise in F # für Werte oder Variablen nicht verwendet. In bestimmten Situationen wird jedoch NULL als nicht normaler Wert angezeigt. Wenn ein Typ in F # definiert ist, ist NULL nicht als regulärer Wert zulässig, es sei denn, das [allownullliteral](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-allownullliteralattribute.html#Value) -Attribut wird auf den Typ angewendet. Wenn ein Typ in einer anderen .NET-Sprache definiert ist, ist NULL ein möglicher Wert, und wenn Sie mit solchen Typen interagieren, kann der F #-Code NULL-Werte erkennen.

Für einen Typ, der in f # definiert und streng von f # verwendet wird, besteht die einzige Möglichkeit zum Erstellen eines NULL-Werts mit der F #-Bibliothek direkt in der Verwendung von "deaktiviert [. defaultof](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators-unchecked.html#defaultof) " oder " [Array. zeroCreate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate)". Für einen F #-Typ, der von anderen .NET-Sprachen verwendet wird, oder wenn Sie diesen Typ mit einer API verwenden, die nicht in F # geschrieben ist, wie z. b. die .NET Framework, können NULL-Werte auftreten.

Sie können den- `option` Typ in F # verwenden, wenn Sie eine Verweis Variable mit einem möglichen NULL-Wert in einer anderen .NET-Sprache verwenden möchten. Anstelle von NULL mit einem F #- `option` Typ verwenden Sie den Optionswert, `None` Wenn kein-Objekt vorhanden ist. Sie verwenden den Optionswert `Some(obj)` mit einem-Objekt, `obj` Wenn ein-Objekt vorhanden ist. Weitere Informationen finden Sie unter [Optionen](../options.md). Beachten Sie, dass Sie einen Wert immer noch `null` in eine Option packen können, wenn, für den Wert ist `Some x` `x` `null` . Daher ist es wichtig, dass Sie verwenden, `None` Wenn ein Wert ist `null` .

Das `null` Schlüsselwort ist ein gültiges Schlüsselwort in der Sprache F #, das Sie verwenden müssen, wenn Sie mit .NET Framework-APIs oder anderen APIs arbeiten, die in einer anderen .NET-Sprache geschrieben sind. Die zwei Situationen, in denen Sie möglicherweise einen NULL-Wert benötigen, sind, wenn Sie eine .NET-API aufrufen und einen NULL-Wert als Argument übergeben, und wenn Sie den Rückgabewert oder einen Output-Parameter von einem .NET-Methoden Aufrufwert interpretieren.

Um einen NULL-Wert an eine .NET-Methode zu übergeben, verwenden Sie einfach das- `null` Schlüsselwort im aufrufenden Code. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Um einen NULL-Wert zu interpretieren, der aus einer .NET-Methode abgerufen wird, verwenden Sie den Musterabgleich, wenn möglich. Im folgenden Codebeispiel wird gezeigt, wie der Muster Vergleich verwendet wird, um den NULL-Wert zu interpretieren, der von zurückgegeben wird, `ReadLine` Wenn er versucht, über das Ende eines Eingabedaten Stroms hinaus zu lesen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

NULL-Werte für F #-Typen können auch auf andere Weise generiert werden, z. b. Wenn Sie verwenden `Array.zeroCreate` , das aufruft `Unchecked.defaultof` . Sie müssen mit diesem Code vorsichtig sein, damit die NULL-Werte gekapselt bleiben. In einer Bibliothek, die nur für F # vorgesehen ist, müssen Sie nicht in jeder Funktion auf NULL-Werte überprüfen. Wenn Sie eine Bibliothek für die Interoperation mit anderen .NET-Sprachen schreiben, müssen Sie möglicherweise Überprüfungen für NULL-Eingabeparameter hinzufügen und einen `ArgumentNullException` wie in c# oder Visual Basic Code auslösen.

Sie können den folgenden Code verwenden, um zu überprüfen, ob ein beliebiger Wert NULL ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Siehe auch

- [Werte](index.md)
- [Vergleichsausdrücke](../match-expressions.md)
