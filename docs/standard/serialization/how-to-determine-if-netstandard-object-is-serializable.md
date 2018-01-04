---
title: 'Vorgehensweise: bestimmen, ob ein .NET Standard Objekt serialisierbar ist.'
description: Zeigt, wie Sie bestimmen, ob ein .NET Standard zur Laufzeit serialisiert werden kann.
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c44e350ad4e561f03bf6c598172058a0a9ca41e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="87d2f-103">Vorgehensweise: bestimmen, ob ein .NET Standard Objekt serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="87d2f-103">How to: Determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="87d2f-104">.NET Standard ist eine Spezifikation, die definiert, die Typen und Member, die auf bestimmte Implementierungen von .NET vorhanden sein müssen, die auf diese Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="87d2f-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="87d2f-105">Allerdings werden .NET Standard nicht definiert, ob ein Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="87d2f-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="87d2f-106">In der Standardbibliothek .NET definierten Typen sind nicht gekennzeichnet, mit der <xref:System.SerializableAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="87d2f-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="87d2f-107">Stattdessen können bestimmte .NET-Implementierungen, z. B. .NET Framework und .NET Core, zu bestimmen, ob ein bestimmter Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="87d2f-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="87d2f-108">Wenn Sie einer Bibliothek mit der Zielversion .NET Standard entwickelt haben, kann Ihre Bibliothek von der Implementierung einer .NET verwendet werden, die den standardmäßigen .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="87d2f-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="87d2f-109">Das heißt, Sie im Voraus wissen können, ob ein bestimmter Typ serialisierbar ist. Sie können nur bestimmen, ob es zur Laufzeit serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="87d2f-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="87d2f-110">Können Sie bestimmen, ob ein Objekt serialisierbar zur Laufzeit durch das Abrufen des Werts der <xref:System.Type.IsSerializable> Eigenschaft von einem <xref:System.Type> Objekt, das dieses Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="87d2f-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="87d2f-111">Im folgende Beispiel stellt eine Implementierung bereit.</span><span class="sxs-lookup"><span data-stu-id="87d2f-111">The following example provides one implementation.</span></span> <span data-ttu-id="87d2f-112">Definiert eine `IsSerializable(Object)` Erweiterungsmethode, der angibt, ob bei einem <xref:System.Object> Instanz serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="87d2f-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="87d2f-113">Sie können dann jedes Objekt übergeben, auf die Methode, die bestimmen, ob können serialisiert und auf die aktuelle Implementierung der .NET, wie im folgenden Beispiel gezeigt deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="87d2f-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a><span data-ttu-id="87d2f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87d2f-114">See also</span></span>

<span data-ttu-id="87d2f-115">[Binäre Serialisierung](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="87d2f-115">[Binary serialization](binary-serialization.md) </span></span>  
<span data-ttu-id="87d2f-116"><xref:System.SerializableAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="87d2f-116"><xref:System.SerializableAttribute?displayProperty=fullName></span></span>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
