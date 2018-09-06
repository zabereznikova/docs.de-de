---
title: NULL-Werte (F#)
description: Erfahren Sie, wie der null-Wert in der Programmiersprache f# verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: 8751ac402c43ddb07fb62e08b6c6d5403cbe9acc
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787897"
---
# <a name="null-values"></a>NULL-Werte

In diesem Thema wird beschrieben, wie der null-Wert in f# verwendet wird.

## <a name="null-value"></a>NULL-Wert

Der null-Wert wird normalerweise nicht in f# nach Werten oder Variablen verwendet. Allerdings wird Sie Null als ein nicht normaler Wert in bestimmten Situationen angezeigt. Wenn ein Typ im F#-definiert ist, Null ist nicht zulässig als reguläre-Wert, wenn die [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) -Attribut auf den Typ angewendet wird. Wenn ein Typ in einer anderen definiert ist, null ist ein möglicher Wert, und bei der Sie die Interaktion mit Typen dieser Art sind, kann null-Werte von F#-Code auftreten.

Für einen Typ im F#-definiert und ausschließlich von f# verwendet, die einzige Möglichkeit, erstellen Sie einen null-Wert direkt unter Verwendung der f#-Bibliothek ist die Verwendung [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) oder [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Allerdings für einen F#-Typ, von anderen .NET-Sprachen verwendet wird, oder null-Werte können auftreten, wenn Sie diesen Typ mit einer API verwenden, die nicht in F# erläutert, wie z. B. .NET Framework geschrieben wird.

Sie können die `option` Typ im F#-Wenn Sie eine Reference-Variable mit einem möglichen Nullwert in einer anderen .NET-Sprache verwenden können. Anstelle von Null, mit dem F#- `option` Typ, den Wert für die Verwendung `None` , wenn kein Objekt vorhanden ist. Sie verwenden den Wert der Option `Some(obj)` mit einem Objekt `obj` , wenn ein Objekt vorhanden ist. Weitere Informationen finden Sie unter [Optionen](../options.md).

Die `null` -Schlüsselwort ist ein gültiges Schlüsselwort in der Sprache f# und müssen Sie es verwenden, bei der Arbeit mit .NET Framework-APIs oder andere APIs, die in einer anderen .NET-Sprache geschrieben werden. Die zwei Situationen, in denen Sie einen null-Wert möglicherweise, werden beim Aufrufen einer API für .NET und einen null-Wert als Argument übergeben, und wenn Sie den Rückgabewert oder Ausgabeparameter von einem Methodenaufruf .NET interpretiert werden soll.

Um einen null-Wert an eine .NET-Methode übergeben zu übergeben, verwenden Sie einfach die `null` Schlüsselwort im aufrufenden Code. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Um einen null-Wert zu interpretieren, der von einer .NET-Methode abgerufen werden, verwenden Sie die Musterabgleich, sofern möglich. Im folgenden Codebeispiel wird veranschaulicht, wie den null-Wert interpretiert, die von zurückgegeben wird mithilfe des musterabgleichs `ReadLine` wenn er versucht, die das Ende eines Eingabedatenstroms zu lesen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

NULL-Werte für f#-Typen können auch auf andere Weise, wie z. B. bei Verwendung von generiert `Array.zeroCreate`, welche Aufrufe `Unchecked.defaultof`. Sie müssen Code zum Beibehalten der null-Werten gekapselt vorsichtig sein. In einer Bibliothek nur für f# vorgesehen sind müssen Sie keinen null-Werte in jeder Funktion überprüfen. Wenn Sie eine Bibliothek für die Interoperation mit anderen .NET-Sprachen schreiben, müssen Sie möglicherweise Hinzufügen von Überprüfungen auf Null Eingabeparametern, und lösen eine `ArgumentNullException`genau wie in c# oder Visual Basic-Code.

Sie können den folgenden Code verwenden, um zu überprüfen, ob ein beliebiger Wert gleich null ist.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Siehe auch

- [Werte](index.md)
- [Vergleichsausdrücke](../match-expressions.md)
