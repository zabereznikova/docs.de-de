---
title: 'Vorgehensweise: Abrufen der Standardansicht einer Datensammlung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 746331e69ee1e5eee795a0e35202f4889b72c53f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222106"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Vorgehensweise: Abrufen der Standardansicht einer Datensammlung
Sichten können die Datenerfassung auf unterschiedliche Weise je nach sortieren, filtern oder gruppieren die Kriterien angezeigt werden. Jede Sammlung verfügt über eine gemeinsame Standardansicht, die als die tatsächliche Bindung-Quelle verwendet wird, wenn eine Bindung eine Sammlung als Quelle angegeben. In diesem Beispiel veranschaulicht das Abrufen der Standardansicht einer Auflistung.  
  
## <a name="example"></a>Beispiel  
 Um die Ansicht zu erstellen, benötigen Sie einen Objektverweis auf die Auflistung ein. Dieses Datenobjekt kann durch Verweisen auf Ihren eigenen Code-Behind-Objekt, durch den Datenkontext, abrufen, indem Abrufen einer Eigenschaft der Datenquelle oder Abrufen einer Eigenschaft der Bindung abgerufen werden. In diesem Beispiel wird gezeigt, wie zum Abrufen der <xref:System.Windows.FrameworkElement.DataContext%2A> ein Datenobjekt und die Verwendung die standardauflistung direkt abrufen Anzeigeberechtigung für diese Sammlung.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In diesem Beispiel ist das Stammelement ist ein <xref:System.Windows.Controls.StackPanel>. Die <xref:System.Windows.FrameworkElement.DataContext%2A> nastaven NA hodnotu *MyDataSource*, die bezieht sich auf einen Datenanbieter, die eine <xref:System.Collections.ObjectModel.ObservableCollection%601> von *Reihenfolge* Objekte.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Alternativ können Sie instanziieren und Binden an eine eigene Auflistung Ansicht mithilfe der <xref:System.Windows.Data.CollectionViewSource> Klasse. Dieser Auflistungsansicht wird nur von Steuerelementen gemeinsam genutzt, die direkt an ihn binden. Ein Beispiel finden Sie unter Vorgehensweise erstellen Sie eine Ansicht im Abschnitt der [Übersicht über die Datenbindung](data-binding-overview.md).  
  
 Beispiele für die Funktionalität einer Auflistungsansicht, finden Sie unter [Sortieren von Daten in einer Ansicht](how-to-sort-data-in-a-view.md), [Filtern von Daten in einer Ansicht](how-to-filter-data-in-a-view.md), und [Navigieren durch die Objekte in einer Datenauflistungsansicht](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
