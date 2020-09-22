---
title: Marshalling von Delegaten als Rückrufmethode
description: Erfahren Sie mehr zum Marshalling eines Delegaten als Rückrufmethode. In diesem Beispiel wird veranschaulicht, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
ms.openlocfilehash: 5e63dc9b7142934c56fb70bce7b878a37a540faa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556023"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Marshalling von Delegaten als Rückrufmethode
In diesem Beispiel wird veranschaulicht, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet. Ein Delegat ist eine Klasse, die einen Verweis auf eine Methode enthalten kann, und gleichbedeutend mit einem typsicheren Funktionszeiger oder einer Rückruffunktion ist.

> [!NOTE]
> Bei Verwendung eines Delegaten in einem Aufruf schützt die Common Language Runtime den Delegaten für die Dauer dieses Aufrufs vor der Garbage Collection. Wenn die nicht verwaltete Funktion jedoch den Delegaten speichert, um ihn nach dem Abschluss des Aufrufs zu verwenden, müssen Sie die Garbage Collection manuell verhindern, bis die nicht verwaltete Funktion mit dem Delegaten beendet wird. Weitere Informationen finden Sie unter [HandleRef-Beispiel](/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) und [GCHandle-Beispiel](/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).

Das Rückrufbeispiel verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:

- `TestCallBack` aus „PinvokeLib.dll“ exportiert.

    ```cpp
    void TestCallBack(FPTR pf, int value);
    ```

- `TestCallBack2` aus „PinvokeLib.dll“ exportiert.

    ```cpp
    void TestCallBack2(FPTR2 pf2, char* value);
    ```

[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktionen enthält.

Die `NativeMethods`-Klasse in diesem Beispiel enthält verwaltete Prototypen für die `TestCallBack`- und `TestCallBack2`-Methoden. Beide Methoden übergeben einen Delegaten als Parameter an eine Rückruffunktion. Die Signatur des Delegaten muss mit der Signatur der Methode übereinstimmen, auf die er verweist. Die `FPtr`- und `FPtr2`-Delegaten verfügen beispielsweise über Signaturen, die identisch mit den `DoSomething`- und `DoSomething2`-Methoden sind.

## <a name="declaring-prototypes"></a>Deklarieren von Prototypen
[!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
[!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
[!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]

## <a name="calling-functions"></a>Aufrufen von Funktionen
[!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
[!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
[!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]

## <a name="see-also"></a>Siehe auch

- [Verschiedene Marshallingbeispiele](/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
- [Datentypen für den Plattformaufruf](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
