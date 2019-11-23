---
title: 'Protobuf-Netztypen: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über die Typen von genetzten Nachrichten in protobuf und GrpC C#und wie Sie in generiert werden.
ms.date: 09/09/2019
ms.openlocfilehash: bbc7ed41516d29f867bbc9da5b258f6a3c9ff261
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967390"
---
# <a name="protobuf-nested-types"></a>Geschachtelter Protobuf-Typen

Ebenso wie C# das Deklarieren von Klassen in anderen Klassen ermöglicht, können Sie Nachrichten Definitionen in anderen Nachrichten Schachteln. Im folgenden Beispiel wird gezeigt, wie Sie die folgenden Typen von Typen erstellen:

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

Im generierten C# Code wird der `Inner` Typ in einer geschachtelten statischen `Types` Klasse innerhalb der Klasse `HelloRequest` deklariert:

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[Zurück](protobuf-data-types.md)
>[Weiter](protobuf-repeated.md)
