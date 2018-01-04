---
title: 'Gewusst wie: Bestimmen, ob ein Freezable-Objekt fixiert ist'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eed85f982687bfc90f53e57ab1ec3949820097e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Gewusst wie: Bestimmen, ob ein Freezable-Objekt fixiert ist
Dieses Beispiel zeigt, wie Sie ermitteln, ob ein <xref:System.Windows.Freezable> Objekt eingefroren ist. Wenn Sie versuchen, ein fixierter ändern <xref:System.Windows.Freezable> -Objekt löst eine <xref:System.InvalidOperationException>. Verwenden, um zu vermeiden, dass diese Ausnahme ausgelöst, die <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft von der <xref:System.Windows.Freezable> bestimmt, ob es eingefroren wurde.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden eingefroren eine <xref:System.Windows.Media.SolidColorBrush> und testet dann mithilfe der <xref:System.Windows.Freezable.IsFrozen%2A> Eigenschaft, um zu bestimmen, ob es eingefroren wurde.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
