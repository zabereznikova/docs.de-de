---
title: 'Vorgehensweise: Ermitteln, ob ein .NET Standard-Objekt serialisierbar ist'
description: Hier erfahren Sie, wie Sie herausfinden, ob ein .NET Standard-Typ zur Laufzeit serialisiert werden kann.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: a425d44ac3b58a568bd51e638f28a2b76ced9dec
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223984"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="f7978-103">Vorgehensweise: Ermitteln, ob ein .NET Standard-Objekt serialisierbar ist</span><span class="sxs-lookup"><span data-stu-id="f7978-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="f7978-104">Bei .NET Standard handelt es sich um eine Spezifikation, die definiert, welche Typen und Member in bestimmten .NET-Implementierungen vorhanden sein müssen, die mit dieser Version des Standards übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f7978-104">.NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="f7978-105">.NET Standard legt jedoch nicht fest, ob ein Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="f7978-105">However, .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="f7978-106">Die in der .NET Standard-Bibliothek definierten Typen sind nicht mit dem Attribut <xref:System.SerializableAttribute> gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f7978-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="f7978-107">Stattdessen kann bei bestimmten .NET-Implementierungen, wie .NET Framework und .NET Core, unabhängig bestimmt werden, ob ein bestimmter Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="f7978-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="f7978-108">Wenn Sie eine Bibliothek für .NET Standard entwickelt haben, kann diese von jeder .NET-Implementierung verarbeitet werden, die .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f7978-108">If you've developed a library that targets .NET Standard, your library can be consumed by any .NET implementation that supports .NET Standard.</span></span> <span data-ttu-id="f7978-109">Daher können Sie nicht im Voraus wissen, ob ein bestimmter Typ serialisierbar ist. Dies ist erst zur Laufzeit möglich.</span><span class="sxs-lookup"><span data-stu-id="f7978-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="f7978-110">Wenn Sie ermitteln möchten, ob ein Objekt zur Laufzeit serialisierbar ist, rufen Sie den Wert der <xref:System.Type.IsSerializable>-Eigenschaft eines <xref:System.Type>-Objekts ab, das den Typ dieses Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="f7978-110">You can determine whether an object is serializable at run time by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="f7978-111">Der folgende Code zeigt ein Implementierungsbeispiel.</span><span class="sxs-lookup"><span data-stu-id="f7978-111">The following example provides one implementation.</span></span> <span data-ttu-id="f7978-112">Es definiert die Erweiterungsmethode `IsSerializable(Object)`, mit der angegeben wird, ob eine beliebige <xref:System.Object>-Instanz serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7978-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="f7978-113">Anschließend können Sie ein beliebiges Objekt an die Methode übergeben, um herauszufinden, ob es in der aktuellen .NET-Implementierung serialisiert und deserialisiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="f7978-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f7978-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7978-114">See also</span></span>

- [<span data-ttu-id="f7978-115">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="f7978-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
