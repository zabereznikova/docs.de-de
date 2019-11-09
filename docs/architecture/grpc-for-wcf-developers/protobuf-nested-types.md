---
title: 'Protobuf-Netztypen: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über die Typen von genetzten Nachrichten in protobuf und GrpC C#und wie Sie in generiert werden.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ec9fc522619230c1201bfef1e8128f7356936212
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841402"
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
