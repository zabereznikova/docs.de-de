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
# <a name="protobuf-nested-types"></a><span data-ttu-id="959ea-103">Geschachtelter Protobuf-Typen</span><span class="sxs-lookup"><span data-stu-id="959ea-103">Protobuf nested types</span></span>

<span data-ttu-id="959ea-104">Ebenso wie C# das Deklarieren von Klassen in anderen Klassen ermöglicht, können Sie Nachrichten Definitionen in anderen Nachrichten Schachteln.</span><span class="sxs-lookup"><span data-stu-id="959ea-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="959ea-105">Im folgenden Beispiel wird gezeigt, wie Sie die folgenden Typen von Typen erstellen:</span><span class="sxs-lookup"><span data-stu-id="959ea-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="959ea-106">Im generierten C# Code wird der `Inner` Typ in einer geschachtelten statischen `Types` Klasse innerhalb der Klasse `HelloRequest` deklariert:</span><span class="sxs-lookup"><span data-stu-id="959ea-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="959ea-107">[Zurück](protobuf-data-types.md)
>[Weiter](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="959ea-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
