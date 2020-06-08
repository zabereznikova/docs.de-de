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
ms.openlocfilehash: 5ac81a61691ec20daafc9e18978ba5814a150383
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288068"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben
Das folgende Beispiel zeigt zwei Möglichkeiten, wie parallele Aufgaben verwendet werden können, um eine Datenstruktur zu durchlaufen. Die Erstellung der Struktur selbst dient als Übung.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Die beiden gezeigten Methoden sind funktional äquivalent. Wenn Sie die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>-Methode zum Erstellen und Ausführen der Aufgaben verwenden, geben die Aufgaben ein Handle zurück, das zum Warten auf die Aufgaben und Behandeln von Ausnahmen verwendet werden kann.  
  
## <a name="see-also"></a>Weitere Informationen

- [Task Parallel Library (TPL)](task-parallel-library-tpl.md)
