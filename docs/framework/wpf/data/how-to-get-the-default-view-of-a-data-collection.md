---
title: 'Gewusst wie: Abrufen der Standardansicht einer Datenauflistung'
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
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebb74e1db2e63269f70a13ef8520ab1383ecae08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Gewusst wie: Abrufen der Standardansicht einer Datenauflistung
Ansichten können die gleichen Datensammlung unterschiedlich, je nach sortieren, filtern oder Gruppierungskriterien angezeigt werden. Jede Auflistung verfügt über eine freigegebene Standardansicht, die als tatsächliche Bindungsquelle verwendet wird, wenn eine Bindung eine Auflistung als Updatequelle angibt. In diesem Beispiel wird gezeigt, wie die Standardansicht einer Auflistung abgerufen werden.  
  
## <a name="example"></a>Beispiel  
 Um die Ansicht zu erstellen, benötigen Sie einen Objektverweis auf die Auflistung ein. Dieses Datenobjekt kann durch Verweisen auf Ihren eigenen Code-Behind-Objekt, durch den Datenkontext abrufen, indem Abrufen einer Eigenschaft der Datenquelle oder Abrufen einer Eigenschaft der Bindung abgerufen werden. In diesem Beispiel wird gezeigt, wie zum Abrufen der <xref:System.Windows.FrameworkElement.DataContext%2A> des ein Datenobjekt und verwenden Sie ihn direkt der standardauflistung abgerufen für diese Sammlung anzuzeigen.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In diesem Beispiel ist das Stammelement einer <xref:System.Windows.Controls.StackPanel>. Die <xref:System.Windows.FrameworkElement.DataContext%2A> auf festgelegt ist *MyDataSource*, dem bezieht sich auf einen Datenanbieter, der eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von *Reihenfolge* Objekte.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Alternativ können Sie instanziieren und Binden an Ihre eigene Auflistung Ansicht mithilfe der <xref:System.Windows.Data.CollectionViewSource> Klasse. Dieser Auflistungsansicht wird nur von Steuerelementen gemeinsam genutzt, die direkt an diese binden. Ein Beispiel finden Sie in den zum Erstellen eine Ansicht im Abschnitt der [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Beispiele für die Funktionalität, die von einer Auflistungsansicht bereitgestellt, finden Sie unter [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), und [navigieren Sie über die Objekte in einer Datenauflistungsansicht](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
