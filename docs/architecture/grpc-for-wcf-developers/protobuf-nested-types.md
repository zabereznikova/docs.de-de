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
# <a name="protobuf-nested-types"></a><span data-ttu-id="24ed2-103">Geschachtelter Protobuf-Typen</span><span class="sxs-lookup"><span data-stu-id="24ed2-103">Protobuf nested types</span></span>

<span data-ttu-id="24ed2-104">Ebenso wie C# das Deklarieren von Klassen in anderen Klassen ermöglicht, können Sie mithilfe des Protokoll Puffers (protobuf) Nachrichten Definitionen in anderen Nachrichten Schachteln.</span><span class="sxs-lookup"><span data-stu-id="24ed2-104">Just as C# allows you to declare classes inside other classes, Protocol Buffer (Protobuf) allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="24ed2-105">Im folgenden Beispiel wird gezeigt, wie Sie die folgenden Typen von Typen erstellen:</span><span class="sxs-lookup"><span data-stu-id="24ed2-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="24ed2-106">Im generierten C# Code wird der `Inner` Typ in einer geschachtelten statischen `Types` Klasse innerhalb der Klasse `HelloRequest` deklariert:</span><span class="sxs-lookup"><span data-stu-id="24ed2-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="24ed2-107">[Zurück](protobuf-data-types.md)
>[Weiter](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="24ed2-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
