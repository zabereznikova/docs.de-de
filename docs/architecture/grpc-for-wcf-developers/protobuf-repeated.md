---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf Sammlungen behandelt und wie Sie mit .NET-Auflistungen in Beziehung stehen.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867502"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Wiederholte Felder für Listen und Arrays

Listen werden im Protokollpuffer (protobuf) mithilfe des `repeated` Schlüssel Worts "prefix" angegeben. Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Im generierten Code `repeated` werden Felder durch schreibgeschützte Eigenschaften des [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] Typs anstelle eines der integrierten .net-Auflistungs Typen dargestellt. Dieser Typ implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, z <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601> . b. und. Sie können LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren.

Der- `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist.

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
>[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)
