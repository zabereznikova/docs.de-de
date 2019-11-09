---
title: 'Protobuf-Zuordnungen für Wörterbücher: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie protobuf-Zuordnungen zur Darstellung von verwenden. Die Wörterbuchtypen von net.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: aef6b0f378e7a63f362ec42642cae15b32d49a08
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841450"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="9f9aa-103">Protobuf-Zuordnungen für Wörterbücher</span><span class="sxs-lookup"><span data-stu-id="9f9aa-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="9f9aa-104">Es ist wichtig, dass Sie beliebige Auflistungen benannter Werte in Nachrichten darstellen können.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="9f9aa-105">In .net wird dies häufig mithilfe von Wörterbuchtypen gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="9f9aa-106">Die protobuf-Entsprechung des .net-<xref:System.Collections.Generic.IDictionary%602> Typs ist der `map<key_type, value_type>`-Typ.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="9f9aa-107">In diesem Abschnitt wird gezeigt, wie Sie eine `map` in protobuf deklarieren und wie Sie den generierten Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="9f9aa-108">Im generierten Code verwenden `map` Felder die `Google.Protobuf.Collections.MapField<TKey, TValue>`-Klasse, die die .NET-Standard Auflistungs Schnittstellen implementiert, einschließlich <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="9f9aa-109">Zuordnungs Felder können nicht direkt in einer Nachrichten Definition wiederholt werden, Sie können jedoch eine Nachricht erstellen, die eine Zuordnung enthält, und `repeated` für den Nachrichtentyp verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9f9aa-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="9f9aa-110">Verwenden von mapField-Eigenschaften im Code</span><span class="sxs-lookup"><span data-stu-id="9f9aa-110">Using MapField properties in code</span></span>

<span data-ttu-id="9f9aa-111">Die aus `map` Feldern generierten `MapField` Eigenschaften sind schreibgeschützt und werden niemals `null`.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="9f9aa-112">Um eine Zuordnungs Eigenschaft festzulegen, verwenden Sie die `Add(IDictionary<TKey,TValue> values)`-Methode der leeren `MapField`-Eigenschaft, um Werte aus einem beliebigen .net-Wörterbuch zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9f9aa-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="9f9aa-113">Weiterführende Themen</span><span class="sxs-lookup"><span data-stu-id="9f9aa-113">Further reading</span></span>

<span data-ttu-id="9f9aa-114">Weitere Informationen zu protobuf finden Sie in der offiziellen [protobuf-Dokumentation](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="9f9aa-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9f9aa-115">[Zurück](protobuf-enums.md)
>[Weiter](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="9f9aa-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
