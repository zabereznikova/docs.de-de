---
title: "Gewusst wie: Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e86c7f875376a4ab28eec7cd032a165745445441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>Gewusst wie: Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView
In diesem Beispiel wird gezeigt, wie definiert <xref:System.Windows.Style.Triggers%2A> für eine <xref:System.Windows.Controls.ListViewItem> Steuerelement, damit bei einem Eigenschaftswert des eine <xref:System.Windows.Controls.ListViewItem> Änderungen, die <xref:System.Windows.Style> von der <xref:System.Windows.Controls.ListViewItem> Änderungen als Reaktion.  
  
## <a name="example"></a>Beispiel  
 Gegebenenfalls die <xref:System.Windows.Style> von einem <xref:System.Windows.Controls.ListViewItem> definieren, um als Reaktion auf eigenschaftenänderungen zu ändern, <xref:System.Windows.Style.Triggers%2A> für die <xref:System.Windows.Style> ändern.  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.Trigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft, um <xref:System.Windows.Media.Brushes.Blue%2A> und ändert die <xref:System.Windows.FrameworkElement.Cursor%2A> anzuzeigenden eine <xref:System.Windows.Input.CursorType.Hand> bei der <xref:System.Windows.UIElement.IsMouseOver%2A> eigenschaftsänderungen `true`.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.MultiTrigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft eine <xref:System.Windows.Controls.ListViewItem> zu <xref:System.Windows.Media.Brushes.Yellow%2A> bei der <xref:System.Windows.Controls.ListViewItem> das ausgewählte Element ist und über den Tastaturfokus verfügt.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
