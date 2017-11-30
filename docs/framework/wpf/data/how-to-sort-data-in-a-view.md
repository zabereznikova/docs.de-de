---
title: 'Gewusst wie: Sortieren von Daten in einer Ansicht'
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
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c39cec8aaf12b268790c19751562b16fa34cfdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-data-in-a-view"></a>Gewusst wie: Sortieren von Daten in einer Ansicht
In diesem Beispiel wird das Sortieren von Daten in einer Ansicht beschreibt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine einfache <xref:System.Windows.Controls.ListBox> und ein <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der Schaltfläche enthält die Logik zum Sortieren der Elemente in der <xref:System.Windows.Controls.ListBox> in absteigender Reihenfolge. Hierzu können Sie da Elemente hinzufügen einer <xref:System.Windows.Controls.ListBox> auf diese Weise hinzugefügt der <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Controls.ListBox>, und <xref:System.Windows.Controls.ItemCollection> leitet sich von der <xref:System.Windows.Data.CollectionView> Klasse. Wenn Sie binden Ihrer <xref:System.Windows.Controls.ListBox> zu einer Sammlung mit den <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft, können Sie das gleiche Verfahren zum Sortieren.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Solange Sie einen Verweis auf das Ansichtsobjekt verfügen, können Sie das gleiche Verfahren, um den Inhalt der anderen Auflistungsansichten zu sortieren. Ein Beispiel zum Abrufen einer Ansicht finden Sie unter [die Standardansicht einer Datensammlung erhalten](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView Spalte bei einem Header geklickt wird](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Weitere Informationen zu Ansichten finden Sie unter Bindung für Sammlungen im [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Ein Beispiel zum Sortierfunktionen in Anwenden von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], finden Sie unter [sortieren und Gruppe mithilfe einer Sicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
