---
title: NULL-Werte
description: Erfahren Sie, wie der null-Wert in der Programmiersprache F# verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: 58c54065a98a84c4d4e912cbc42d59cfea8c6de1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610995"
---
# <a name="null-values"></a>NULL-Werte

In diesem Thema wird beschrieben, wie der null-Wert in F# verwendet wird.

## <a name="null-value"></a>NULL-Wert

Der null-Wert wird normalerweise nicht in F# nach Werten oder Variablen verwendet. Allerdings wird Sie Null als ein nicht normaler Wert in bestimmten Situationen angezeigt. Wenn ein Typ, im definiert ist F#, Null wird als regulärer Wert nicht zulässig, es sei denn, die [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) -Attribut auf den Typ angewendet wird. Wenn ein Typ in einer anderen definiert ist, wird Null ist ein möglicher Wert aus, und wenn Sie eine Interaktion mit Typen dieser Art sind Ihre F# Code können auftreten, null-Werte.

Für einen Typ im F#-definiert und ausschließlich von F# verwendet, die einzige Möglichkeit, erstellen Sie einen null-Wert direkt unter Verwendung der F#-Bibliothek ist die Verwendung [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) oder [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Für eine F# Typ, der von anderen .NET-Sprachen verwendet wird oder wenn Sie diesen Typ mit einer API verwenden, die nicht, in geschrieben werden F#, z. B. .NET Framework, der null-Werte können auftreten.

Können Sie die `option` geben F# Wenn können eine Verweisvariable mit einem möglichen Nullwert in einer anderen .NET-Sprache. Anstelle von Null mit einem F# `option` Typ, den Wert für die Verwendung `None` , wenn kein Objekt vorhanden ist. Sie verwenden den Wert der Option `Some(obj)` mit einem Objekt `obj` , wenn ein Objekt vorhanden ist. Weitere Informationen finden Sie unter [Optionen](../options.md).

Die `null` -Schlüsselwort ist ein gültiges Schlüsselwort in der Sprache F# und müssen Sie es verwenden, bei der Arbeit mit .NET Framework-APIs oder andere APIs, die in einer anderen .NET-Sprache geschrieben werden. Die zwei Situationen, in denen Sie einen null-Wert möglicherweise, werden beim Aufrufen einer API für .NET und einen null-Wert als Argument übergeben, und wenn Sie den Rückgabewert oder Ausgabeparameter von einem Methodenaufruf .NET interpretiert werden soll.

Um einen null-Wert an eine .NET-Methode übergeben zu übergeben, verwenden Sie einfach die `null` Schlüsselwort im aufrufenden Code. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Um einen null-Wert zu interpretieren, der von einer .NET-Methode abgerufen werden, verwenden Sie die Musterabgleich, sofern möglich. Im folgenden Codebeispiel wird veranschaulicht, wie den null-Wert interpretiert, die von zurückgegeben wird mithilfe des musterabgleichs `ReadLine` wenn er versucht, die das Ende eines Eingabedatenstroms zu lesen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

NULL-Werte für F#-Typen können auch auf andere Weise, wie z. B. bei Verwendung von generiert `Array.zeroCreate`, welche Aufrufe `Unchecked.defaultof`. Sie müssen Code zum Beibehalten der null-Werten gekapselt vorsichtig sein. In einer Bibliothek nur für F# vorgesehen sind müssen Sie keinen null-Werte in jeder Funktion überprüfen. Wenn Sie eine Bibliothek für die Interoperation mit anderen .NET-Sprachen schreiben, müssen Sie möglicherweise Hinzufügen von Überprüfungen auf Null Eingabeparametern, und lösen eine `ArgumentNullException`genau wie in c# oder Visual Basic-Code.

Sie können den folgenden Code verwenden, um zu überprüfen, ob ein beliebiger Wert gleich null ist.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Siehe auch

- [Werte](index.md)
- [Vergleichsausdrücke](../match-expressions.md)