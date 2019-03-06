---
title: 'Vorgehensweise: Bestimmen, ob ein Freezable-Objekt fixiert ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362512"
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
