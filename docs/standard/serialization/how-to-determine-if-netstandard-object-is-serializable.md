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
ms.openlocfilehash: 9f7ab8a824b9687f68382a5edc342536289c5d09
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282323"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Vorgehensweise: Ermitteln, ob ein .NET Standard-Objekt serialisierbar ist

Bei .NET Standard handelt es sich um eine Spezifikation, die definiert, welche Typen und Member in bestimmten .NET-Implementierungen vorhanden sein müssen, die mit dieser Version des Standards übereinstimmen. .NET Standard legt jedoch nicht fest, ob ein Typ serialisierbar ist. Die in der .NET Standard-Bibliothek definierten Typen sind nicht mit dem Attribut <xref:System.SerializableAttribute> gekennzeichnet. Stattdessen kann bei bestimmten .NET-Implementierungen, wie .NET Framework und .NET Core, unabhängig bestimmt werden, ob ein bestimmter Typ serialisierbar ist.

Wenn Sie eine Bibliothek für .NET Standard entwickelt haben, kann diese von jeder .NET-Implementierung verarbeitet werden, die .NET Standard unterstützt. Daher können Sie nicht im Voraus wissen, ob ein bestimmter Typ serialisierbar ist. Dies ist erst zur Laufzeit möglich.

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
