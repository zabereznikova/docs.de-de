---
title: Marshalling von Delegaten als Rückrufmethode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 579bc56a538707fd19d6d089c7f3c0c0561ea9eb
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454420"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Marshalling von Delegaten als Rückrufmethode
In diesem Beispiel wird veranschaulicht, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet. Ein Delegat ist eine Klasse, die einen Verweis auf eine Methode enthalten kann, und gleichbedeutend mit einem typsicheren Funktionszeiger oder einer Rückruffunktion ist.  
  
> [!NOTE]
>  Bei Verwendung eines Delegaten in einem Aufruf schützt die Common Language Runtime den Delegaten für die Dauer dieses Aufrufs vor der Garbage Collection. Wenn die nicht verwaltete Funktion jedoch den Delegaten speichert, um ihn nach dem Abschluss des Aufrufs zu verwenden, müssen Sie die Garbage Collection manuell verhindern, bis die nicht verwaltete Funktion mit dem Delegaten beendet wird. Weitere Informationen finden Sie unter [HandleRef-Beispiel](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) und [GCHandle-Beispiel](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).  
  
 Das Rückrufbeispiel verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:  
  
-   **TestCallBack** aus „PinvokeLib.dll“ exportiert.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2** aus „PinvokeLib.dll“ exportiert.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktionen enthält.  
  
 Die `LibWrap`-Klasse in diesem Beispiel enthält verwaltete Prototypen für die `TestCallBack`- und `TestCallBack2`-Methoden. Beide Methoden übergeben einen Delegaten als Parameter an eine Rückruffunktion. Die Signatur des Delegaten muss mit der Signatur der Methode übereinstimmen, auf die er verweist. Die `FPtr`- und `FPtr2`-Delegaten verfügen beispielsweise über Signaturen, die identisch mit den `DoSomething`- und `DoSomething2`-Methoden sind.  
  
## <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verschiedene Marshallingbeispiele](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))  
 [Datentypen für den Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
