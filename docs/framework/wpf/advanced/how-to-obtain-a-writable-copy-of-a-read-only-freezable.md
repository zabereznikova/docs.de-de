---
title: 'Vorgehensweise: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 2853b1e02e1223cbb2b6dff4acbddb0a41d882cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629955"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Vorgehensweise: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Freezable.Clone%2A> Methode zum Erstellen einer überschreibbaren Kopie eine schreibgeschützte <xref:System.Windows.Freezable>.  
  
 Nach einem <xref:System.Windows.Freezable> Objekt markiert ist als schreibgeschützt ("eingefroren"), nicht ändern. Sie können jedoch die <xref:System.Windows.Freezable.Clone%2A> Methode, um einen änderbaren Klon des fixierten Objekts zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen änderbaren Klon eines fixierten <xref:System.Windows.Media.SolidColorBrush> Objekt.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
