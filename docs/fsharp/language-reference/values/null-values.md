---
title: NULL-Werte (F#)
description: Erfahren Sie, wie der null-Wert in der Programmiersprache f# verwendet wird.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 68ebd261-51cf-4582-b2dc-44c84d1c2500
ms.openlocfilehash: 01c14de00eb5efd0952145ffc8aabe69d65a3a48
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="null-values"></a>NULL-Werte

In diesem Thema wird beschrieben, wie der null-Wert in f# verwendet wird.


## <a name="null-value"></a>NULL-Wert
Der null-Wert wird normalerweise nicht in f# für Werte oder Variablen verwendet. Allerdings wird Null als einen ungewöhnlichen Wert in bestimmten Situationen angezeigt. Wenn ein Typ in f# definiert ist, Null ist nicht zulässig als reguläre-Wert, wenn die [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) -Attribut auf den Typ angewendet wird. Wenn ein Typ in einer anderen definiert ist, null ist ein möglicher Wert, und wenn Sie die Zusammenarbeit mit solche Typen sind, begegnen F#-Code null-Werte.

Für einen Typ in f# definiert und ausschließlich von f# verwendet, ist die einzige Möglichkeit, einen null-Wert mithilfe der f#-Bibliothek direkt erstellen verwenden [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) oder [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Allerdings für einen Typ [F#], aus anderen Sprachen .NET verwendet wird, oder null-Werte können auftreten, wenn Sie diesen Typ über eine API verwenden, die nicht in F# erläutert, wie .NET Framework geschrieben wird.

Sie können die `option` Typ in F# erläutert werden. Wenn Sie eine Verweisvariable mit einem möglichen null-Wert in einer anderen .NET-Sprache verwenden können. Anstelle von Null, mit dem F#- `option` Typ, verwenden Sie den Wert der Option `None` , wenn kein Objekt vorhanden ist. Sie verwenden den Optionswert `Some(obj)` mit einem Objekt `obj` , wenn ein Objekt vorhanden ist. Weitere Informationen finden Sie unter [Optionen](../options.md).

Die `null` -Schlüsselwort ist ein gültiges Schlüsselwort in der Programmiersprache f# und müssen Sie es bei der Arbeit mit .NET Framework-APIs oder andere APIs, die in einer anderen .NET-Sprache geschrieben werden. Die zwei Situationen, in denen Sie einen null-Wert möglicherweise, werden beim Aufrufen einer .NET API und einen null-Wert als Argument übergeben, und wenn Sie den Rückgabewert oder Ausgabeparameter aus einem Methodenaufruf .NET interpretiert werden soll.

Um einen null-Wert an eine .NET-Methode übergeben zu übergeben, verwenden Sie einfach die `null` Schlüsselwort im aufrufenden Code. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Um einen null-Wert zu interpretieren, der von einer .NET-Methode abgerufen werden, mithilfe des Mustervergleichs möglich. Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe des Mustervergleichs die null-Wert interpretiert werden sollen, die von zurückgegeben wird `ReadLine` beim Versuch, das Ende eines Eingabedatenstroms zu lesen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

NULL-Werte für f#-Typen können auch auf andere Weise, wie z. B. bei Verwendung von generiert `Array.zeroCreate`, welche Aufrufe `Unchecked.defaultof`. Sie müssen mit solchen Code gekapselt null-Werte beibehalten vorsichtig sein. In einer Bibliothek, die nur für f# vorgesehen sind müssen Sie keinen null-Werte in jeder Funktion überprüfen. Wenn Sie eine Bibliothek für die Interoperation mit anderen .NET-Sprachen schreiben, müssen Sie möglicherweise hinzufügen auf Null überprüft Eingabeparameter und löst eine `ArgumentNullException`, wie Sie in c# oder Visual Basic-Code ausführen.

Im folgenden Code können Sie überprüfen, ob ein beliebiger Wert null ist.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Siehe auch
[Werte](index.md)

[Vergleichsausdrücke](../match-expressions.md)
