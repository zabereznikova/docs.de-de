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
# <a name="protobuf-maps-for-dictionaries"></a>Protobuf-Zuordnungen für Wörterbücher

Es ist wichtig, dass Sie beliebige Auflistungen benannter Werte in Nachrichten darstellen können. In .net wird dies häufig durch Wörterbuchtypen gehandhabt. Die Entsprechung des .net-<xref:System.Collections.Generic.IDictionary%602> Typs in Protokollpuffer (protobuf) ist der `map<key_type, value_type>`-Typ. In diesem Abschnitt wird gezeigt, wie Sie einen `map` Typ in protobuf deklarieren und wie Sie den generierten Code verwenden.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

Im generierten Code verwenden `map` Felder die `Google.Protobuf.Collections.MapField<TKey, TValue>`-Klasse. Diese Klasse implementiert die standardmäßigen .net-Auflistungs Schnittstellen, einschließlich <xref:System.Collections.Generic.IDictionary%602>.

Karten Felder können nicht direkt in einer Nachrichten Definition wiederholt werden. Sie können jedoch eine Nachricht erstellen, die eine Zuordnung enthält, und `repeated` für den Nachrichtentyp verwenden, wie im folgenden Beispiel gezeigt:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Verwenden von mapField-Eigenschaften im Code

Die aus `map` Feldern generierten `MapField` Eigenschaften sind schreibgeschützt und werden niemals `null`. Um eine Zuordnungs Eigenschaft festzulegen, verwenden Sie die `Add(IDictionary<TKey,TValue> values)`-Methode der leeren `MapField`-Eigenschaft, um Werte aus einem beliebigen .net-Wörterbuch zu kopieren.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Weitere Informationsquellen

Weitere Informationen zu protobuf finden Sie in der offiziellen [protobuf-Dokumentation](https://developers.google.com/protocol-buffers/docs/overview).

>[!div class="step-by-step"]
>[Zurück](protobuf-enums.md)
>[Weiter](wcf-services-to-grpc-comparison.md)
