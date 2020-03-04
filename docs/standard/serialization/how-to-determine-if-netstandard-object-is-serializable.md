---
title: Ermitteln, ob ein .NET Standard Objekt serialisierbar ist
description: Zeigt, wie Sie bestimmen können, ob ein .NET Standard Typ zur Laufzeit serialisiert werden kann.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159896"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="8f1ae-103">Ermitteln, ob ein .NET Standard Objekt serialisierbar ist</span><span class="sxs-lookup"><span data-stu-id="8f1ae-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="8f1ae-104">Der .NET Standard ist eine Spezifikation, die die Typen und Member definiert, die für bestimmte .net-Implementierungen vorhanden sein müssen, die dieser Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="8f1ae-105">Der .NET Standard definiert jedoch nicht, ob ein Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="8f1ae-106">Die in der .NET Standard-Bibliothek definierten Typen sind nicht mit dem <xref:System.SerializableAttribute>-Attribut gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="8f1ae-107">Stattdessen können bestimmte .net-Implementierungen, wie z. b. die .NET Framework und .net Core, feststellen, ob ein bestimmter Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="8f1ae-108">Wenn Sie eine Bibliothek entwickelt haben, die die .NET Standard als Ziel hat, kann die Bibliothek von jeder .NET-Implementierung genutzt werden, die die .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="8f1ae-109">Dies bedeutet, dass Sie nicht im Voraus wissen können, ob ein bestimmter Typ serialisierbar ist. Sie können nur bestimmen, ob es zur Laufzeit serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="8f1ae-110">Sie können bestimmen, ob ein Objekt zur Laufzeit serialisierbar ist, indem Sie den Wert der <xref:System.Type.IsSerializable>-Eigenschaft eines <xref:System.Type> Objekts abrufen, das den Typ dieses Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="8f1ae-111">Im folgenden Beispiel wird eine-Implementierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-111">The following example provides one implementation.</span></span> <span data-ttu-id="8f1ae-112">Es definiert eine `IsSerializable(Object)` Erweiterungsmethode, die angibt, ob eine beliebige <xref:System.Object> Instanz serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f1ae-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="8f1ae-113">Anschließend können Sie ein beliebiges-Objekt an die-Methode übergeben, um zu bestimmen, ob es in der aktuellen .NET-Implementierung serialisiert und deserialisiert werden kann, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f1ae-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8f1ae-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f1ae-114">See also</span></span>

- [<span data-ttu-id="8f1ae-115">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8f1ae-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
