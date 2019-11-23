---
title: 'Protobuf-Zuordnungen für Wörterbücher: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie protobuf-Zuordnungen zur Darstellung von verwenden. Die Wörterbuchtypen von net.
ms.date: 09/09/2019
ms.openlocfilehash: 8b4f29daa263f329dc533d3ddc596d0f47c1b6e0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967415"
---
# <a name="protobuf-maps-for-dictionaries"></a>Protobuf-Zuordnungen für Wörterbücher

Es ist wichtig, dass Sie beliebige Auflistungen benannter Werte in Nachrichten darstellen können. In .net wird dies häufig mithilfe von Wörterbuchtypen gehandhabt. Die protobuf-Entsprechung des .net-<xref:System.Collections.Generic.IDictionary%602> Typs ist der `map<key_type, value_type>`-Typ. In diesem Abschnitt wird gezeigt, wie Sie eine `map` in protobuf deklarieren und wie Sie den generierten Code verwenden.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

Im generierten Code verwenden `map` Felder die `Google.Protobuf.Collections.MapField<TKey, TValue>`-Klasse, die die .NET-Standard Auflistungs Schnittstellen implementiert, einschließlich <xref:System.Collections.Generic.IDictionary%602>.

Zuordnungs Felder können nicht direkt in einer Nachrichten Definition wiederholt werden, Sie können jedoch eine Nachricht erstellen, die eine Zuordnung enthält, und `repeated` für den Nachrichtentyp verwenden, wie im folgenden Beispiel gezeigt:

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

## <a name="further-reading"></a>Weiterführende Themen

Weitere Informationen zu protobuf finden Sie in der offiziellen [protobuf-Dokumentation](https://developers.google.com/protocol-buffers/docs/overview).

>[!div class="step-by-step"]
>[Zurück](protobuf-enums.md)
>[Weiter](wcf-services-to-grpc-comparison.md)
