---
title: "Gewusst wie: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts"
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
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fe22e49ee28de60bc76d7a4f543462bbcfac48c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Gewusst wie: Erstellen einer überschreibbaren Kopie eines schreibgeschützten Freezable-Objekts
Dieses Beispiel zeigt, wie die <xref:System.Windows.Freezable.Clone%2A> Methode, um eine schreibbare Kopie ein schreibgeschütztes erstellen <xref:System.Windows.Freezable>.  
  
 Nach einem <xref:System.Windows.Freezable> Objekts gekennzeichnet ist als schreibgeschützt ("eingefroren"), nicht ändern. Sie können jedoch die <xref:System.Windows.Freezable.Clone%2A> Methode, um einen änderbaren Klon des fixierten Objekts erstellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen änderbaren Klon des ein fixierter <xref:System.Windows.Media.SolidColorBrush> Objekt.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
