---
title: 'Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6446145d34d22503697bbca59bc2cb2cd2619cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben
Das folgende Beispiel zeigt zwei Möglichkeiten, wie parallele Aufgaben verwendet werden können, um eine Datenstruktur zu durchlaufen. Die Erstellung der Struktur selbst dient als Übung.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Die beiden gezeigten Methoden sind funktional äquivalent. Wenn Sie die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>-Methode zum Erstellen und Ausführen der Aufgaben verwenden, geben die Aufgaben ein Handle zurück, das zum Warten auf die Aufgaben und Behandeln von Ausnahmen verwendet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
