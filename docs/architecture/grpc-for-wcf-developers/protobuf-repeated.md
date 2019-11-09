---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sammlungen von protobuf behandelt werden und wie Sie mit .NET-Auflistungen in Beziehung stehen.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841396"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="ce4f7-103">Wiederholte Felder für Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="ce4f7-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="ce4f7-104">Listen werden in protobuf mithilfe des `repeated` Prefix-Schlüssel Worts angegeben.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="ce4f7-105">Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="ce4f7-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="ce4f7-106">Im generierten Code werden `repeated` Felder durch den `Google.Protobuf.Collections.RepeatedField<T>` generischen Typ und nicht durch einen der integrierten .net-Auflistungs Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="ce4f7-107">Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="ce4f7-108">Es implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, wie z. b. <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IEnumerable%601>, sodass Sie LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ce4f7-109">[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="ce4f7-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
