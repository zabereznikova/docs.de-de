---
title: Tastatur
description: 'Erfahren Sie, wie Sie F #-Options Typen verwenden können, wenn ein tatsächlicher Wert für einen benannten Wert oder eine Variable nicht vorhanden ist.'
ms.date: 08/13/2020
ms.openlocfilehash: 0618590c10f6ecac51a23483ca0ab6cd66f2df4f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557567"
---
# <a name="options"></a>Tastatur

Der Optionstyp in F # wird verwendet, wenn für einen benannten Wert oder eine Variable kein tatsächlicher Wert vorhanden ist. Eine Option verfügt über einen zugrunde liegenden Typ und kann einen Wert dieses Typs enthalten, oder es kann kein Wert vorhanden sein.

## <a name="remarks"></a>Bemerkungen

Der folgende Code veranschaulicht eine Funktion, die einen Optionstyp generiert.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Wie Sie sehen können, wird generiert, wenn die Eingabe `a` größer als 0 (null) ist `Some(a)` .  Andernfalls `None` wird generiert.

Der Wert `None` wird verwendet, wenn eine Option nicht über einen tatsächlichen Wert verfügt. Andernfalls gibt der Ausdruck `Some( ... )` der Option einen Wert. Die Werte `Some` und `None` sind bei Muster Übereinstimmungen nützlich, wie in der folgenden Funktion `exists` , die zurückgibt, `true` Wenn die Option über einen Wert verfügt, `false` andernfalls.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Using-Optionen

Optionen werden häufig verwendet, wenn eine Suche kein übereinstimmendes Ergebnis zurückgibt, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

Im vorherigen Code wird eine Liste rekursiv durchsucht. Die Funktion `tryFindMatch` nimmt eine Prädikat Funktion `pred` an, die einen booleschen Wert zurückgibt, und eine Liste, die durchsucht werden soll. Wenn ein Element gefunden wird, das das Prädikat erfüllt, wird die Rekursion beendet, und die Funktion gibt den Wert als Option im Ausdruck zurück `Some(head)` . Die Rekursion endet, wenn die leere Liste abgeglichen wird. An diesem Punkt wurde der Wert `head` nicht gefunden, und `None` wird zurückgegeben.

Viele F #-Bibliotheksfunktionen, die eine Auflistung nach einem Wert durchsuchen, der eventuell vorhanden ist, geben den `option` Typ zurück. Gemäß der Konvention beginnen diese Funktionen mit dem `try` Präfix, z [`Seq.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) . b..

Optionen können auch nützlich sein, wenn ein Wert möglicherweise nicht vorhanden ist, z. b. wenn es möglich ist, dass eine Ausnahme ausgelöst wird, wenn Sie versuchen, einen Wert zu erstellen. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

Die `openFile` Funktion im vorherigen Beispiel weist den-Typ auf, `string -> File option` da Sie ein-Objekt zurückgibt, `File` Wenn die Datei erfolgreich geöffnet wird und `None` eine Ausnahme auftritt. Abhängig von der Situation ist es möglicherweise nicht sinnvoll, eine Ausnahme abzufangen, anstatt Sie zu übertragen.

Außerdem ist es weiterhin möglich, `null` oder einen Wert, der NULL ist, an die Groß-/Kleinschreibung einer Option zu übergeben `Some` . Dies wird im allgemeinen vermieden und ist in der Regel in der F #-Programmierung in der Routine, aber aufgrund der Art der Verweis Typen in .net möglich.

## <a name="option-properties-and-methods"></a>Options Eigenschaften und-Methoden

Der Optionstyp unterstützt die folgenden Eigenschaften und Methoden.

|Eigenschaft oder Methode|type|BESCHREIBUNG|
|------------------|----|-----------|
|[None](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#None)|`'T option`|Eine statische Eigenschaft, die es Ihnen ermöglicht, einen Optionswert mit dem `None` Wert zu erstellen.|
|[IsNone](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsNone)|`bool`|Gibt zurück, `true` Wenn die Option den `None` Wert hat.|
|[IsSome](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsSome)|`bool`|Gibt zurück `true` , wenn die Option über einen Wert verfügt, der nicht ist `None` .|
|[Einige](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Some)|`'T option`|Ein statischer Member, der eine Option mit einem Wert erstellt, der nicht ist `None` .|
|[Wert](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Value)|`'T`|Gibt den zugrunde liegenden Wert zurück oder löst eine aus, `System.NullReferenceException` Wenn der Wert ist `None` .|

## <a name="option-module"></a>Options Modul

Es gibt ein Modul, eine [Option](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html), die nützliche Funktionen enthält, die Vorgänge für Optionen ausführen. Einige Funktionen wiederholen die Funktionalität der Eigenschaften, sind aber in Kontexten nützlich, in denen eine Funktion benötigt wird. " [Option. isSome](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isSome) " und " [Option. isNone](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isNone) " sind beide Modulfunktionen, die testen, ob eine Option einen Wert enthält. [Option. Get](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#get) erhält den Wert, falls vorhanden. Wenn kein Wert vorhanden ist, wird eine ausgelöst `System.ArgumentException` .

Die [Option. Bind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#bind) -Funktion führt eine Funktion für den Wert aus, wenn ein Wert vorhanden ist. Die Funktion muss genau ein Argument annehmen, und der Parametertyp muss der Optionstyp sein. Der Rückgabewert der Funktion ist ein weiterer Optionstyp.

Das Options Modul enthält auch Funktionen, die den Funktionen entsprechen, die für Listen, Arrays, Sequenzen und andere Auflistungs Typen verfügbar sind. Zu diesen Funktionen gehören [`Option.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#map) , [`Option.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#iter) , [`Option.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#forall) , [`Option.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#exists) , [`Option.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#foldBack) , [`Option.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#fold) und [`Option.count`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#count) . Diese Funktionen ermöglichen die Verwendung von Optionen wie eine Auflistung von 0 (null) oder einem Element. Weitere Informationen und Beispiele finden Sie in der Erörterung von Sammlungs Funktionen in [Listen](lists.md).

## <a name="converting-to-other-types"></a>Wandeln in andere Typen

Optionen können in Listen oder Arrays konvertiert werden. Wenn eine Option in eine dieser Datenstrukturen konvertiert wird, verfügt die resultierende Datenstruktur über kein oder ein Element. Verwenden Sie, um eine Option in ein Array zu konvertieren [`Option.toArray`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toArray) . Verwenden Sie, um eine Option in eine Liste zu konvertieren [`Option.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toList) .

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
