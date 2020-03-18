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
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="e794c-103">Wiederholte Felder für Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="e794c-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="e794c-104">Sie geben Listen in Protocol Buffer (Protobuf) mithilfe des `repeated` Präfixschlüssels an.</span><span class="sxs-lookup"><span data-stu-id="e794c-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="e794c-105">Das folgende Beispiel zeigt, wie eine Liste erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="e794c-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="e794c-106">Im generierten `repeated` Code werden Felder `Google.Protobuf.Collections.RepeatedField<T>` durch den generischen Typ und nicht durch einen der integrierten .NET-Auflistungstypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e794c-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="e794c-107">Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Drahtformat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e794c-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="e794c-108">Es implementiert alle standardmäßigen .NET-Auflistungsschnittstellen, z. <xref:System.Collections.Generic.IList%601> B. und <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e794c-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e794c-109">So können Sie LINQ-Abfragen verwenden oder sie einfach in ein Array oder eine Liste konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e794c-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e794c-110">[VorherigeS](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="e794c-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
