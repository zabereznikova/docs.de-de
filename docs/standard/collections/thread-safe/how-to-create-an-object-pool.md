---
title: Erstellen eines Objektpools mittels ConcurrentBag
ms.date: 05/01/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: 2c060dc901f8d06a5f9c51db1cd563cb28e4fda3
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728473"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a>Erstellen eines Objektpools mittels ConcurrentBag

Dieses Beispiel zeigt, wie Sie einen <xref:System.Collections.Concurrent.ConcurrentBag%601> verwenden, um einen Objektpool zu implementieren. Objektpools können die Anwendungsleistung in Situationen verbessern, in denen Sie mehrere Instanzen einer Klasse benötigen und es teuer ist, die Klasse zu erstellen oder zu löschen. Wenn ein Clientprogramm ein neues Objekt benötigt, versucht der Objektpool zunächst, ein Objekt bereitzustellen, das bereits erstellt und an den Pool zurückgegeben wurde. Nur wenn kein Objekt verfügbar ist, wird ein neues erstellt.

Zum Speichern der Objekte wird ein <xref:System.Collections.Concurrent.ConcurrentBag%601>-Objekt verwendet, da es ein schnelles Einfügen und Entfernen unterstützt, besonders dann, wenn der gleiche Thread Elemente hinzufügt und entfernt. Dieses Beispiel kann noch bereitgestellt werden, um es auf eine <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> aufzubauen, die von der Behälterdatenstruktur implementiert wird, so wie <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.

> [!TIP]
> In diesem Artikel wird beschrieben, wie Sie Ihre eigene Implementierung eines Objektpools mit einem zugrunde liegenden gleichzeitigen Typ („concurrent“) schreiben, um Objekte zur Wiederverwendung zu speichern. Der Typ <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> ist jedoch bereits unter dem Namespace <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> vorhanden. Sie sollten den verfügbaren Typ verwenden, bevor Sie eine eigene Implementierung erstellen, die viele zusätzliche Features umfasst.

## <a name="example"></a>Beispiel

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a>Siehe auch

- [Threadsichere Sammlungen](../../../../docs/standard/collections/thread-safe/index.md)
