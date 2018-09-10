---
title: 'Gewusst wie: Erstellen eines Objektpools mittels ConcurrentBag'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bc0c6bebbab6e84c165f41300a4cb16c8746a07
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207017"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Gewusst wie: Erstellen eines Objektpools mittels ConcurrentBag
Dieses Beispiel zeigt, wie Sie einen parallelen Behälter verwenden, um einen Objektpool zu implementieren. Objektpools können die Anwendungsleistung in Situationen verbessern, in denen Sie mehrere Instanzen einer Klasse benötigen und es teuer ist, die Klasse zu erstellen oder zu löschen. Wenn ein Clientprogramm ein neues Objekt benötigt, versucht der Objektpool zunächst, ein Objekt bereitzustellen, das bereits erstellt und an den Pool zurückgegeben wurde. Nur wenn kein Objekt verfügbar ist, wird ein neues erstellt.  
  
 Zum Speichern der Objekte wird ein <xref:System.Collections.Concurrent.ConcurrentBag%601>-Objekt verwendet, da es ein schnelles Einfügen und Entfernen unterstützt, besonders dann, wenn der gleiche Thread Elemente hinzufügt und entfernt. Dieses Beispiel kann noch bereitgestellt werden, um es auf eine <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> aufzubauen, die von der Behälterdatenstruktur implementiert wird, so wie <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>Siehe auch

- [Threadsichere Sammlungen](../../../../docs/standard/collections/thread-safe/index.md)
