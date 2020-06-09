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
ms.openlocfilehash: b6791ae0666aeb0ac02d8a38ca419d7de2b263cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289602"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Vorgehensweise: Ermitteln, ob ein .NET Standard-Objekt serialisierbar ist

Mit der Angabe .NET Standard wird definiert, welche Typen und Member für bestimmte .NET-Implementierungen vorhanden sein müssen, die mit dieser Version übereinstimmen. Die Angabe .NET Standard besagt jedoch nicht, ob ein Typ serialisierbar ist. Die in der .NET Standard-Bibliothek definierten Typen sind nicht mit dem Attribut <xref:System.SerializableAttribute> gekennzeichnet. Stattdessen kann bei bestimmten .NET-Implementierungen, wie .NET Framework und .NET Core, unabhängig bestimmt werden, ob ein bestimmter Typ serialisierbar ist.

Wenn Sie eine Bibliothek entwickelt haben, die sich auf .NET Standard bezieht, kann diese von jeder .NET-Implementierung genutzt werden, die .NET Standard unterstützt. Daher können Sie nicht im Voraus wissen, ob ein bestimmter Typ serialisierbar ist. Dies ist erst zur Laufzeit möglich.

Wenn Sie ermitteln möchten, ob ein Objekt zur Laufzeit serialisierbar ist, rufen Sie den Wert der <xref:System.Type.IsSerializable>-Eigenschaft eines <xref:System.Type>-Objekts ab, das den Typ dieses Objekts darstellt. Der folgende Code zeigt ein Implementierungsbeispiel. Es definiert die Erweiterungsmethode `IsSerializable(Object)`, mit der angegeben wird, ob eine beliebige <xref:System.Object>-Instanz serialisiert werden kann.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Anschließend können Sie ein beliebiges Objekt an die Methode übergeben, um herauszufinden, ob es in der aktuellen .NET-Implementierung serialisiert und deserialisiert werden kann:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
