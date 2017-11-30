---
title: "Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c029a763faaa0b4d6ea5612efe079e47415b6fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben
Das folgende Beispiel zeigt zwei Möglichkeiten, die in denen Parallele Aufgaben verwendet werden können, um eine strukturdatenstruktur zu durchlaufen. Die Erstellung der Struktur selbst wird als eine Übung beibehalten.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Die beiden Methoden gezeigt sind funktional äquivalent. Mithilfe der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> Methode zum Erstellen und Ausführen der Aufgaben erhalten Sie ein Handle von den Aufgaben, die zum Warten auf die Aufgaben und Behandeln von Ausnahmen verwendet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
