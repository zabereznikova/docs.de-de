---
title: "Gewusst wie: Verwenden von Triggern zum Formatieren ausgew&#228;hlter Elemente in einem ListView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ListView-Steuerelemente, Stile"
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Verwenden von Triggern zum Formatieren ausgew&#228;hlter Elemente in einem ListView
Dieses Beispiel zeigt, wie Sie definieren <xref:System.Windows.Style.Triggers%2A> für eine <xref:System.Windows.Controls.ListViewItem> Steuerelement, damit bei einem Eigenschaftswert, der eine <xref:System.Windows.Controls.ListViewItem> ändert, der <xref:System.Windows.Style> von der <xref:System.Windows.Controls.ListViewItem> Änderungen in der Antwort.  
  
## <a name="example"></a>Beispiel  
 Sie ggf. die <xref:System.Windows.Style> von einer <xref:System.Windows.Controls.ListViewItem> definieren, um als Reaktion auf Änderungen an den Eigenschaften zu ändern, <xref:System.Windows.Style.Triggers%2A> für die <xref:System.Windows.Style> ändern.  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.Trigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> -Eigenschaft auf <xref:System.Windows.Media.Brushes.Blue%2A> und ändert die <xref:System.Windows.FrameworkElement.Cursor%2A> angezeigt eine <xref:System.Windows.Input.CursorType> bei der <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft ändert sich in `true`.  
  
 [!code-xml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.MultiTrigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> -Eigenschaft des ein <xref:System.Windows.Controls.ListViewItem> zu <xref:System.Windows.Media.Brushes.Yellow%2A> bei der <xref:System.Windows.Controls.ListViewItem> das ausgewählte Element und den Tastaturfokus hat.  
  
 [!code-xml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Control>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Gewusst-wie-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)