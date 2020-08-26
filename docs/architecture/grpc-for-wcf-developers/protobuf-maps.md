---
title: 'Protobuf-Zuordnungen für Wörterbücher: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf-Zuordnungen verwendet werden, um Wörterbuchtypen in .net darzustellen.
ms.date: 09/09/2019
ms.openlocfilehash: 2c2ae76d47b2309227d22235b5acbe2afa794158
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867464"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="f0f40-103">Protobuf-Zuordnungen für Wörterbücher</span><span class="sxs-lookup"><span data-stu-id="f0f40-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="f0f40-104">Es ist wichtig, dass Sie beliebige Auflistungen benannter Werte in Nachrichten darstellen können.</span><span class="sxs-lookup"><span data-stu-id="f0f40-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="f0f40-105">In .net wird dies häufig durch Wörterbuchtypen gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="f0f40-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="f0f40-106">Die Entsprechung des .net- <xref:System.Collections.Generic.IDictionary%602> Typs in Protokollpuffer (protobuf) ist der- `map<key_type, value_type>` Typ.</span><span class="sxs-lookup"><span data-stu-id="f0f40-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="f0f40-107">In diesem Abschnitt wird gezeigt, wie Sie einen `map` Typ in protobuf deklarieren und wie Sie den generierten Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0f40-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="f0f40-108">Im generierten Code `map` werden Felder durch schreibgeschützte Eigenschaften des- [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] Typs dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f0f40-108">In the generated code, `map` fields are represented by read-only properties of the [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] type.</span></span> <span data-ttu-id="f0f40-109">Dieser Typ implementiert die .NET-Standard Auflistungs Schnittstellen, einschließlich <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="f0f40-109">This type implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="f0f40-110">Karten Felder können nicht direkt in einer Nachrichten Definition wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="f0f40-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="f0f40-111">Sie können jedoch eine Nachricht erstellen, die eine Zuordnung enthält und `repeated` für den Nachrichtentyp verwendet wird, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f0f40-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="f0f40-112">Verwenden von mapField-Eigenschaften im Code</span><span class="sxs-lookup"><span data-stu-id="f0f40-112">Using MapField properties in code</span></span>

<span data-ttu-id="f0f40-113">Die `MapField` aus Feldern generierten Eigenschaften sind schreibgeschützt `map` und werden niemals verwendet `null` .</span><span class="sxs-lookup"><span data-stu-id="f0f40-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="f0f40-114">Verwenden Sie zum Festlegen einer Zuordnungs Eigenschaft die- `Add(IDictionary<TKey,TValue> values)` Methode für die leere- `MapField` Eigenschaft, um Werte aus einem beliebigen .net-Wörterbuch zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f0f40-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="f0f40-115">Weitere nützliche Informationen</span><span class="sxs-lookup"><span data-stu-id="f0f40-115">Further reading</span></span>

<span data-ttu-id="f0f40-116">Weitere Informationen zu protobuf finden Sie in der offiziellen [protobuf-Dokumentation](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="f0f40-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
><span data-ttu-id="f0f40-117">[Zurück](protobuf-enums.md)
>[Weiter](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="f0f40-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
