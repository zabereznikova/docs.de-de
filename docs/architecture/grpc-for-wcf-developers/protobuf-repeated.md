---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sammlungen von protobuf behandelt werden und wie Sie mit .NET-Auflistungen in Beziehung stehen.
ms.date: 09/09/2019
ms.openlocfilehash: 17c579bc98ba62ea74b9452bdb28efd96fc51406
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967365"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="fbb1a-103">Wiederholte Felder für Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="fbb1a-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="fbb1a-104">Listen werden in protobuf mithilfe des `repeated` Prefix-Schlüssel Worts angegeben.</span><span class="sxs-lookup"><span data-stu-id="fbb1a-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="fbb1a-105">Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="fbb1a-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="fbb1a-106">Im generierten Code werden `repeated` Felder durch den `Google.Protobuf.Collections.RepeatedField<T>` generischen Typ und nicht durch einen der integrierten .net-Auflistungs Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fbb1a-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="fbb1a-107">Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fbb1a-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="fbb1a-108">Es implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, wie z. b. <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IEnumerable%601>, sodass Sie LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="fbb1a-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fbb1a-109">[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="fbb1a-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
