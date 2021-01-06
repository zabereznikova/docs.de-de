---
title: 'Protobuf-Zuordnungen für Wörterbücher: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf-Zuordnungen verwendet werden, um Wörterbuchtypen in .net darzustellen.
ms.date: 12/15/2020
ms.openlocfilehash: d38270d4bc320cf1f758080c18843ed1d716b350
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938545"
---
# <a name="protobuf-maps-for-dictionaries"></a>Protobuf-Zuordnungen für Wörterbücher

Es ist wichtig, dass Sie beliebige Auflistungen benannter Werte in Nachrichten darstellen können. In .net wird diese Aktivität häufig durch Wörterbuchtypen verarbeitet. Die Entsprechung des .net- <xref:System.Collections.Generic.IDictionary%602> Typs in Protokollpuffer (protobuf) ist der- `map<key_type, value_type>` Typ. In diesem Abschnitt wird gezeigt, wie Sie einen `map` Typ in protobuf deklarieren und wie Sie den generierten Code verwenden.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

Im generierten Code `map` werden Felder durch schreibgeschützte Eigenschaften des- [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] Typs dargestellt. Dieser Typ implementiert die .NET-Standard Auflistungs Schnittstellen, einschließlich <xref:System.Collections.Generic.IDictionary%602> .

Karten Felder können nicht direkt in einer Nachrichten Definition wiederholt werden. Sie können jedoch eine Nachricht erstellen, die eine Zuordnung enthält und `repeated` für den Nachrichtentyp verwendet wird, wie im folgenden Beispiel gezeigt:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Verwenden von mapField-Eigenschaften im Code

Die `MapField` aus Feldern generierten Eigenschaften sind schreibgeschützt `map` und werden niemals verwendet `null` . Verwenden Sie zum Festlegen einer Zuordnungs Eigenschaft die- `Add(IDictionary<TKey,TValue> values)` Methode für die leere- `MapField` Eigenschaft, um Werte aus einem beliebigen .net-Wörterbuch zu kopieren.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Weitere nützliche Informationen

Weitere Informationen zu protobuf finden Sie in der offiziellen [protobuf-Dokumentation](https://developers.google.com/protocol-buffers/docs/overview).

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
>[Zurück](protobuf-enums.md)
>[Weiter](wcf-services-to-grpc-comparison.md)
