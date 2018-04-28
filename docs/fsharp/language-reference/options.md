---
title: Optionen (F#)
description: Informationen Sie zum Verwenden von f#-Option, die Typen, wenn ein tatsächlicher Wert möglicherweise nicht vorhanden für einen benannten Wert oder eine Variable.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: ce9be0793c86d8d588fb4f905394bd2383c262e1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="options"></a>Optionen

Der Optionstyp in f# wird verwendet, wenn ein tatsächlichen Wert für einen benannten Wert oder die Variable möglicherweise nicht vorhanden ist. Eine Option verfügt über einen zugrunde liegenden Typ und einen Wert dieses Typs aufnehmen kann, oder es kann kein Wert.

## <a name="remarks"></a>Hinweise
Der folgende Code zeigt eine Funktion, die einen Optionstyp generiert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Wie Sie sehen können, und wenn die Eingabe `a` ist größer als 0 (null) `Some(a)` wird generiert.  Andernfalls `None` generiert wird.

Der Wert `None` wird verwendet, wenn eine Option nicht über einen tatsächlichen Wert verfügt. Andernfalls, den Ausdruck `Some( ... )` bietet die Möglichkeit, das einen Wert. Die Werte `Some` und `None` eignen sich in einem Mustervergleich müssen wie in der folgenden Funktion `exists`, welche gibt `true` , wenn die Option einen Wert hat und `false` Wenn dies nicht der Fall.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Mithilfe der Optionen
Optionen werden häufig verwendet, wenn eine Suche kein entsprechendes Ergebnis zurückgibt, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

Im vorherigen Code ist eine Liste rekursiv durchsucht. Die Funktion `tryFindMatch` nimmt eine Prädikatfunktion `pred` , die einen booleschen Wert und eine zu durchsuchende Liste zurückgibt. Wenn ein Element, das das Prädikat erfüllt gefunden wird, die Rekursion beendet, und die Funktion gibt den Wert als eine Option im Ausdruck `Some(head)`. Die Rekursion endet, wenn die leere Liste verglichen wird. An diesem Punkt den Wert `head` nicht gefunden wurde, und `None` wird zurückgegeben.

Viele F#-Bibliotheksfunktionen Durchsuchen einer Auflistung nach einem Wert, der Rückgabewert ist möglicherweise nicht vorhanden, die die `option` Typ. Gemäß der Konvention werden diese Funktionen, beginnen Sie mit der `try` Präfix, z. B. [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).

Optionen können auch nützlich sein, wenn ein Wert nicht vorhanden, z. B. sein kann wenn es möglich ist, dass eine Ausnahme ausgelöst wird, wenn Sie versuchen, einen Wert zu erstellen. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

Die `openFile` Funktion im vorherigen Beispiel verfügt über `string -> File option` da es gibt eine `File` Objekt, wenn die Datei erfolgreich öffnet und `None` Wenn eine Ausnahme auftritt. Abhängig von der Situation ist es nicht auf eine entsprechende Entwurfsoption mobilgerätverwaltungszertifikat verteilt, anstatt eine Ausnahme abgefangen werden.


## <a name="option-properties-and-methods"></a>Die Eigenschaften und Methoden
Der Optionstyp unterstützt die folgenden Eigenschaften und Methoden.



|Eigenschaft oder Methode|Typ|Beschreibung|
|------------------|----|-----------|
|[Keine](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Eine statische Eigenschaft, mit dem Sie einen Optionswert zu erstellen, verfügt, die `None` Wert.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Gibt `true` , wenn die Option hat die `None` Wert.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Gibt `true` Wenn die Option einen Wert, der nicht `None`.|
|[Einige](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Ein statischer Member, die eine Option erstellt wurde, einen Wert, der nicht `None`.|
|[Wert](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Gibt den zugrunde liegenden Wert zurück oder löst eine `System.NullReferenceException` ist der Wert `None`.|

## <a name="option-module"></a>Option-Modul
Es ist ein Modul [Option](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), enthält nützliche Funktionen, die Vorgänge für Optionen ausführen. Einige Funktionen wiederholen Sie die Funktionalität der Eigenschaften jedoch eignen sich in Kontexte, in denen eine Funktion erforderlich ist. [Option.isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) und [Option.isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) sind Modulfunktionen testen, ob eine Option einen Wert enthält. [Option.Get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) Ruft den Wert ab, sofern vorhanden. Wenn kein Wert vorhanden ist, löst sie `System.ArgumentException`.

Die [Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) Funktion führt eine Funktion auf dem Wert aus, wenn ein Wert vorhanden ist. Die Funktion muss genau ein Argument annehmen, und dessen Parametertyp muss der Optionstyp sein. Der Rückgabewert der Funktion ist eine andere Optionstyp.

Option-Modul enthält auch Funktionen, die die Funktionen entsprechen, die für Listen, Arrays, Sequenzen und anderen Auflistungstypen verfügbar sind. Zu diesen Funktionen zählen [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), und [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876). Diese Funktionen aktivieren, wie eine Auflistung von NULL oder eins-Elementen verwendet werden. Weitere Informationen und Beispiele finden Sie in den Ausführungen Auflistungsfunktionen in [listet](lists.md).


## <a name="converting-to-other-types"></a>Konvertieren in andere Typen
Optionen können in Listen oder Arrays konvertiert werden. Wenn eine Option entweder diese Datenstrukturen konvertiert wird, hat die resultierende Datenstruktur 0 (null) oder ein Element aus. Um eine Option in ein Array zu konvertieren, verwenden [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64). Verwenden Sie zum Konvertieren einer Option auf eine Liste [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[F#-Typen](fsharp-types.md)
