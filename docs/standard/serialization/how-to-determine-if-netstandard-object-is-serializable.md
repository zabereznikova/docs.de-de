---
title: 'Vorgehensweise: bestimmen, ob ein .NET Standard Objekt serialisierbar ist.'
description: Zeigt, wie Sie bestimmen, ob ein .NET Standard zur Laufzeit serialisiert werden kann.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 247eed2e7091930c6bcfaa524296b45350dd6510
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580987"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Vorgehensweise: bestimmen, ob ein .NET Standard Objekt serialisierbar ist.

.NET Standard ist eine Spezifikation, die definiert, die Typen und Member, die auf bestimmte Implementierungen von .NET vorhanden sein müssen, die auf diese Version des Standards entsprechen. Allerdings werden .NET Standard nicht definiert, ob ein Typ serialisierbar ist. In der Standardbibliothek .NET definierten Typen sind nicht gekennzeichnet, mit der <xref:System.SerializableAttribute> Attribut. Stattdessen können bestimmte .NET-Implementierungen, z. B. .NET Framework und .NET Core, zu bestimmen, ob ein bestimmter Typ serialisierbar ist. 

Wenn Sie einer Bibliothek mit der Zielversion .NET Standard entwickelt haben, kann Ihre Bibliothek von der Implementierung einer .NET verwendet werden, die den standardmäßigen .NET unterstützt. Das heißt, Sie im Voraus wissen können, ob ein bestimmter Typ serialisierbar ist. Sie können nur bestimmen, ob es zur Laufzeit serialisierbar ist.

Können Sie bestimmen, ob ein Objekt serialisierbar zur Laufzeit durch das Abrufen des Werts der <xref:System.Type.IsSerializable> Eigenschaft von einem <xref:System.Type> Objekt, das dieses Objekt darstellt. Im folgende Beispiel stellt eine Implementierung bereit. Definiert eine `IsSerializable(Object)` Erweiterungsmethode, der angibt, ob bei einem <xref:System.Object> Instanz serialisiert werden kann.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Sie können dann jedes Objekt übergeben, auf die Methode, die bestimmen, ob können serialisiert und auf die aktuelle Implementierung der .NET, wie im folgenden Beispiel gezeigt deserialisiert:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>Siehe auch

[Binäre Serialisierung](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=nameWithType>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
