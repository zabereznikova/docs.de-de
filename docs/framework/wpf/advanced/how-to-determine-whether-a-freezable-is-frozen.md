---
title: 'Vorgehensweise: Bestimmen, ob ein Freezable-Objekt fixiert ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776232"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Vorgehensweise: Bestimmen, ob ein Freezable-Objekt fixiert ist
Dieses Beispiel zeigt, wie Sie ermitteln, ob eine <xref:System.Windows.Freezable> Objekt eingefroren ist. Wenn Sie versuchen, ein fixiertes ändern <xref:System.Windows.Freezable> -Objekt löst eine <xref:System.InvalidOperationException>. Verwenden, um zu vermeiden, diese Ausnahme auslöst, die <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft der <xref:System.Windows.Freezable> bestimmt, ob er fixiert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel friert ein <xref:System.Windows.Media.SolidColorBrush> und testet dann mithilfe der <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft, um zu bestimmen, ob er fixiert ist.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Übersicht über Freezable-Objekte](freezable-objects-overview.md)
- [Themen zu Vorgehensweisen](base-elements-how-to-topics.md)
