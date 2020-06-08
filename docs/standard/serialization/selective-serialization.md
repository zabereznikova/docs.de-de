---
title: Selektive Serialisierung
description: In diesem Artikel wird gezeigt, wie Sie Felder mit dem NonSerialized-Attribut markieren, wodurch die Serialisierung des Feldes verhindert wird.
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: 74113979f0ebe77319ae308c2a669e91d8cb4209
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84278414"
---
# <a name="selective-serialization"></a><span data-ttu-id="df638-103">Selektive Serialisierung</span><span class="sxs-lookup"><span data-stu-id="df638-103">Selective serialization</span></span>
<span data-ttu-id="df638-104">Eine Klasse enthält oft Felder, die nicht serialisiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="df638-104">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="df638-105">Angenommen, eine Klasse speichert in einer Membervariablen eine Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="df638-105">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="df638-106">Wenn die Klasse deserialisiert wird, wird der Thread, dessen ID bei der Serialisierung der Klasse gespeichert wurde, möglicherweise nicht mehr ausgeführt. Daher ist es nicht sinnvoll, diesen Wert zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="df638-106">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="df638-107">Sie können verhindern, dass Membervariablen serialisiert werden, indem Sie sie wie folgt mit dem [NonSerialized](xref:System.NonSerializedAttribute)-Attribut markieren.</span><span class="sxs-lookup"><span data-stu-id="df638-107">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="df638-108">Legen Sie nach Möglichkeit jedes Objekt, das sicherheitsrelevante Daten enthalten kann, als nicht serialisierbar fest.</span><span class="sxs-lookup"><span data-stu-id="df638-108">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="df638-109">Wenn das Objekt serialisiert werden muss, wenden Sie das `NonSerialized`-Attribut auf bestimmte Felder an, die vertrauliche Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="df638-109">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="df638-110">Wenn diese Felder nicht von der Serialisierung ausgeschlossen werden, werden die darin gespeicherten Daten für jeglichen Code verfügbar gemacht, der zur Serialisierung berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="df638-110">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="df638-111">Weitere Informationen zum Schreiben von sicherem Serialisierungscode finden Sie unter [Sicherheit und Serialisierung](../../framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="df638-111">For more information about writing secure serialization code, see [Security and Serialization](../../framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="df638-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df638-112">See also</span></span>

- [<span data-ttu-id="df638-113">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="df638-113">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="df638-114">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="df638-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="df638-115">Sicherheit und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="df638-115">Security and Serialization</span></span>](../../framework/misc/security-and-serialization.md)
