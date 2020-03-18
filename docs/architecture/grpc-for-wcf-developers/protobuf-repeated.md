---
title: Wiederholte Felder für Listen und Arrays - gRPC für WCF-Entwickler
description: Verstehen, wie Protobuf Sammlungen verarbeitet und wie sie sich auf .NET-Auflistungen beziehen.
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147970"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Wiederholte Felder für Listen und Arrays

Sie geben Listen in Protocol Buffer (Protobuf) mithilfe des `repeated` Präfixschlüssels an. Das folgende Beispiel zeigt, wie eine Liste erstellt wird:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Im generierten `repeated` Code werden Felder `Google.Protobuf.Collections.RepeatedField<T>` durch den generischen Typ und nicht durch einen der integrierten .NET-Auflistungstypen dargestellt.

Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Drahtformat erforderlich ist. Es implementiert alle standardmäßigen .NET-Auflistungsschnittstellen, z. <xref:System.Collections.Generic.IList%601> B. und <xref:System.Collections.Generic.IEnumerable%601>. So können Sie LINQ-Abfragen verwenden oder sie einfach in ein Array oder eine Liste konvertieren.

>[!div class="step-by-step"]
>[VorherigeS](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)
