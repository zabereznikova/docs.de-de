---
title: 'Protobuf-Zuordnungen für Wörterbücher: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf-Zuordnungen verwendet werden, um Wörterbuchtypen in .net darzustellen.
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543130"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="36439-103">Protobuf-Zuordnungen für Wörterbücher</span><span class="sxs-lookup"><span data-stu-id="36439-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="36439-104">Es ist wichtig, dass Sie beliebige Auflistungen benannter Werte in Nachrichten darstellen können.</span><span class="sxs-lookup"><span data-stu-id="36439-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="36439-105">In .net wird dies häufig durch Wörterbuchtypen gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="36439-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="36439-106">Die Entsprechung des .net-<xref:System.Collections.Generic.IDictionary%602> Typs in Protokollpuffer (protobuf) ist der `map<key_type, value_type>`-Typ.</span><span class="sxs-lookup"><span data-stu-id="36439-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="36439-107">In diesem Abschnitt wird gezeigt, wie Sie einen `map` Typ in protobuf deklarieren und wie Sie den generierten Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="36439-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="36439-108">Im generierten Code verwenden `map` Felder die `Google.Protobuf.Collections.MapField<TKey, TValue>`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="36439-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="36439-109">Diese Klasse implementiert die standardmäßigen .net-Auflistungs Schnittstellen, einschließlich <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="36439-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="36439-110">Karten Felder können nicht direkt in einer Nachrichten Definition wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="36439-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="36439-111">Sie können jedoch eine Nachricht erstellen, die eine Zuordnung enthält, und `repeated` für den Nachrichtentyp verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="36439-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="36439-112">Verwenden von mapField-Eigenschaften im Code</span><span class="sxs-lookup"><span data-stu-id="36439-112">Using MapField properties in code</span></span>

<span data-ttu-id="36439-113">Die aus `map` Feldern generierten `MapField` Eigenschaften sind schreibgeschützt und werden niemals `null`.</span><span class="sxs-lookup"><span data-stu-id="36439-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="36439-114">Um eine Zuordnungs Eigenschaft festzulegen, verwenden Sie die `Add(IDictionary<TKey,TValue> values)`-Methode der leeren `MapField`-Eigenschaft, um Werte aus einem beliebigen .net-Wörterbuch zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="36439-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="36439-115">Weitere Informationsquellen</span><span class="sxs-lookup"><span data-stu-id="36439-115">Further reading</span></span>

<span data-ttu-id="36439-116">Weitere Informationen zu protobuf finden Sie in der offiziellen [protobuf-Dokumentation](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="36439-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="36439-117">[Zurück](protobuf-enums.md)
>[Weiter](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="36439-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
