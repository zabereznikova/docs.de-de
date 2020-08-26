---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf Sammlungen behandelt und wie Sie mit .NET-Auflistungen in Beziehung stehen.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867502"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="234b3-103">Wiederholte Felder für Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="234b3-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="234b3-104">Listen werden im Protokollpuffer (protobuf) mithilfe des `repeated` Schlüssel Worts "prefix" angegeben.</span><span class="sxs-lookup"><span data-stu-id="234b3-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="234b3-105">Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="234b3-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="234b3-106">Im generierten Code `repeated` werden Felder durch schreibgeschützte Eigenschaften des [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] Typs anstelle eines der integrierten .net-Auflistungs Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="234b3-106">In the generated code, `repeated` fields are represented by read-only properties of the [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="234b3-107">Dieser Typ implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, z <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601> . b. und.</span><span class="sxs-lookup"><span data-stu-id="234b3-107">This type implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="234b3-108">Sie können LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren.</span><span class="sxs-lookup"><span data-stu-id="234b3-108">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

<span data-ttu-id="234b3-109">Der- `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="234b3-109">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span>

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
><span data-ttu-id="234b3-110">[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="234b3-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
