---
title: So bestimmen, ob ein .NET Standard-Objekt serialisierbar ist.
description: Zeigt, wie Sie bestimmen, ob ein .NET Standard-Typ zur Laufzeit serialisiert werden kann.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881407"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>So bestimmen, ob ein .NET Standard-Objekt serialisierbar ist.

.NET Standard ist eine Spezifikation, die definiert die Typen und Member, die in bestimmten .NET-Implementierungen vorhanden sein müssen, die diese Version des Standards entsprechen. Allerdings werden .NET Standard nicht definiert, ob ein Typ serialisiert werden. In .NET Standard-Bibliothek definierten Typen sind nicht gekennzeichnet, mit der <xref:System.SerializableAttribute> Attribut. Stattdessen können sich bestimmte Implementierungen von .NET, z.B. .NET Framework und .NET Core, um zu bestimmen, ob ein bestimmter Typ serialisierbar ist. 

Wenn Sie einer Bibliothek, das als Ziel .NET Standard entwickelt haben, kann Ihre Bibliothek von jeder .NET Implementierung verwendet werden, die .NET Standard unterstützt. Das heißt, Sie im Voraus wissen können, ob ein bestimmter Typ serialisierbar ist. Sie können nur bestimmen, ob es zur Laufzeit serialisierbar ist.

Können Sie bestimmen, ob ein Objekt serialisierbar ist, zur Laufzeit durch Abrufen des Werts der der <xref:System.Type.IsSerializable> Eigenschaft eine <xref:System.Type> -Objekt, Typ des Objekts darstellt. Im folgenden Beispiel wird eine Implementierung. Definiert eine `IsSerializable(Object)` -Erweiterungsmethode, der angibt, ob ein <xref:System.Object> Instanz serialisiert werden kann.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Sie können dann ein Objekt übergeben, an die Methode, um festzustellen, ob es kann serialisiert und in der aktuellen.NET-Implementierung, wie im folgenden Beispiel gezeigt deserialisiert:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
