---
title: 'Protobuf-Netztypen: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über die Typen von genetzten Nachrichten in protobuf und GrpC C#und wie Sie in generiert werden.
ms.date: 09/09/2019
ms.openlocfilehash: 7b9a331336ebe1ca7bc75fdd164b7b88ae4f9db2
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542845"
---
# <a name="protobuf-nested-types"></a>Geschachtelter Protobuf-Typen

Ebenso wie C# das Deklarieren von Klassen in anderen Klassen ermöglicht, können Sie mithilfe des Protokoll Puffers (protobuf) Nachrichten Definitionen in anderen Nachrichten Schachteln. Im folgenden Beispiel wird gezeigt, wie Sie die folgenden Typen von Typen erstellen:

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
