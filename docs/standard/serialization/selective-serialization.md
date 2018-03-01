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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb4391e0f78534146ee253f88ad2ae94aa1a11f8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="selective-serialization"></a><span data-ttu-id="12395-102">Selektive Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12395-102">Selective serialization</span></span>
<span data-ttu-id="12395-103">Eine Klasse enthält oft Felder, die nicht serialisiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="12395-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="12395-104">Angenommen, eine Klasse speichert in einer Membervariablen eine Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="12395-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="12395-105">Wenn die Klasse deserialisiert wird, wird der Thread, dessen ID bei der Serialisierung der Klasse gespeichert wurde, möglicherweise nicht mehr ausgeführt. Daher ist es nicht sinnvoll, diesen Wert zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="12395-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="12395-106">Sie können verhindern, dass Membervariablen serialisiert werden, indem Sie sie wie folgt mit dem [NonSerialized](xref:System.NonSerializedAttribute)-Attribut markieren.</span><span class="sxs-lookup"><span data-stu-id="12395-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="12395-107">Legen Sie nach Möglichkeit jedes Objekt, das sicherheitsrelevante Daten enthalten kann, als nicht serialisierbar fest.</span><span class="sxs-lookup"><span data-stu-id="12395-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="12395-108">Wenn das Objekt serialisiert werden muss, wenden Sie das `NonSerialized`-Attribut auf bestimmte Felder an, die vertrauliche Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="12395-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="12395-109">Wenn diese Felder nicht von der Serialisierung ausgeschlossen werden, werden die darin gespeicherten Daten für jeglichen Code verfügbar gemacht, der zur Serialisierung berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="12395-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="12395-110">Weitere Informationen zum Schreiben von sicherem Serialisierungscode finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="12395-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="12395-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12395-111">See also</span></span>  
 [<span data-ttu-id="12395-112">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12395-112">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="12395-113">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12395-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="12395-114">Sicherheit und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12395-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)