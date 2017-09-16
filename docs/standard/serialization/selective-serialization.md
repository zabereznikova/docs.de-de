---
title: Selektive Serialisierung
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 5cf437604f3072f3dec7b15897fcf5b6788289f0
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="selective-serialization"></a>Selektive Serialisierung
Eine Klasse enthält oft Felder, die nicht serialisiert werden sollten. Angenommen, eine Klasse speichert in einer Membervariablen eine Thread-ID. Wenn die Klasse deserialisiert wird, wird der Thread, dessen ID bei der Serialisierung der Klasse gespeichert wurde, möglicherweise nicht mehr ausgeführt. Daher ist es nicht sinnvoll, diesen Wert zu serialisieren. Sie können verhindern, dass Membervariablen serialisiert werden, indem Sie sie wie folgt mit dem [NonSerialized](xref:System.NonSerializedAttribute)-Attribut markieren.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Legen Sie nach Möglichkeit jedes Objekt, das sicherheitsrelevante Daten enthalten kann, als nicht serialisierbar fest. Wenn das Objekt serialisiert werden muss, wenden Sie das `NonSerialized`-Attribut auf bestimmte Felder an, die vertrauliche Daten speichern. Wenn diese Felder nicht von der Serialisierung ausgeschlossen werden, werden die darin gespeicherten Daten für jeglichen Code verfügbar gemacht, der zur Serialisierung berechtigt ist. Weitere Informationen zum Schreiben von sicherem Serialisierungscode finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Siehe auch  
 [Binäre Serialisierung](binary-serialization.md)   
 [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)   
 [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)
