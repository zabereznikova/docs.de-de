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
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Ermitteln, ob ein .NET Standard Objekt serialisierbar ist

Der .NET Standard ist eine Spezifikation, die die Typen und Member definiert, die für bestimmte .net-Implementierungen vorhanden sein müssen, die dieser Version des Standards entsprechen. Der .NET Standard definiert jedoch nicht, ob ein Typ serialisierbar ist. Die in der .NET Standard-Bibliothek definierten Typen sind nicht mit dem <xref:System.SerializableAttribute>-Attribut gekennzeichnet. Stattdessen können bestimmte .net-Implementierungen, wie z. b. die .NET Framework und .net Core, feststellen, ob ein bestimmter Typ serialisierbar ist.

Wenn Sie eine Bibliothek entwickelt haben, die die .NET Standard als Ziel hat, kann die Bibliothek von jeder .NET-Implementierung genutzt werden, die die .NET Standard unterstützt. Dies bedeutet, dass Sie nicht im Voraus wissen können, ob ein bestimmter Typ serialisierbar ist. Sie können nur bestimmen, ob es zur Laufzeit serialisierbar ist.

Sie können bestimmen, ob ein Objekt zur Laufzeit serialisierbar ist, indem Sie den Wert der <xref:System.Type.IsSerializable>-Eigenschaft eines <xref:System.Type> Objekts abrufen, das den Typ dieses Objekts darstellt. Im folgenden Beispiel wird eine-Implementierung bereitstellt. Es definiert eine `IsSerializable(Object)` Erweiterungsmethode, die angibt, ob eine beliebige <xref:System.Object> Instanz serialisiert werden kann.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Anschließend können Sie ein beliebiges-Objekt an die-Methode übergeben, um zu bestimmen, ob es in der aktuellen .NET-Implementierung serialisiert und deserialisiert werden kann, wie im folgenden Beispiel gezeigt:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
