---
title: Optionen
description: Erfahren Sie, wie Sie ein F#-Option, die Typen, wenn ein tatsächlicher Wert möglicherweise nicht vorhanden. für ein benannter Wert oder eine Variable.
ms.date: 05/16/2016
ms.openlocfilehash: 9326cf04f53adac7422c09a49a59c4eecd49486d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627347"
---
# <a name="options"></a>Optionen

Der Optionstyp in F# wird verwendet, wenn für einen benannten Wert oder eine Variable kein tatsächlicher Wert vorhanden ist. Eine Option verfügt über einen zugrunde liegenden Typ und kann einen Wert dieses Typs enthalten, oder es kann kein Wert vorhanden sein.

## <a name="remarks"></a>Hinweise

Der folgende Code veranschaulicht eine Funktion, die einen Optionstyp generiert.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Wie Sie sehen können, `a` `Some(a)` wird generiert, wenn die Eingabe größer als 0 (null) ist.  `None` Andernfalls wird generiert.

Der Wert `None` wird verwendet, wenn eine Option nicht über einen tatsächlichen Wert verfügt. Andernfalls gibt der Ausdruck `Some( ... )` der Option einen Wert. Die Werte `Some` und `None` sind bei Muster Übereinstimmungen nützlich, wie in der `exists`folgenden Funktion, `true` die `false` zurückgibt, wenn die Option über einen Wert verfügt, andernfalls.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Verwenden von Optionen

Optionen werden häufig verwendet, wenn eine Suche kein übereinstimmendes Ergebnis zurückgibt, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

Im vorherigen Code wird eine Liste rekursiv durchsucht. Die Funktion `tryFindMatch` nimmt eine Prädikat Funktion `pred` an, die einen booleschen Wert zurückgibt, und eine Liste, die durchsucht werden soll. Wenn ein Element gefunden wird, das das Prädikat erfüllt, wird die Rekursion beendet, und die Funktion gibt den Wert als Option `Some(head)`im Ausdruck zurück. Die Rekursion endet, wenn die leere Liste abgeglichen wird. An diesem Punkt wurde der `head` Wert nicht gefunden, und `None` wird zurückgegeben.

Viele F# Library-Funktionen, die eine Auflistung für einen Wert zu suchen, die möglicherweise nicht in der Rückgabe der `option` Typ. Gemäß der Konvention beginnen diese Funktionen mit dem `try` Präfix, [`Seq.tryFindIndex`](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)z. b.

Optionen können auch nützlich sein, wenn ein Wert möglicherweise nicht vorhanden ist, z. b. wenn es möglich ist, dass eine Ausnahme ausgelöst wird, wenn Sie versuchen, einen Wert zu erstellen. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

Die `openFile` Funktion im vorherigen Beispiel weist den- `string -> File option` Typ auf, da `File` Sie ein-Objekt zurückgibt, `None` wenn die Datei erfolgreich geöffnet wird und eine Ausnahme auftritt. Abhängig von der Situation ist es möglicherweise nicht sinnvoll, eine Ausnahme abzufangen, anstatt Sie zu übertragen.

Außerdem ist es weiterhin möglich, oder einen `null` Wert, der NULL ist, an die `Some` Groß-/Kleinschreibung einer Option zu übergeben. Dies wird im allgemeinen vermieden und ist in der Regel in der F# Routine Programmierung, aber aufgrund der Art der Verweis Typen in .net möglich.

## <a name="option-properties-and-methods"></a>Options Eigenschaften und-Methoden

Der Optionstyp unterstützt die folgenden Eigenschaften und Methoden.

|Eigenschaft oder Methode|Typ|Beschreibung|
|------------------|----|-----------|
|[Keine](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Eine statische Eigenschaft, die es Ihnen ermöglicht, einen Optionswert mit dem `None` Wert zu erstellen.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Gibt `true` zurück, wenn die Option `None` den Wert hat.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Gibt `true` zurück, wenn die Option über einen Wert verfügt `None`, der nicht ist.|
|[Einige](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Ein statischer Member, der eine Option mit einem Wert erstellt, der `None`nicht ist.|
|[Wert](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Gibt den zugrunde liegenden Wert zurück oder löst `System.NullReferenceException` eine aus, wenn `None`der Wert ist.|

## <a name="option-module"></a>Options Modul

Es gibt ein Modul, eine [Option](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), die nützliche Funktionen enthält, die Vorgänge für Optionen ausführen. Einige Funktionen wiederholen die Funktionalität der Eigenschaften, sind aber in Kontexten nützlich, in denen eine Funktion benötigt wird. " [Option. isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) " und " [Option. isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) " sind beide Modulfunktionen, die testen, ob eine Option einen Wert enthält. [Option. Get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) erhält den Wert, falls vorhanden. Wenn kein Wert vorhanden ist, `System.ArgumentException`wird eine ausgelöst.

Die [Option. Bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) -Funktion führt eine Funktion für den Wert aus, wenn ein Wert vorhanden ist. Die Funktion muss genau ein Argument annehmen, und der Parametertyp muss der Optionstyp sein. Der Rückgabewert der Funktion ist ein weiterer Optionstyp.

Das Options Modul enthält auch Funktionen, die den Funktionen entsprechen, die für Listen, Arrays, Sequenzen und andere Auflistungs Typen verfügbar sind. Zu diesen Funktionen [`Option.map`](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622)gehören [`Option.iter`](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [`Option.forall`](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [`Option.exists`](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [,`Option.foldBack`](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb) [,`Option.fold`](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8)und [.`Option.count`](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876) Diese Funktionen ermöglichen die Verwendung von Optionen wie eine Auflistung von 0 (null) oder einem Element. Weitere Informationen und Beispiele finden Sie in der Erörterung von Sammlungs Funktionen in [Listen](lists.md).

## <a name="converting-to-other-types"></a>Wandeln in andere Typen

Optionen können in Listen oder Arrays konvertiert werden. Wenn eine Option in eine dieser Datenstrukturen konvertiert wird, verfügt die resultierende Datenstruktur über kein oder ein Element. Verwenden [`Option.toArray`](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64)Sie, um eine Option in ein Array zu konvertieren. Verwenden [`Option.toList`](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1)Sie, um eine Option in eine Liste zu konvertieren.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
