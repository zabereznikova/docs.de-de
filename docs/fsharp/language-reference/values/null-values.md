---
title: NULL-Werte
description: Erfahren Sie, wie der null-Wert in der Programmiersprache F# verwendet wird.
ms.date: 03/22/2019
ms.openlocfilehash: 2038c0a461fec9884c51edd50c3c9f336104e30e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630804"
---
# <a name="null-values"></a>NULL-Werte

In diesem Thema wird beschrieben, wie der null-Wert in F# verwendet wird.

## <a name="null-value"></a>NULL-Wert

Der null-Wert wird normalerweise nicht in F# nach Werten oder Variablen verwendet. In bestimmten Situationen wird jedoch NULL als nicht normaler Wert angezeigt. Wenn ein Typ in F#definiert ist, ist NULL nicht als regulärer Wert zulässig, es sei denn, das [allownullliteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) -Attribut wird auf den Typ angewendet. Wenn ein Typ in einer anderen .NET-Sprache definiert ist, ist NULL ein möglicher Wert, und wenn Sie mit solchen Typen interagieren, kann der F# Code NULL-Werte sehen.

Für einen Typ im F#-definiert und ausschließlich von F# verwendet, die einzige Möglichkeit, erstellen Sie einen null-Wert direkt unter Verwendung der F#-Bibliothek ist die Verwendung [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) oder [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Für einen F# Typ, der von anderen .NET-Sprachen verwendet wird, oder wenn Sie diesen Typ mit einer API verwenden, die nicht in F#geschrieben ist, z. b. die .NET Framework, können NULL-Werte auftreten.

Sie können den `option` -Typ in F# verwenden, wenn Sie eine Verweis Variable mit einem möglichen NULL-Wert in einer anderen .NET-Sprache verwenden möchten. Anstelle von NULL mit einem F# `option` -Typ verwenden Sie den Optionswert `None` , wenn kein-Objekt vorhanden ist. Sie verwenden den Optionswert `Some(obj)` mit `obj` einem-Objekt, wenn ein-Objekt vorhanden ist. Weitere Informationen finden Sie unter [Optionen](../options.md). Beachten Sie `null` , dass Sie einen Wert immer noch in eine Option packen können, wenn, `x` für `null` `Some x`den Wert ist. Daher ist es wichtig, dass Sie verwenden `None` , wenn ein Wert ist. `null`

Die `null` -Schlüsselwort ist ein gültiges Schlüsselwort in der Sprache F# und müssen Sie es verwenden, bei der Arbeit mit .NET Framework-APIs oder andere APIs, die in einer anderen .NET-Sprache geschrieben werden. Die zwei Situationen, in denen Sie möglicherweise einen NULL-Wert benötigen, sind, wenn Sie eine .NET-API aufrufen und einen NULL-Wert als Argument übergeben, und wenn Sie den Rückgabewert oder einen Output-Parameter von einem .NET-Methoden Aufrufwert interpretieren.

Um einen NULL-Wert an eine .NET-Methode zu übergeben, `null` verwenden Sie einfach das-Schlüsselwort im aufrufenden Code. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Um einen NULL-Wert zu interpretieren, der aus einer .NET-Methode abgerufen wird, verwenden Sie den Musterabgleich, wenn möglich. Im folgenden Codebeispiel wird gezeigt, wie der Muster Vergleich verwendet wird, um den NULL-Wert `ReadLine` zu interpretieren, der von zurückgegeben wird, wenn er versucht, über das Ende eines Eingabedaten Stroms hinaus zu lesen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

NULL-Werte für F#-Typen können auch auf andere Weise, wie z. B. bei Verwendung von generiert `Array.zeroCreate`, welche Aufrufe `Unchecked.defaultof`. Sie müssen mit diesem Code vorsichtig sein, damit die NULL-Werte gekapselt bleiben. In einer Bibliothek nur für F# vorgesehen sind müssen Sie keinen null-Werte in jeder Funktion überprüfen. Wenn Sie eine Bibliothek für die Interoperation mit anderen .NET-Sprachen schreiben, müssen Sie möglicherweise Überprüfungen für NULL-Eingabeparameter hinzu `ArgumentNullException`fügen und einen wie in C# oder Visual Basic Code auslösen.

Sie können den folgenden Code verwenden, um zu überprüfen, ob ein beliebiger Wert NULL ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Siehe auch

- [Werte](index.md)
- [Vergleichsausdrücke](../match-expressions.md)
