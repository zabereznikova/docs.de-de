---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf Sammlungen behandelt und wie Sie mit .NET-Auflistungen in Beziehung stehen.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542958"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="0396c-103">Wiederholte Felder für Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="0396c-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="0396c-104">Listen werden im Protokollpuffer (protobuf) mithilfe des `repeated` Prefix-Schlüssel Worts angegeben.</span><span class="sxs-lookup"><span data-stu-id="0396c-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="0396c-105">Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="0396c-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="0396c-106">Im generierten Code werden `repeated` Felder durch den `Google.Protobuf.Collections.RepeatedField<T>` generischen Typ und nicht durch einen der integrierten .net-Auflistungs Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0396c-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="0396c-107">Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0396c-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="0396c-108">Es implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, z. b. <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0396c-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="0396c-109">Sie können LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0396c-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0396c-110">[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="0396c-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
